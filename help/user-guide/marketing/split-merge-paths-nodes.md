---
title: Aufspalten und Zusammenführen von Pfadknoten
description: Erfahren Sie, wie Sie mithilfe von Knotenpunkten für Aufspaltungs- und Zusammenführungspfade in Personen-Journeys Personen basierend auf definierten Bedingungen in verschiedene Pfade segmentieren und dann an einem gemeinsamen, nachgelagerten Punkt zusammenführen können.
TQID: 'https://experienceleague.adobe.com/XMN7lgb77bFlJkNXrmPf9ZSCV-GgIuybtr-O3AsqT2U'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
source-git-commit: bc370a501d3f8ff80ad846576b62504aca77f530
workflow-type: tm+mt
source-wordcount: '1083'
ht-degree: 2%
---
# Aufspalten und Zusammenführen von Pfadknoten

Verwenden Sie Split-Pfade und Merge-Pfade in Personen-Journeys, um Personen basierend auf von Ihnen definierten Bedingungen in verschiedene Pfade zu segmentieren, und führen Sie diese Pfade dann zusammen, damit die Journey fortgesetzt werden kann. Mit Pfaden für die Aufspaltung können Sie Aktionen und Ereignisse an bestimmte Zielgruppensegmente anpassen, während Pfade zum Zusammenführen diese Segmente an einem gemeinsamen Punkt kombinieren.

## Pfade von Knoten teilen

Verwenden Sie geteilte Knoten, um Personen entsprechend den von Ihnen definierten Bedingungen zu segmentieren. Erstellen Sie Pfade für die Audience-Liste gemäß Bedingungen, definieren Sie jeden Pfad mit Aktions- und Ereignisknoten für das Segment, kombinieren Sie dann die Pfade und setzen Sie das Journey fort.

Ein Knoten für aufgeteilte Pfade definiert einen oder mehrere segmentierte Pfade, die auf Personenfiltern basieren.

<!-- A split based on a people filter is automatically closed with a merge paths node so that all people can move forward to the next step. Split by people paths can include only people actions. These paths cannot be split again and automatically join back. _not currently true_ -->

_**Funktion eines Knotens mit aufgeteiltem Pfad**_

* Die Auswertung jedes Pfads erfolgt von oben nach unten. Wenn eine Person dem ersten und zweiten Pfad entspricht, fährt sie nur auf dem ersten Pfad fort.
* Der Knoten unterstützt die Definition eines Pfads _Andere Personen_, in dem Sie Aktionen oder Ereignisse für Personen hinzufügen können, die nicht mit einem der definierten Segmente/Pfade übereinstimmen.

### Filter für übereinstimmende Personen

Verwenden Sie für jeden Pfad, den Sie für den Knoten definieren, die folgenden Filtertypen, um Personen entsprechend einer oder mehreren Bedingungen abzugleichen.

| Filter | Beschreibung |
| ------- | ----------- |
| Aktivitätsverlauf | Aktivitäten basierend auf Bedingungen, die anhand eines oder mehrerer ausgewählter Elemente ausgewertet werden |
| Brand Concierge | Aktivitäten für mit [!DNL Brand Concierge] interagierende Leads. |
| Unternehmensattribute | Attribute aus dem Firmen-/Kontoprofil, einschließlich: <li>[!UICONTROL Jahresumsatz] <li>[!UICONTROL Firmenname] <li>[!UICONTROL Rechnungsland] <li>[!UICONTROL Branche] <li>[!UICONTROL Anzahl Mitarbeiter] <li>[!UICONTROL SIC-Code] <li>[!UICONTROL state] |
| Absichtsdaten | Attribute, die auf den mit dem Personenprofil verknüpften Absichtsdaten basieren. |
| Opportunitys | Status und Attribute basierend auf den mit dem Personenprofil verbundenen Opportunitys, einschließlich: <li>[!UICONTROL Hat Gelegenheit] <li>[!UICONTROL Anzahl der Opportunitys] <li>[!UICONTROL Opportunity-Gesamtbetrag] <li>[!UICONTROL Wurde der Opportunity hinzugefügt] <li>[!UICONTROL Wurde von der Opportunity entfernt] |
| Personenattribute | Attribute aus dem B2B-Personenprofil, einschließlich: <li>[!UICONTROL Stadt] <li>[!UICONTROL Land] <li>[!UICONTROL Geburtsdatum] <li>[!UICONTROL E-Mail-Adresse] <li>[!UICONTROL E-Mail ungültig] <li>[!UICONTROL E-Mail ausgesetzt] <li>[!UICONTROL Vorname] <li>[!UICONTROL Abgeleitete Statusregion] <li>[!UICONTROL Stellenbezeichnung] <li>[!UICONTROL Nachname] <li>[!UICONTROL Mobiltelefonnummer] <li>[!UICONTROL Personen-Interaktionsbewertung] <li>[!UICONTROL Telefonnummer] <li>[!UICONTROL Postleitzahl] <li>[!UICONTROL state] <li>[!UICONTROL Abo storniert] <li>[!UICONTROL Grund für Abmeldung] |
| Verkaufs-Apps | Lead-Aktivitäten im Zusammenhang mit [!DNL Sales Qualifier] oder [!DNL Marketo Sales Insights]. |
| Spezielle Filter | Filterattribute, die nicht unter die vordefinierten Kategorien fallen, bieten Flexibilität für benutzerdefinierte oder verschiedene Filterkriterien. |

