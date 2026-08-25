---
title: Überwachen auf einen Ereignisknoten
description: Konfigurieren des Lauschens auf Ereignisknoten in Marketo Optimizer - Festlegen von Ereignisfiltern, Anwenden optionaler Trigger und Vorantreiben von Personen, wenn Aktivitäten oder Datenänderungen auftreten.
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 5%

---

# Überwachen eines Ereignisknotens

Fügen Sie den Knoten _Auf ein Ereignis warten_ hinzu, um Ihre Zielgruppe beim Eintreten eines Ereignisses zum nächsten Schritt auf dem Journey zu bewegen.

## Ereignis-Trigger {#event-triggers}

Sie können Trigger um [!DNL Marketo Engage] Aktivitäten herum erstellen, z. B.:

* Formular ausfüllen - Wird ausgelöst, wenn eine Person ein [!DNL Marketo Engage] Formular auf Ihrer Landingpage ausfüllt.
* Besuche Web-Seite - Wird ausgelöst, wenn ein Lead eine verfolgte Web-Seite anzeigt (Sie können exakte URLs angeben oder Platzhalter verwenden).
* Klicks auf Link - Wird ausgelöst, wenn auf einen verfolgten Link in einer Marketing-E-Mail geklickt wird.
* Änderungen der Datenwerte - Wird ausgelöst, wenn ein bestimmtes Feld (z. B. Lead-Status, Bewertung oder Branche) im Datensatz einer Person aktualisiert wird.
* Campaign wird angefordert - Wird häufig für API- oder Webhook-Integrationen verwendet, startet dieser Trigger eine Kampagne, wenn sie von einem anderen Programm oder Webservice aufgerufen wird.
* Bewertung wird geändert - Wird ausgelöst, wenn der Lead-Score eines Kontakts über einen bestimmten Schwellenwert hinaus ansteigt oder abnimmt.
* Mobile Push-Benachrichtigung getippt - Wird in Smart-Kampagnen für Mobile-Marketing ausgelöst, wenn auf einem Gerät mit einer Push-Benachrichtigung interagiert wird.

## Ereignisfilter {#event-filters}

| Filter | Beschreibung |
| ------- | ----------- |
| Aktivitätsverlauf > E-Mail | E-Mail-Aktivitäten basierend auf Bedingungen, die mithilfe einer oder mehrerer ausgewählter E-Mail-Nachrichten ausgewertet werden: <li>Link in E-Mail angeklickt <li>Hat E-Mail geöffnet |
| Aktivitätsverlauf > Datenwert geändert | Für ein ausgewähltes Personenattribut wurde ein Wert geändert. Zu diesen Änderungstypen gehören: <li>Neuer Wert <li>Vorheriger Wert <li>Grund <li>Quelle <li>Datum der Aktivität <li> Min. Häufigkeit |

## Ereignisknoten hinzufügen {#add-event-node}

1. Navigieren Sie zur Journey-Arbeitsfläche.

1. Klicken Sie auf das Pluszeichen ( **+** ) in einem Pfad und wählen Sie **[!UICONTROL Auf ein Ereignis überwachen]**.

   ![Klicken Sie auf das Symbol zum Hinzufügen auf dem Journey-Pfad](./assets/person-journey-canvas-add-node.png){width="200"}

1. Klicken Sie in den Knoteneigenschaften auf der rechten Seite **[!UICONTROL Ereigniskriterien hinzufügen]**.

1. Fügen Sie im _[!UICONTROL Ereignis bearbeiten]_ die Ereignisse zum Trigger hinzu.

   ![Ereignis bearbeiten - Ereignis-Trigger ](./assets/edit-event-triggers.png){width="600" zoomable="yes"}

1. (Optional) Wählen Sie **[!UICONTROL Dialogfeld die Registerkarte]** Filter“ aus und fügen Sie Filterkriterien für die Trigger hinzu.

1. Klicken Sie **[!UICONTROL Ereignis bearbeiten]** und definieren Sie Details für das Ereignis.

   ![Ereignis bearbeiten - Ereignisfilterung](./assets/edit-event-filters.png){width="600" zoomable="yes"}

1. Klicken Sie auf **[!UICONTROL Speichern]**.

<!--
1. If needed, set the **[!UICONTROL Timeout]** option to limit the time period to listen for the event.

   >[!NOTE]
   >
   >The journey ends after a timeout unless you define a timeout path, where you can add other nodes.

   Enable the **[!UICONTROL Timeout]** option and select the duration for which the journey waits for an event to occur before it times out.

   You can choose to end the path here or take a different course of action by setting another path. To create a new path in the journey where you can add actions and events applicable to accounts when the event does not occur, select the **[!UICONTROL Set timeout path]** check box.

   ![Journey event node - set timeout path](assets/node-event-timeout-set-path.png){width="700" zoomable="yes"}
-->

>[!NOTE]
>
>Die Zeitüberschreitungsfunktion für das Überwachen eines Ereignisknotens funktioniert derzeit nicht. Es ist für eine spätere Version geplant.

