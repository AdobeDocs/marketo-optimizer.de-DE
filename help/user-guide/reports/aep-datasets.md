---
title: Experience Platform-Datensätze
description: Erfahren Sie mehr über die Datensätze, die Marketo Optimizer in Adobe Experience Platform schreibt, um Customer Journey Analytics-Berichte und Ad-hoc-Abfragen zu unterstützen.
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
source-git-commit: 1ebb0036699252c50f33ba6c0f4a56e8e670aacd
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 4%
---

# Experience Platform-Datensätze

[!DNL Adobe Marketo Optimizer] repliziert Lead-, Journey- und Aktivitätsdaten in [!DNL Adobe Experience Platform]. Diese Datensätze unterstützen die [!UICONTROL Berichte] und das eingebettete [!DNL Adobe Customer Journey Analytics]. Sie können sie auch direkt mit [!DNL Query Service] für Ad-hoc-Analysen abfragen.

Die Datensätze werden vom System verwaltet. Eine Verbindung in [!DNL Customer Journey Analytics] verknüpft sie mit der Datenansicht, die [!DNL Marketo Optimizer] Berichte verwenden, sodass Sie diese Verbindung nicht selbst erstellen müssen. Diese Verbindung ist dieselbe, die Sie erreichen, wenn Sie **[!UICONTROL Analysieren in CJA]** in einem Berichtsabschnitt auswählen. Siehe [Analysebericht in Customer Journey Analytics](./reports-overview.md#analyze-a-report-in-cja).

## Verfügbare Datensätze {#available-datasets}

Die folgenden Datensätze werden für jede [!DNL Marketo Optimizer]-Instanz ausgefüllt.

>[!NOTE]
>
>Jeder Datensatzname verwendet das Präfix `AJOB2B` , das den Systemnamen für [!DNL Marketo Optimizer] angibt. Dieses Verhalten ist zu erwarten, und Sie können diese Namen verwenden, um die Datensätze in Ihrer [!DNL Experience Platform] Sandbox zu finden.

| Datensatz | Schema | Beschreibung |
| --- | --- | --- |
| `AJOB2B - Person` | Person | Standard-Lead-Attribute. |
| `AJOB2B - PersonActivity` | Personenaktivität | Aktivitätsereignisse, die mit einer Person verbunden sind. |
| `AJOB2B - PersonActivityType` | Aktivitätstyp der Person | Mit einer Person verknüpfte Aktivitätstypen. |
| `AJOB2B - PersonActivityTypeEngagementMapping` | Interaktionszuordnung für Personenaktivitätstyp | Ordnet Aktivitätstypen ihrer Interaktionsklassifizierung, ihrem Kanalereignis und ihrer Ausrichtung zu. |
| `AJOB2B - Journey` | Journey | Liste der Journey und ihrer Lebenszyklus-Metadaten. |
| `AJOB2B - JourneyNode` | Journey-Knoten | Liste der Knoten auf einer Journey und der zugehörigen Metadaten. |
| `AJOB2B - EngagementAsset` | Interaktions-Asset | Einheitliche Suche nach Interaktions-Asset-IDs und Anzeigenamen für alle Interaktions-Asset-Typen. |

## Abfragen von Datensätzen mit dem Abfrage-Service {#query-service}

Verwenden Sie [!DNL Query Service], um Ad-hoc-SQL-Abfragen für diese Datensätze auszuführen, wenn Sie Analysen außerhalb [!DNL Customer Journey Analytics] Berichte benötigen. Der Abfragezugriff erfordert die entsprechenden [!DNL Experience Platform] für Ihre Sandbox. Allgemeine Informationen zur Syntax und Einrichtung von Abfragen finden Sie unter [Abfrage-Service](https://experienceleague.adobe.com/de/docs/experience-platform/query/home){target="_blank"}.

![Der Abfrage-Service-Editor zeigt eine SELECT-Abfrage für den Datensatz ajob2b_Journey und eine Tabelle der resultierenden Journey-Einträge.](./assets/aep-query-service.png){width="800" zoomable="yes"}

>[!NOTE]
>
>Diese Datensätze sind schreibgeschützt. Um zu ändern, welche Daten [!DNL Marketo Optimizer] erfasst, aktualisieren Sie die Quelldaten in [!DNL Marketo Optimizer] oder [!DNL Marketo Engage], anstatt einen Datensatz direkt zu bearbeiten.
