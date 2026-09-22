---
title: Erstellen von Analytics-Berichten
description: Erfahren Sie, wie Sie im Coworker Chat die Fähigkeit Surface Analytics verwenden können, Aktivitäts-, E-Mail-, Lead-, Segment- und Journey-Berichte über Eingabeaufforderungen in natürlicher Sprache zu generieren.
autotag-review: '2026-09-21T14:58:26.479Z'
TQID: 'https://experienceleague.adobe.com/BSDEihjdpz-YZjMWrYTmIuyjqtcjRHRrJdz4xPFZbHU'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 1650dadf-b034-5ac9-a309-77ad1e2f5035
    internal-label: Chat Interface
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
subfeature_v2:
  - id: b9e5c7f3-be30-563c-9e41-cc8ea76e2fee
    internal-label: Skills
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: 1dcc3bcdc59114c7fc1e16178db8921ae173b955
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%
---
# Erstellen von Analyseberichten

Die [_Surface Analytics_-](./skills.md#analytics-reporting) in [!DNL Adobe Marketo Optimizer] beantwortet Fragen zur natürlichen Sprache Ihrer Daten. Verwenden Sie ihn in der [Coworker chat](./chat-interface.md)-Oberfläche, um Aktivitätstrends, E-Mail-Leistung, Lead- und Kontodaten, Segment- und Listenmitgliedschaft und Journey-Metriken zu untersuchen. Die Ergebnisse werden als Diagramme und Tabellen zurückgegeben, sodass Sie keine Abfrage oder kein Dashboard manuell erstellen müssen.

* **Kenntnisse** - `surface-analytics`
* **Aufruf** - Stellen Sie eine Frage in natürlicher Sprache oder verwenden Sie einen Schrägstrich, um die Surface Analytics-Fähigkeit auszuführen. Beispiel: _„Anzeigen der täglichen Aktivitätsanzahl für die letzten 30 Tage.“_
* **Liest aus** - [!DNL Marketo Optimizer] Analysedaten; liest [!DNL Marketo Engage] Analysedaten für Fragen, die beide Produkte betreffen

>[!NOTE]
>
>Berichtsdaten werden alle zwei Stunden aktualisiert. Die Ergebnisse spiegeln möglicherweise nicht die Aktivität der letzten zwei Stunden wider.

## Aktivitätstrends anzeigen {#activity-trends}

Fragen Sie nach der täglichen oder wöchentlichen Aktivitätsanzahl und schlüsseln Sie die Ergebnisse nach Aktivitätstyp oder Produktbereich auf.

* _„Anzeigen der täglichen Aktivitätsanzahl für die letzten 30 Tage.“_
* _„Was sind die Top-Aktivitätstypen in dieser Woche?“_
* _„Aufschlüsselung der Aktivitäten des letzten Monats nach App-Bereich.“_

## E-Mail-Leistung überprüfen {#email-performance}

Fragen Sie nach dem Versandvolumen, den Öffnungs- und Klickraten, Bounces und Abmeldungen für Ihre E-Mail-Programme.

* _„Wie hoch ist die E-Mail-Öffnungsrate nach Journey?“_
* _„Klickraten der letzten 90 Tage anzeigen._
* _„Wie viele Abmeldungen haben wir letzte Woche erhalten?“_

## Lead- und Kontodaten analysieren {#lead-account-data}

Fragen zur Verteilung der Lead-Punktzahl, zur Aufschlüsselung der Rollen und zu geografischen oder firmografischen Rollups.

* _„Zeigen Sie mir die Verteilung der Punktzahl auf die Leads.“_
* _„Wie viele Personen befinden sich in jedem Account?“_
* _„Schlüsseln Sie Leads nach Persona auf.“_

## Segment- und Listenmitgliedschaft überprüfen {#segment-list-membership}

Fragen Sie, wer zu einer bestimmten Liste oder einem bestimmten Segment gehört.

* _„Wie viele Personen sind in der Q1 Nurture-Liste?“_
* _„Welches Segment hat die meisten Mitglieder?“_

## Erkunden von Journey-Metriken {#journey-metrics}

Fragen Sie nach der Journey-Mitgliedschaft, Abschlussraten, Knotendurchlauf und funnel-Analyse.

* _„Wie hoch ist die Abschlussrate der Demo-Follow-up-Journey?“_
* _„Wie viele Personen befinden sich in jedem Knoten der LeadNurtureJourney?“_

## Stellen von Fragen über Produkte hinweg {#cross-product}

Surface Analytics kann Fragen, die sowohl [!DNL Marketo Engage]- als auch [!DNL Marketo Optimizer] Daten umfassen, in einer einzigen Eingabeaufforderung beantworten.

* _„Was ist meine leistungsstärkste E-Mail in LumaSecure und in LumaStorage?“_

## Einschränkungen {#limitations}

| Einschränkung | Detail |
|---|---|
| Bearbeiten oder Erstellen von Datensätzen | Nicht unterstützt. Surface Analytics liest und berichtet nur über vorhandene Daten. |
| Lesbare Namen in den Ergebnissen | Nicht immer verfügbar. Einige Berichte zeigen eine interne ID an, wie z. B. eine Journey- oder E-Mail-ID, anstatt eines Namens. |
| Duplizieren von Berichtskarten | Eine einzelne Frage kann gelegentlich mehr als eine Berichtskarte für dasselbe Ergebnis zurückgeben. |
