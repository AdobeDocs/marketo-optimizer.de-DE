---
title: Überwachen und Debuggen des Journey-Fortschritts
description: Erfahren Sie, wie Sie die Journey-Observability-Qualifikation im Coworker chat verwenden, um zu debuggen und zu überwachen, wie sich Personen und Leads durch Journeys, Entscheidungen über Teilpfade und Timing bewegen.
TQID: 'https://experienceleague.adobe.com/Pnd1fVWUZ-g27UDE-y6Pc2Qwjsx-1pDSCaTGxjrBTRc'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 1650dadf-b034-5ac9-a309-77ad1e2f5035id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 634
ht-degree: 0%

---

# Überwachen und Debuggen des Journey-Fortschritts

Die [_Journey Observability_ SKILL](./skills.md#journeys) in [!DNL Adobe Marketo Optimizer] beantwortet Fragen in natürlicher Sprache darüber, wie sich Menschen und Leads durch Journey bewegen. Verwenden Sie ihn in der [Coworker chat](./chat-interface.md)-Oberfläche, um den Fortschritt zu verfolgen, Split-Path-Entscheidungen zu verstehen, Personen innerhalb von Journey-Knoten zu analysieren und Timing-Metriken zu überprüfen. Sie können auch nach Verhaltensmustern bei Journeys fragen.

* **Kenntnisse** - `journey-observability`
* **Aufruf** - Stellen Sie eine Frage in natürlicher Sprache oder verwenden Sie einen Schrägstrich, um die Journey-Beobachtungsfähigkeiten auszuführen. Beispiel: _„Wie ist demo_ lead_24@company.com durch die LeadNurtureJourney gekommen?“_
* **Liest aus** - [!DNL Marketo Optimizer] Journey-Daten; liest [!DNL Marketo Engage] statischen Listen, um die Mitgliedschaft in der Liste zu überprüfen

## Personen- oder Lead-Details anzeigen {#person-details}

Fragen Sie nach grundlegenden, schreibgeschützten Details zu einer Person oder einem Lead, um einen Kontext herzustellen, bevor Sie deren Journey untersuchen. Geben Sie die E-Mail-Adresse, Lead-ID oder den Lead-Namen der Person an.

* _„Gib mir grundlegende Informationen über Lead demo_ lead_24@company.com.“_
* _„Was ist die Stellenbezeichnung und das Land für Profil john.doe@company.com?“_
* _„Zeigen Sie mir die E-Mail-Adresse und die Rolle für lead_ 01.“_

## Fortschritt durch einen Journey verfolgen {#journey-progression}

Fragen Sie, wie sich eine Person oder ein Lead durch einen Journey bewegt hat, um den Einstieg, den Austritt, die Dauer und den Pfad auf Knotenebene anzuzeigen. Geben Sie die E-Mail-Adresse oder Lead-ID der Person und den Journey-Namen an.

* _„Wie kam demo_ lead_24@company.com durch die LeadNurtureJourney?“_
* _„Welche Knoten hat john.doe@company.com in der Produkt-Demo-Journey durchlaufen?“_

## Entscheidungen über Teilungspfade verstehen {#split-path-analysis}

Frage, warum eine Person oder ein Lead einen bestimmten Pfad an einem aufgeteilten Knoten verwendet hat oder nicht. Journey Observability erklärt die Entscheidung anhand der zu diesem Zeitpunkt ausgewerteten Attributwerte. Geben Sie die E-Mail-Adresse oder Lead-ID der Person, den Journey-Namen und die ID des Aufspaltungsknotens an.

* _„Warum ist demo_ lead_24@company.com auf den Pfad „Starke Interaktion“ am Split-Knoten c764a9 gegangen?“_
* _„Warum hat john.doe@company.com den qualifizierten Pfad auf dem Knoten ab123f in LeadNurtureJourney nicht verwendet?“_
* _„Vergleichen Sie, warum lead_ 01 und lead_02 unterschiedliche Pfade bei Split-Knoten x99f3b gewählt haben.“_

## Analysieren von Personen in Journey-Knoten {#node-analysis}

Fragen Sie nach Personen- oder Lead-Zahlen und Details in einem Journey-Knoten oder Aufspaltungspfad. Filtern Sie Ergebnisse nach Persona, Rolle, Standort oder Interaktionsstufe. Geben Sie die Knoten-ID an.

* _„Geben Sie mir alle Personen, die sich derzeit im „High Engagement“-Pfad des Node-459c7c befinden.“_
* _„Wie viele Leads befinden sich im Qualifizierungsknoten der Demo Nurture Journey?“_
* _„Anzeigen von Leads im Aufspaltungspfad „Geringe Absicht“, gefiltert nach Rolle: Marketing-Manager.“_

## Identifizieren von Mustern in allen Journeys {#pattern-recognition}

Bitten Sie die Journey-Observability, häufige Pfade, Abfallpunkte und wiederholte Verhaltensweisen auf einer Journey zu identifizieren. Geben Sie den Journey-Namen und optional einen Zeitrahmen, eine Rolle, ein Produkt oder ein Konto an, um die Ergebnisse einzugrenzen.

* _„Was sind die häufigsten Pfade von SDRs auf der Produkt-Demo-Journey?“_
* _„Wo werden Leads in der Regel in der LeadNurtureJourney abgelegt?“_
* _„Gibt es ungewöhnliche Verzögerungen oder unerwartete Pfade in der Q1 Nurture Journey?“_

## Zeitliche und operative Metriken überprüfen {#operational-metrics}

Fragen Sie nach Einstiegszeiten, Wartezeiten, Übergangslatenz und angehaltenem Fortschritt für eine Journey. Geben Sie den Journey-Namen und optional eine Knoten-ID oder Personenkennung an.

* _„Wann ist john.doe@company.com auf die Demo-Follow-up-Journey gekommen?“_
* _„Wie lange warten Leads normalerweise am Qualifizierungsknoten in LeadNurtureJourney?“_
* _„Welche Leads sind seit mehr als sieben Tagen auf der Demo-Follow-up-Journey blockiert?“_

## Einschränkungen {#limitations}

| Einschränkung | Detail |
|---|---|
| Personen- oder Lead-Attribute bearbeiten | Nicht unterstützt. Personen- und Lead-Datensätze direkt in [!DNL Marketo Engage] oder [!DNL Marketo Optimizer] aktualisieren. |
| Erstellen, Bearbeiten, Pausieren oder Fortsetzen von Journeys | Nicht unterstützt. Verwenden Sie stattdessen die [Journey](../marketing/person-journeys.md)Arbeitsfläche oder eine Journey-Bearbeitungsfunktion in [Kollegen-](./skills.md#journeys). |
| Ändern der Split-Logik oder der Journey-Konfiguration | Nicht unterstützt. Aufspaltungspfade direkt auf der [Journey-Arbeitsfläche bearbeiten](../marketing/split-merge-paths-nodes.md). |
| Zusammensetzung der Einkaufsgruppe oder Datenaggregationen auf Kontoebene | Außerhalb des Bereichs. Journey-Beobachtungsberichte nur auf Personen- und Lead-Ebene. |
| Ändern von Journey-Zeitplänen oder -Zeiten | Nicht unterstützt. |
