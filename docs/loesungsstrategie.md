---
sidebar_position: 5
sidebar_label: Lösungsstrategie
---

# Lösungsstrategie

Dieser Abschnitt enthält einen stark verdichteten Architekturüberblick. Eine Gegenüberstellung der wichtigsten Ziele und Lösungsansätze.

## 4.1 Einsteig in die Lösungsstrategie

|Qualitätsziel|Dem zuträgliche Ansätze in der Architektur|
|--------------|:-----:|
|Analysierbarkeit| <ul><li>Architekturüberblick nach arc42</li><li>Klares Domänemodell</li></ul>|
|Änderbarkeit|<ul><li>verbreitete Programmiersprache (Java)</li><li>Klare Kapselung der Aufgaben und Aggregate</li></ul>|
|Interaktion|<ul><li>Klare Trennung der Zugriffe anhand der Rollen</li><li>Die Rollen interagieren fließend miteinander</li><li>Das Programm bildet ein geschlossenes System mit gezielter Funktionalität</li></ul>|


## 4.2 Der Aufbau von ChickenApplication

Chicken Application ist als Java-Programm im Spring Framework realisiert, und dgrob in folgende Teile zerlegt:

- Klausurverwaltung
- Urlaubsverwaltung
- Kontrolle der Zugriffsrechte
- Auslieferung der Websites um mit der Software zu interagieren

Dank dieser Zerlegung ist die Änderung von Zugriffsrechten, so wie die Einführung neuer Bestandteile simpel und effizient.
Alle Teile sind durch Schnittstellen abstrahiert, die Implementierungen werden per Dependency Injection zusammengesteckt. Die Zerlegung erlaubt es weiterhin die Software, allen voran die Schachalgorithmen, leicht automatisiert zu testen.

Die Interaktion zwischen Algorithmen­Teilen erfolgt über den Austausch fachlich motivierter Datenstrukturen, realisiert als Klassen.

## 4.3 Die Anbindung

Die Anwendung wird alleinig über die Interaktion mit den Websites gesteuert, es findet keine Kontrolle oder Eingabe über die Konsole statt.

![Startseite aus Sicht eines Studenten](\img\Startseite.JPG)

Im Hintergrund werden die eingegebenen Daten verwaltet, während die Anwendung auch während Berechnungen im Hintergrund reaktiv bleibt und weiter nutzbar ist.
