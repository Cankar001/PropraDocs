---
sidebar_position: 11
sidebar_label: Qualitätsanforderungen
---

# Qualitätsanforderungen

Die folgende Darstellung zeigt anhand eines Qualitätsbaumes einen Überblick über die relevanten Qualitätsmerkmale und nennt Beispiele, an welchen Stellen sie in der Anwendung erfüllt werden.

![Qualitätsbaum](\img\QualityTree.PNG)


## 10.2 Qualitätsszenarien

|ID|Szenario|
|--------------|:-----:|
|W01|Auch ohne Grundkenntnis über das Modul und den Ablauf des Universitätsalltags ist es innerhalb kurzer Zeit möglich, den Sinn der Anwendung so wie ihre interne Funktionalität zu verstehen|
|W02|Ein Erfahrener Entwickler möchte ein Beispiel für die Implementation eines Aggregats anschauen. Dank der Dokumentation und der kalren Struktur ist dies gezielt in wenigen Minuten möglich|
|W03|Eine neue Funktionalität (z.B. Events) soll eingefügt werden. Mit nur wenigen Änderung an bestimmten Klassen ist es problemfrei möglich, die Funktionalität zu integrieren|
|W04|Tutoren sollen nun vollen Zugriff auf alle Views haben. Mit nur wenigen Zeilen ist diese Änderung ohne Probleme einzufügen|
|K01|Ein Tutor benutzt die Anwendung in Edge, während ein Student die Anwensung in Brave benutzt. Die Anwendung ist problemfrei über beide Browser bedienbar.|
|F01|Ein Student versucht einen ungültigen, regelunkonformen Urlaub einzutragen. Die Anwendung erkennt dies, und verhindert den fehlerhaften Eintrag.|
|F02|Ein Student versucht eine Klausur zu erstellen, welche nicht existiert. Das Programm prüft vor der erstellung, ob die Klausur laut LSF wirklich existiert, und lehnt die Erstellung ggf. ab|
|F03|Ein Student fehlt unentschuldigt mehrere Male. Der Tutor kann darauf hin passenden Strafurlaub eintragen.|
|F04|Ein Student trägt ein, dass er eine Klausur innerhalb eines Praktikumtages schreibt. Die Anwundung kann unterscheiden, ob es sich um eine Präsenz- oder Onlineklausur handelt, und passt die Freistellung an|
|E01|Ein Nutzer ohne große Technikkenntnisse kann die Anwendung ohne Hilfe benutzen, da sie klar strukturiert und übersichtlich gehalten ist.|
|E02|Bei Klausureinreichungen und dem Eintragen von Urlaub, prüft die Anwendung automatisch die Gültigkeit, und die Kompatibilität mit anderen Eintragungen.|
|E03|Ein Student trägt Urlaub in einem Zeitraum ein, in welchem er für eine Klausur angemeldet ist. Die Anwendung passt den Urlaub automatisch auf die umliegende Freistellung an, um falsche Urlaubsabzüge zu vermeiden|
|P01|Das Modul wird umstrukturiert, es müssen nun auch Veranstaltungen berücksichtigt werden. Die Anpassungen sind klar strukturiert, und einfach vorzunehmen|
