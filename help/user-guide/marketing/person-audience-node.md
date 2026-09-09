---
title: Zielgruppen-Journey-Knoten für Person
description: Konfigurieren Sie den Zielgruppenknoten Person in Journey Optimizer B2B, um mithilfe von dynamischen Personenlisten oder ereignisbasierten Zielgruppen anzugeben, welche Profile auf eine Journey zugreifen.
TQID: 'https://experienceleague.adobe.com/WqM-yLPadt6lBFtqJOGUxDtk0fm6n6S29wQTRSWB8fY'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 46e599c6-e20f-5f67-9824-93415016f66bid: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 215
ht-degree: 0%

---

# Zielgruppenknoten Person

Der _Personen-Zielgruppe_-Knoten gibt an, welche Personenprofile in die Journey eintreten. Wenn Sie [Personen-Journey erstellen](./person-journeys.md) beginnt die Journey immer mit einem Personen-Zielgruppenknoten, der die Eingabe definiert. Der Zielgruppenknoten Person kann einen von zwei Zielgruppen-Eingabetypen aufweisen: eine Liste dynamischer Personen oder einen Ereignis-Trigger.

Wenn die dynamische Personenliste, die Sie für den Personen-Journey benötigen, nicht bereits vorhanden ist, erstellen [ die Personenliste ](../audiences/people-lists.md#create-a-people-list) konfigurieren Sie dann den Zielgruppenknoten Person .

_So konfigurieren Sie die Journey-Zielgruppe :_

1. Klicken Sie auf **[!UICONTROL Knoten]** Zielgruppe“.

   Diese Aktion zeigt die Knoteneigenschaften rechts an.

   ![Zielgruppen-Journey-Knoten für Person](./assets/person-audience-node-properties.png){width="600" zoomable="yes"}

1. Verwenden Sie eine der folgenden Zielgruppen-Konfigurationsoptionen für die Zielgruppe der Person:

   * **[!UICONTROL Dynamische Liste]** - Verwenden Sie eine dynamische, regelbasierte Personenliste. Die Listenregeln werden zur Journey-Laufzeit ausgewertet, um Mitglieder der Journey zu qualifizieren. Personen, die sich zu einem späteren Zeitpunkt für die dynamische Liste disqualifizieren, werden nicht von der Journey entfernt. Siehe _[Dynamische](../audiences/people-lists.md#dynamic-lists)_.

   * **[!UICONTROL Ereigniszielgruppe]** - Verwenden Sie eine Ereigniszielgruppe, um die Journey-Zielgruppe basierend auf qualifizierten Ereignissen zu definieren. Definieren Sie Zielgruppenmitglieder mithilfe der Personenprofilfilterung und des Trigger-Journey-Eintrags mithilfe von Ereigniskriterien. Siehe _[Ereignisbasierte Zielgruppen](../audiences/event-based-audiences.md)_.