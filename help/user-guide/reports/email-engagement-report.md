---
title: Email Engagement Report
description: Erfahren Sie mehr über den E-Mail-Interaktionsbericht in Adobe Marketo Optimizer, der E-Mail-Zustellbarkeit und Interaktionsmetriken nach E-Mail und Journey anzeigt.
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
source-git-commit: 8c47a9c69c32ba0a37ba2efadb6ad4c1b796c21d
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 1%
---

# Email Engagement Report

<!-- SPHR-39569: content drafted, but hide: true and hide-from-toc stay until eng confirms this shipped to production. Filter by Program, Filter by Audience, and the program data point from SPHR-32511 are not documented here pending delivery-state confirmation. -->

Verwenden Sie den Bericht [!UICONTROL E-Mail]Interaktion), um die Zustellbarkeit der E-Mails und die Interaktionsleistung in Ihrer gesamten Instanz zu überprüfen, aufgeschlüsselt nach E-Mail und Journey.

_Bericht anzeigen :_

1. Wählen Sie in der linken Navigationsleiste die Option **[!UICONTROL Berichte]**.
1. Klicken Sie auf _Listen_-Symbol ( ![Listen-Symbol](../assets/do-not-localize/icon-table-of-contents.svg) ) und wählen Sie **[!UICONTROL E-Mail-]** im Bedienfeld _[!UICONTROL Inhaltsverzeichnis]_ aus.

![E-Mail-Interaktionsbericht mit Journey-Name- und Persona-Filtern, einem Datumsbereich der letzten 30 Tage und einer Tabelle mit E-Mail-Aktivitätsmetriken.](./assets/reports-email-engagement.png){width="700" zoomable="yes"}

Sie können [&#x200B; Datumsbereich ändern](./reports-overview.md#change-the-date-range) indem Sie dieselbe Datumsbereichsauswahl verwenden, die in anderen Berichtsabschnitten verfügbar ist.

Wählen **[!UICONTROL oben]** Bericht die Option „Freigeben“ aus, um den Export aller Berichtsdaten herunterzuladen oder zu planen. Siehe [_Exportieren eines Berichts_](./reports-overview.md#export-a-report) in der Übersicht über Berichte.

## Berichtstabelle {#report-table}

Der [!UICONTROL E-Mail]Interaktionsbericht zeigt für jede E-Mail eine Zeile mit den folgenden Zeilendimensionen an.

* **[!UICONTROL Email Name]** - Der Name der E-Mail.
* **[!UICONTROL Journey-Name]** - Der Name der Journey, die die E-Mail gesendet hat.

Metrikspalten sind unter **[!UICONTROL E-Mail-Aktivitäten]** gruppiert.

| Spalte | Beschreibung |
| --- | --- |
| [!UICONTROL gesendet] | Anzahl der gesendeten E-Mails. |
| [!UICONTROL Zugestellt] | Anzahl der zugestellten E-Mails. |
| [!UICONTROL &#x200B; % Zugestellt] | Prozentsatz der gesendeten E-Mails, die zugestellt wurden |
| [!UICONTROL Hardbounce] | Anzahl der E-Mails, die dauerhaft nicht zugestellt werden konnten. |
| [!UICONTROL Softbounce] | Anzahl der E-Mails, die vorübergehend nicht zugestellt werden konnten. |
| [!UICONTROL Geöffnet] | Anzahl der Öffnungen der E-Mail durch Empfänger. |
| [!UICONTROL &#x200B; % geöffnet] | Prozentsatz der zugestellten E-Mails, die geöffnet wurden. |
| [!UICONTROL angeklickt] | Anzahl der Klicks von Empfängern auf einen Link in der E-Mail. |
| [!UICONTROL &#x200B; % angeklickt] | Prozentsatz der zugestellten E-Mails, die einen Klick erhalten haben |
| [!UICONTROL Klick-zum-Öffnen-Verhältnis] | Prozentsatz der geöffneten E-Mails, die einen Klick erhalten haben |
| [!UICONTROL Abo storniert] | Die Anzahl der Empfänger, die sich von der E-Mail abgemeldet haben. |
| [!UICONTROL % abgemeldet] | Prozentsatz der zugestellten E-Mails, die zu einer Abmeldung führten. |

<!--

## Filters {#filters}

Use filters to narrow the report to a specific journey, persona, or date range. Select **[!UICONTROL Reset all]** to clear every filter and return to the default view.

* **[!UICONTROL Journey Name (Event)]** - Filter by the journey that sent the email. Default is [!UICONTROL No filter].
* **[!UICONTROL Persona (Event)]** - Filter by the persona associated with the email. Default is [!UICONTROL No filter].
* **[!UICONTROL Date range]** - Filter by a specific date span, shown as explicit start and end dates. Default is [!UICONTROL Last 30 days].
-->