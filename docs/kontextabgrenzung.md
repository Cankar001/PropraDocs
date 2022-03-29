---
sidebar_position: 4
sidebar_label: Kontextabgrenzung
---

# Kontextabgrenzung
Dieser Abschnitt beschreibt das Umfeld von DokChess. Für welche Benutzer ist es da, und mit welchen Fremdsystemen interagiert es?


## Fachlicher Kontext

### Student
Nach Anmeldung haben Studenten Zugriff auf ihren Urlaub, und eine Liste von Klausuranmeldungen.
Sie können beides selbst verwalten, haben aber keinen Exklusivzugriff.
Sie stellen die niedrigste Rolle dar.

### Tutoren
Die Tutor:innen haben die Aufgabe, die Anwesenheit der Teilnehmer:innen zu überprüfen. Dazu tragen sie ein, wenn Studierende fehlen. Die Anwendung soll Tutor:innen einen Überblick über die geplanten Fehlzeiten ermöglichen.

### Organisatoren
Die Organisator:innen müssen am Ende des Praktikums die Anwesenheit der Studierenden überprüfen. Die Anwendung soll daher eine Reporting-Funktion haben, die anzeigt, ob Studierende zu oft abwesend waren.

## Technischer Kontext

### Github OAuth
Die User melden sich per GitHub über die OAuth API an.

### HHU LSF
Die Authentifizierung für Klausuren erfolgt über das LSF der HHU anhand der Veranstaltungs-Ids.
