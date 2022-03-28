---
sidebar_position: 7
sidebar_label: Querschnittliche Konzepte
---

# Querschnittliche Konzepte

Dieser Abschnitt beschreibt allgemeine Strukturen und Aspekte, die systemweit gelten. Darüber hinaus stellt er verschiedene technische Lösungskonzepte vor.

## 8.1 Abhängigkeiten
ChickenApplication folgt dem Konzept der Onion-Architektur und ist folgendermaßen unterteilt:

<img src="/img/UML-8.png" alt="UML zur Beschreibung der genaueren Struktur" />

## 8.2 Die User
Die Anwendung ist von 3 verschiedenen Rollen aus nutzbar, den Studenten, den Tutoren und den Organisatoren.

Die Anmeldung erfolgt über GitHub, wonach der User anhand seiner ID identifiziert wird.
Die Rolle eines Users bestimmt, auf welche Ansichten er Zugriff hat, und somit auch, auf welche Bedienelemente der Application.

## 8.3 Das Student-Aggregat
Der Student speichert seine Klausuranmeldungen, so wie seine angemeldeten Urlaubseinträge.
Urlaub und angemeldete Klausuren können direkt aus dem Studenten abgefragt werden.
Ebenso kann Urlaub gebucht werden, und Klausuren können gebucht oder storniert werden.

Die Entscheidung, Urlaub und Student zusammenzulegen entstand aus dem Schluss, dass Urlaub und Student sich immer zusammen verändern, und somit in ein Aggregat gehören.

Identifiziert werden Studenten über ihre GitHub-ID

## 8.4 Das Klausur-Aggregat

Klausuren speichern ihr Datum, so wie ihre Start- und Endzeit.
Wichtig zu beachten ist, dass die Freistellung nicht intern gespeichert wird, sondern über die Methoden `getStartExemption()` und `getEndExemption()` angefragt werden kann.
Die Flag isOnline definiert, ob die Klausur in Präsenz stattfindet, was dementsprechend die Ausgabe der Freistellungen beeinflusst.
Identifiert wird die Klausur über ihre LSF-ID.

## 8.5 Das AuditLog-Aggregat

Der Auditlog ist entsprechend seiner Aufgabe recht simpel gehalten.
Urlaubsbuchungen oder Stornierungen werden hier dokumentiert, um später vom Organisator abgefragt zu werden.
Urlaubsbuchungen werden natürlich nur dann eingetragen, wenn die Buchung gültig ist.

Auditlog-Einträge werden anhand der GitHub-ID des Studenten, welcher die Buchung durchgeführt hat, zugeordnet.

## 8.6 Der Urlaub

Urlaub ist simpel gehalten - es werden DateTimes gespeichert, um Start und Ende zu definieren.
Urlaube werden innerhalb des Studenten gespeichert.

## 8.7 Der ApplicationService

Um Urlaube und Klausureinträge zu ändern, werden Studenten innerhalb des Application-Service manipuliert, und anschließend wieder gespeichert.
Die Controller nutzen Zugriff auf den ApplicationService, um Anfragen zu stellen und die eingegebenen Daten entsprechend zu verarbeiten.

## 8.8 UrlaubValidator

Der UrlaubValidator prüft, ob Urlaubseingaben valide sind, er  implementiert das "Validator"-Interface.
Die Überprüfung beinhaltet, ob der Urlaub passend in 15 Minuten-Blöcken eingegeben wird, die Zeiten sinnvoll eingegeben, und alle notwendigen Eingaben vorhanden sind.
Bei Fehlern wird eine entsprechende Error-Message generiert, die von außen angefragt werden kann, bei erfolgreicher Prüfung wird ein Pair aus LocalDateTimes zurückgegeben.

## 8.9 KlausurValidator
Der KlasurValiddator prüft, ob Klausureingaben gültig sind, er implementiert das "Validator"-Interface.
Die Überprüfung beinhaltet, ob die Klausur passend in 15 Minuten-Blöcken eingegeben wird, die Zeiten sinnvoll eingegeben, und alle notwendigen Eingaben vorhanden sind.
Bei Fehlern wird eine entsprechende Error-Message generiert, die von außen angefragt werden kann, bei erfolgreicher Prüfung wird ein Klausur-Objekt zurückgegeben.

## 8.10 Validadtor-Interface
Das Validator-Interface bietet die Methode "validate", mit der die Eingaben für den jeweiligen Validator überprüft werden können, so wie die Methode `getErrorMessage()`, um den entsprechenden Fehler zu identifizieren.

## 8.11 Der StudentService
Der StudentService kann Urlaub anpassen und neue Buchungen in bereits vorhandene Einträge einfügen.
Um dies zu tun, werden verhandene Klausuranmeldungen und Urlaubsbuchungen mit neuen Einträgen verglichen, und so entsprechende Urlaubsblöcke zerteilt, oder zusammengefügt.