>[!BEGINSHADEBOX]

**Unterstützte [!DNL Marketo Optimizer] für Bedingungsfilter**

Bei Pfadbedingungen unterstützt [!DNL Marketo Optimizer] Aktivitäten aus der [!DNL Marketo Engage]-Instanz, die als Datenquelle verbunden ist.

>[!NOTE]
>
>Es kann nur eine [!DNL Marketo Engage]-Instanz als Datenquelle geben. Sie ist bei der Bereitstellung Ihrer [!DNL Marketo Optimizer]-Instanz vorkonfiguriert.

Sie können Bedingungen für die folgenden [!DNL Marketo Engage]-Aktivitäten erstellen:

* **[!UICONTROL Ausgefülltes Marketo Engage-Formular]** - Stimmt mit Leads überein, die zu einem beliebigen Zeitpunkt in ihrem Aktivitätsprotokoll, aber nicht veraltet, ein bestimmtes [!DNL Marketo Engage] ausgefüllt haben.
* **[!UICONTROL Besuchte Marketo Engage-Webseite]** - Stimmt mit Leads überein, die eine bestimmte URL auf Ihrer Website oder [!DNL Marketo Engage] Landingpages angesehen haben. Es funktioniert direkt mit dem auf Ihrer Site installierten Munchkin-Trackingcode.
* **[!UICONTROL Auf Link auf Marketo Engage-Web-Seite geklickt]** - Stimmt mit Leads überein, die auf einen bestimmten Link oder ein bestimmtes Asset auf einer verfolgten Seite geklickt haben.
* **[!UICONTROL Wurde Marketo Engage-E-Mail gesendet]** - Gibt an, an wen [!DNL Marketo Engage] versucht haben, eine bestimmte E-Mail zu senden, und berücksichtigt Bereitstellungsaktionen vor Hardbounces oder Serverakzeptanzen.
* **[!UICONTROL Marketo Engage-E-Mail wurde zugestellt]** - Stimmt mit einem Lead überein, dessen Mailserver (MX) eine Erfolgsantwort (eine 250-OK-Nachricht) an den [!DNL Marketo Engage]-Versand-Server zurückgegeben hat.
* **[!UICONTROL Marketo Engage-E-Mail gebounct]** - Treffer für Leads, bei denen es bei einem bestimmten E-Mail-Versand oder innerhalb eines Zeitraums zu einem Hardbounce (dauerhaftem Versandfehler) gekommen ist.
* **[!UICONTROL Marketo Engage-E-Mail-Bounce]** - Gibt Leads zurück, bei denen ein temporärer Versandfehler (z. B. ein voller Posteingang oder ein Offline-Server) aufgetreten ist, anstatt einen permanenten Hardbounce zu verursachen.
* **[!UICONTROL Von Marketo Engage-E-]** abgemeldet: Passt zu Leads, die sich gegen nicht-operative Marketing-E-Mails entschieden haben. In diesem Fall aktualisiert [!DNL Marketo Engage] automatisch den Wert des `Unsubscribed` Feldes des Leads auf `true`, wodurch diese Werte bei zukünftigen Standard-E-Mail-Sendungen unterdrückt werden.
* **[!UICONTROL Geöffnete Marketo Engage-E-]**: Passt zu Leads, die eine verfolgte [!DNL Marketo Engage]-E-Mail geöffnet haben.
* **[!UICONTROL Link in Marketo Engage-E-Mail angeklickt]** - Stimmt mit Leads überein, die auf einen beliebigen Link (oder einen bestimmten Link) in einer [!DNL Marketo Engage]-E-Mail geklickt haben.

