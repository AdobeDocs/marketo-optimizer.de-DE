---
title: Person Journey Individual Report
description: Erfahren Sie mehr über den individuellen Bericht zum Personen-Journey in Adobe Marketo Optimizer, der Fertigstellungs-, Interaktions- und E-Mail-Metriken für eine Journey anzeigt.
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
source-git-commit: 531dce4ffe6000efa0296f0e2393423f54124ea7
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 0%
---

# Person Journey Individual Report

<!-- SPHR-39120: UX plans to move the Journey activity flow tile to the top of the report. Update the tile order in this page when that ships. -->

Klicken Sie **[!UICONTROL Bericht anzeigen]**, um eine Live- oder abgeschlossene Personen-Journey anzuzeigen, deren Leistung einschließlich Status, Interaktion, E-Mail-Metriken und Aktivitätsfluss.

_Bericht anzeigen :_

1. Öffnen Sie eine **[!UICONTROL Live]**- oder **[!UICONTROL Finished]**-Personen-Journey aus der Liste _[!UICONTROL Personen-Journey]_.
1. Wählen Sie in der Journey-Kopfzeile **[!UICONTROL Bericht anzeigen]**.

   ![Personen-Journey-Arbeitsfläche mit hervorgehobener Schaltfläche „Bericht anzeigen“ in der Journey-Kopfzeile.](./assets/reports-person-journey-view-report.png){width="600" zoomable="yes"}

Sie können [ Datumsbereich für ](./reports-overview.md#change-the-date-range) Bericht ändern.

Wählen **[!UICONTROL oben]** Bericht „Freigeben“ aus, um die Daten herunterzuladen oder ihren Export zu planen. Siehe [_Exportieren eines Berichts_](./reports-overview.md#export-a-report) in der Übersicht über Berichte.

![Individueller Bericht zum Personen-Journey mit Journey-Status, Abschlusstrend und Interaktionskacheln.](./assets/reports-individual-journey.png){width="700" zoomable="yes"}

## Filter {#filters}

Die Berichtsfilter beziehen sich auf die aktuelle Journey.

* **[!UICONTROL Journey-Name (Ereignis)]** - Legen Sie die Voreinstellung auf die Journey fest, von der aus Sie den Bericht geöffnet haben.
* **[!UICONTROL Persona (Ereignis)]** - (_noch nicht unterstützt_) Filtern Sie den Bericht nach Personen, die einer bestimmten [abgeleiteten Persona) ](../audiences/personas.md#filter-by-derived-persona). Der Standardwert lautet [!UICONTROL Kein Filter].

Wählen Sie **[!UICONTROL Alle zurücksetzen]** aus, um den Filter _[!UICONTROL Persona (Ereignis)]_ zu löschen und zur Standardansicht zurückzukehren.

## Personenstatus und Interaktion {#person-status-and-engagement}

Dieser Abschnitt enthält vier Kacheln:

* **[!UICONTROL Personenstatus auf der Journey]** - Unterteilt Personen auf der Journey in _[!UICONTROL Abgeschlossen]_ und _[!UICONTROL In Bearbeitung]_ mit entsprechenden Prozentsätzen.
* **[!UICONTROL Abgeschlossene Personen im Zeitverlauf]** - Ein Liniendiagramm, das die Anzahl der Personen verfolgt, die die Journey im ausgewählten Datumsbereich abgeschlossen haben.
* **[!UICONTROL Eingeladene vs. nicht]** Personen: Schlüsselt Personen auf der Journey in _[!UICONTROL Eingeladene]_ und _[!UICONTROL Nicht eingestellt]_-Kategorien mit entsprechenden Prozentsätzen auf.
* **[!UICONTROL Engagierte Personen]** - Die Gesamtzahl der Personen, die sich als an der Journey beteiligt qualifizieren.

## E-Mail-Leistung {#email-performance}

Die [!UICONTROL E-Mail]Leistung) zeigt Versand- und Interaktionsmetriken für jede auf der Journey gesendete E-Mail an. Dieselben E-Mail-Metriken für alle Journey finden Sie im [E-Mail-Interaktionsbericht](./email-engagement-report.md).

![E-Mail-Leistungstabelle mit Metriken für gesendete, zugestellte, geöffnete und angeklickte E-Mails.](./assets/reports-individual-journey-email-performance.png){width="700" zoomable="yes"}

[!UICONTROL E-Mail]Leistung) Tabellenspalten:

* [!UICONTROL Email Name] - Name der E-Mail.
* [!UICONTROL Gesendet] - Anzahl der gesendeten E-Mails.
* [!UICONTROL Zugestellt] - Anzahl der zugestellten E-Mails.
* [!UICONTROL  % Zugestellt] - Anzahl der zugestellten E-Mails dividiert durch die Anzahl der gesendeten Nachrichten.
* [!UICONTROL Geöffnet] - Anzahl der Öffnungen der E-Mail durch Empfänger.
* [!UICONTROL  % geöffnet] - Anzahl der geöffneten E-Mails dividiert durch die Anzahl der zugestellten Nachrichten.
* [!UICONTROL geklickt] - Anzahl der Klicks auf einen Link in der E-Mail.
* [!UICONTROL  % angeklickt] - Anzahl der angeklickten E-Mails dividiert durch die Anzahl der zugestellten Nachrichten.

## Journey-Aktivitätsfluss {#journey-activity-flow}

Die Visualisierung des [!UICONTROL Journey]Aktivitätsflusses zeigt den Pfad, den Personen durch den Journey gehen, beginnend mit der Aktivität _[!UICONTROL Person zum Journey hinzufügen]_. Jeder Knoten zeigt die Anzahl der Pfadansichten für diese Aktivität an.

![Visualisierung des Journey-Aktivitätsflusses mit Pfadansichten von Person zu Journey hinzufügen über den E-Mail-Versand.](./assets/reports-individual-journey-activity-flow.png){width="700" zoomable="yes"}
