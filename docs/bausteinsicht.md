---
sidebar_position: 6
sidebar_label: Bausteinsicht
---

# Bausteinsicht

Dieser Abschnitt zeigt den Internen Aufbau der einzelnen Komponenten und Aggregate der ChickenApplication Anwendung. Die Application ist in 3 große Aggregate aufgeteilt, welche wiederrum in klare Strukturen zerlegt sind.

Die Aggregate und ihre Bestandteile werden im folgenden detailliert erklärt, und anhand von Diagrammen dargelegt.

## 5.1 Bausteine

Im der folgenden Grafik ist eine Übersicht aller Bausteine zu sehen, aus welchen die Applikation besteht.

<img src="/img/OnionJens.png" alt="Diagramm der Rollen" />

|Qualitätsziel|Dem zuträgliche Ansätze in der Architektur|
|--------------|:-----:|
|Controller|Die Controller steuern die Auslieferung der HTML Templates.|
|Aggregate|Die Aggregate bilden Codestrukturen, welche durch die Unabhängigkeit ihrer Zustände definiert werden.|
|Repositories|Die Repositories sind verantwortlich für die Datenbank und geben eine Vorlage der zu implementierenden Funktionen für die Datenbank vor.|

Die folgende Ansicht und Beschreibung soll einen groben überblick über die Bausteine der Architektur bieten, und deren Rolle in der Architektur der Anwendung darstellen.
Genauere technische Details werden in Kapitel 8 beschrieben.