>[!ENDSHADEBOX]

### Hinzufügen eines Knotens mit aufgeteilten Pfaden

1. Navigieren Sie zur Journey-Arbeitsfläche.

1. Klicken Sie auf das Pluszeichen ( **+** ) auf einem Pfad und wählen Sie **[!UICONTROL Pfade aufteilen]**.

   ![Klicken Sie auf das Symbol zum Hinzufügen auf dem Journey-Pfad](./assets/person-journey-canvas-add-node.png){width="200"}

1. Um eine Bedingung zu definieren, die für _[!UICONTROL Pfad 1]_ gilt, klicken Sie auf **[!UICONTROL Bedingung anwenden]**.

1. Um den Aufspaltungspfad zu definieren, fügen Sie einen oder mehrere Filter im Bedingungseditor hinzu.

   * Ziehen Sie einen beliebigen Personenfilter aus dem linken Navigationsbereich und füllen Sie die Definition der Übereinstimmung aus.

   * Klicken Sie **[!UICONTROL Begrenzung hinzufügen]** für jede Begrenzung, die Sie zum Verfeinern der Filterübereinstimmung verwenden möchten.

     ![Pfadknoten aufteilen - Filter für übereinstimmende Personen für Pfadbedingung](./assets/journey-node-split-conditions-people.png){width="700" zoomable="yes"}

   * Verfeinern Sie Ihre Bedingungen, indem Sie oben **[!UICONTROL die]** Filterlogik“ anwenden. Sie wählen, ob alle Bedingungen oder nur eine der Bedingungen erfüllt sein sollen.

   * Klicken Sie auf **[!UICONTROL Fertig]**.

1. Um weitere Pfade hinzuzufügen, klicken Sie auf **[!UICONTROL Pfad hinzufügen]** und wiederholen Sie die vorherigen Schritte, um die für den Pfad geltenden Bedingungen hinzuzufügen.

   Sie können auch jeden Pfad anhand dieser Bedingungen beschriften oder die Standardbeschriftungen verwenden.

1. Ordnen Sie die Pfade bei Bedarf entsprechend der Priorität neu an, die Sie für die Aufspaltung festlegen möchten.

   Die Pfadfilterung wird in der Reihenfolge von oben nach unten bewertet. Jede Person fährt auf dem ersten Pfad fort, der übereinstimmt.

   Klicken Sie auf die Pfeile nach oben und unten oben rechts auf jeder Pfadkarte, um sie in der Liste der Pfade nach oben oder unten zu verschieben.

   <!-- ![Split path node - reorder paths](./assets/node-split-reorder-paths-people.png){width="500" zoomable="yes"} -->

1. Aktivieren Sie die Option **[!UICONTROL Andere Personen]**, um einen Standardpfad für Personen hinzuzufügen, die den definierten Pfaden nicht entsprechen.

   Wenn diese Option nicht aktiviert ist, bewegen sich Personen, die mit keinem definierten Segment/Pfad übereinstimmen, an der Teilung vorbei und fahren mit dem nächsten Schritt auf der Journey fort.

Wenn Sie für jeden Pfad Bedingungen definiert haben, können Sie Aktions- oder Ereignisknoten hinzufügen, die Sie auf Personen in einem Pfad anwenden möchten.

## Zusammenführen von Pfadknoten

1. Navigieren Sie zur Journey-Arbeitsfläche und suchen Sie den aufgeteilten Pfadknoten mit zwei oder mehr Pfaden.

   Jeder Pfad sollte eine Kombination aus Aktions- und Ereignisknoten aufweisen.

1. Klicken Sie auf das Pluszeichen ( **+** ) am Ende eines dieser Pfade und wählen Sie **[!UICONTROL Zusammenführungspfade]** aus den angezeigten Optionen aus.

1. Wählen Sie in den Knoteneigenschaften rechts die Pfade aus, die Sie zusammenführen möchten.

   <!-- ![Journey node - merge paths](./assets/node-merge-select-paths.png){width="600" zoomable="yes"} -->

   An dieser Stelle werden die Pfade zusammengeführt, sodass Personen aus den ausgewählten Pfaden zu einem einzigen Pfad kombiniert werden, der durch den Journey weiter ausgeführt werden kann.

1. Bei Bedarf können Sie die Zusammenführung von Pfaden aufheben, indem Sie zurück zu den Knoteneigenschaften der Zusammenführungspfade navigieren und das Kontrollkästchen für alle Pfade deaktivieren, die Sie entfernen möchten.