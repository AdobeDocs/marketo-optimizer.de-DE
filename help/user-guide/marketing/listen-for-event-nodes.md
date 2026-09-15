---
title: Überwachen auf einen Ereignisknoten
description: Konfigurieren des Lauschens auf Ereignisknoten in Marketo Optimizer - Festlegen von Ereignisfiltern, Anwenden optionaler Trigger und Vorantreiben von Personen, wenn Aktivitäten oder Datenänderungen auftreten.
TQID: 'https://experienceleague.adobe.com/6v3i6M-Hhr2RAWrS68WaEVb8VJEzJZbD7vXOJOsjgc8'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
source-git-commit: cc98b02f4273c5df2e27b52acd1239f0f0bf8aa0
workflow-type: tm+mt
source-wordcount: '1139'
ht-degree: 6%
---
# Überwachen eines Ereignisknotens

Um Ihre Audience beim Eintreten eines Ereignisses zum nächsten Schritt auf dem Journey zu leiten, fügen Sie den Knoten _Auf ein Ereignis_&quot; hinzu.

## Ereignis-Trigger {#event-triggers}

Definieren Sie die Ereigniskriterien, die den Journey-Knoten auslösen, und verschieben Sie das Mitglied der Zielgruppe vorwärts.

| Trigger | Beschreibung |
| -------- | ----------- |
| Brand Concierge | Aktivitäten für mit [!DNL Brand Concierge] interagierende Leads. |
| E-Mail | E-Mail-Aktivitäten für Leads, einschließlich Sendungen, Versand und Interaktion. |
| Ereignis | Interaktive Webinar-Aktivitäten für Leads, einschließlich Registrierung, Teilnahme und Interaktionen. |
| Opportunitys | Aktivitäten im Zusammenhang mit Opportunity-Datensätzen, die mit Leads oder Konten verknüpft sind. |
| Verkaufs-Apps | Lead-Aktivitäten im Zusammenhang mit [!DNL Sales Qualifier] oder [!DNL Marketo Sales Insights]. |
| Andere | Aktivitäten, die nicht unter die vordefinierten Kategorien fallen, bieten Triggern von benutzerspezifischen oder sonstigen Ereignissen Flexibilität. |

>[!BEGINSHADEBOX]

**Unterstützte Marketo Engage-Aktivitäten für Trigger**

Beim Auslösen von Ereignissen unterstützt [!DNL Marketo Optimizer] Aktivitäten aus der [!DNL Marketo Engage]-Instanz, die als Datenquelle verbunden ist.

>[!NOTE]
>
>Es kann nur eine [!DNL Marketo Engage]-Instanz als Datenquelle geben. Sie ist bei der Bereitstellung Ihrer [!DNL Marketo Optimizer]-Instanz vorkonfiguriert.

Sie können Ereignis-Trigger um die folgenden [!DNL Marketo Engage] Aktivitäten erstellen:

* [!UICONTROL Marketo Engage-Formular ausfüllen] - Wird ausgelöst, wenn ein Lead ein angegebenes [!DNL Marketo Engage] Formular sendet.
* [!UICONTROL Besuche Marketo Engage-Webseite] - Wird ausgelöst, wenn ein Lead mit einem Munchkin-Tracking-Cookie eine angegebene Webseite besucht.
* [!UICONTROL Klicks auf Link auf Marketo Engage-Webseite] - Wird ausgelöst, wenn ein Lead auf einen verfolgten Hyperlink auf einer Web-Seite klickt, auf der der [!DNL Marketo Engage] Munchkin-Trackingcode installiert ist.
* [!UICONTROL Marketo Engage-E-Mail wird zugestellt] - Wird ausgelöst, wenn der E-Mail-Server (MX) eines Leads eine Erfolgsantwort (eine Nachricht von 250 OK) an den [!DNL Marketo Engage]-Versand-Server zurückgibt.
* [!UICONTROL Marketo Engage-E-Mail-Bounces] - Wird ausgelöst, wenn ein Ziel-E-Mail-Server eine gesendete E-[!DNL Marketo Engage]-Nachricht als permanenten Fehler zurückweist, z. B. als ungültigen Benutzer oder als unbekannte Domain.
* [!UICONTROL Marketo Engage-E-Mail-Bounces Soft] [!DNL Marketo Engage] - Wird ausgelöst, wenn ein Ziel-E-Mail-Server eine gesendete E-Mail-Nachricht als temporäres Problem zurückweist (z. B. Server ausgelastet oder Postfach voll). [!DNL Marketo Engage] versucht Softbounces automatisch bis zu dreimal über MX-Server, bevor Probleme markiert werden.
* [!UICONTROL Abmeldungen von Marketo Engage-E-Mails] - Wird ausgelöst, wenn ein Lead sich von nicht operativen Marketing-E-Mails abmeldet. Nach der Auslösung aktualisiert [!DNL Marketo Engage] automatisch den Wert des `Unsubscribed` Feldes des Leads auf `true`, wodurch diese Werte bei zukünftigen Standard-E-Mail-Sendungen unterdrückt werden.
* [!UICONTROL Öffnet Marketo Engage-E-]: Wird ausgelöst, wenn ein Lead eine verfolgte [!DNL Marketo Engage]-E-Mail öffnet.
* [!UICONTROL Klicks auf Link in Marketo Engage-E-]: Wird ausgelöst, wenn ein Lead auf einen Link (oder einen bestimmten eingeschränkten Link) in einer [!DNL Marketo Engage]-E-Mail klickt.

>[!ENDSHADEBOX]

## Ereignisfilter {#event-filters}

Sie können Filter einschließen, um übereinstimmende Trigger von Ereignissen auf der Grundlage verschiedener Kriterien zu begrenzen:

| Filter | Beschreibung |
| ------- | ----------- |
| Aktivitätsverlauf | Aktivitäten basierend auf Bedingungen, die anhand eines oder mehrerer ausgewählter Elemente ausgewertet werden |
| Brand Concierge | Aktivitäten für mit [!DNL Brand Concierge] interagierende Leads. |
| Unternehmensattribute | Attribute aus dem Firmen-/Kontoprofil, einschließlich: <li>Jahresumsatz <li>Unternehmensname <li>Rechnungsland <li>Branche <li>Angestelltenanzahl <li>SIC-Code <li>Land |
| Absichtsdaten | Attribute, die auf den mit dem Personenprofil verknüpften Absichtsdaten basieren. |
| Opportunitys | Attribute, die auf den mit dem Personenprofil verbundenen Opportunitys basieren. |
| Personenattribute | Attribute aus dem B2B-Personenprofil, einschließlich: <li>Stadt <li>Land <li>Geburtsdatum <li>E-Mail-Adresse <li>E-Mail-Adresse ungültig <li>E-Mail angehalten <li>Vorname <li>Abgeleitetes Bundesland/abgeleitete Region<li>Stellenbezeichnung <li>Last name <li>Mobiltelefonnummer <li>Personeninteraktionsbewertung <li>Telefonnummer <li>Postleitzahl <li>Land <li>Abbestellt <li>Grund für Abmeldung |
| Verkaufs-Apps | Lead-Aktivitäten im Zusammenhang mit [!DNL Sales Qualifier] oder [!DNL Marketo Sales Insights]. |
| Spezielle Filter | Filterattribute, die nicht unter die vordefinierten Kategorien fallen, bieten Flexibilität für benutzerdefinierte oder verschiedene Filterkriterien. |

>[!BEGINSHADEBOX]

**Unterstützte Marketo Engage-Aktivitäten für Filter**

Beim Filtern nach ausgelösten Ereignissen unterstützt [!DNL Marketo Optimizer] Aktivitäten aus der [!DNL Marketo Engage]-Instanz, die als Datenquelle verbunden ist.

>[!NOTE]
>
>Es kann nur eine [!DNL Marketo Engage]-Instanz als Datenquelle geben. Sie ist bei der Bereitstellung Ihrer [!DNL Marketo Optimizer]-Instanz vorkonfiguriert.

Sie können Ereignisfilter um die folgenden [!DNL Marketo Engage] Aktivitäten erstellen:

* [!UICONTROL Ausgefülltes Marketo Engage-Formular] - Stimmt mit Leads überein, die zu einem beliebigen Zeitpunkt in ihrem Aktivitätsprotokoll, aber nicht veraltet, ein bestimmtes [!DNL Marketo Engage] ausgefüllt haben.
* [!UICONTROL Besuchte Marketo Engage-Webseite] - Stimmt mit Leads überein, die eine bestimmte URL auf Ihrer Website oder [!DNL Marketo Engage] Landingpages angesehen haben. Dies hängt direkt vom auf Ihrer Site installierten Munchkin-Trackingcode ab.
* [!UICONTROL Auf Link auf Marketo Engage-Web-Seite geklickt] - Stimmt mit Leads überein, die auf einen bestimmten Link oder ein bestimmtes Asset auf einer verfolgten Seite geklickt haben.
* [!UICONTROL Wurde Marketo Engage-E-Mail gesendet] - Gibt an, an wen [!DNL Marketo Engage] versucht haben, eine bestimmte E-Mail zu senden, und berücksichtigt Bereitstellungsaktionen vor Hardbounces oder Serverakzeptanzen.
* [!UICONTROL Marketo Engage-E-Mail wurde zugestellt] - Stimmt mit Leads überein, deren E-Mail-Server (MX) eine Erfolgsantwort (eine 250-OK-Nachricht) an den [!DNL Marketo Engage]-Versand-Server zurückgegeben hat.
* [!UICONTROL Marketo Engage-E-Mail gebounct] - Stimmt mit Leads überein, die einen Hardbounce (einen permanenten Versandfehler) bei einem bestimmten E-Mail-Versand oder innerhalb eines bestimmten Zeitraums hatten.
* [!UICONTROL Marketo Engage-E-Mail-Bounce] - Gibt Leads zurück, bei denen ein temporärer Versandfehler (z. B. ein voller Posteingang oder ein Offline-Server) aufgetreten ist, anstatt einen permanenten Hardbounce zu verursachen.
* [!UICONTROL Von Marketo Engage-E-] abgemeldet: Passt zu Leads, die sich gegen nicht-operative Marketing-E-Mails entschieden haben. In diesem Fall aktualisiert [!DNL Marketo Engage] automatisch den Wert des `Unsubscribed` Feldes des Leads auf `true`, wodurch diese Werte bei zukünftigen Standard-E-Mail-Sendungen unterdrückt werden.
* [!UICONTROL Geöffnete Marketo Engage-E-]: Passt zu Leads, die eine verfolgte [!DNL Marketo Engage]-E-Mail geöffnet haben.
* [!UICONTROL Link in Marketo Engage-E-Mail angeklickt] - Stimmt mit Leads überein, die auf einen beliebigen Link (oder einen bestimmten Link) in einer [!DNL Marketo Engage]-E-Mail geklickt haben.

>[!ENDSHADEBOX]

## Ereignisknoten hinzufügen {#add-event-node}

1. Navigieren Sie zur Journey-Arbeitsfläche.

1. Klicken Sie auf das Pluszeichen ( **+** ) in einem Pfad und wählen Sie **[!UICONTROL Auf ein Ereignis überwachen]**.

   ![Klicken Sie auf das Symbol zum Hinzufügen auf dem Journey-Pfad](./assets/person-journey-canvas-add-node.png){width="200"}

1. Klicken Sie in den Knoteneigenschaften auf der rechten Seite **[!UICONTROL Ereigniskriterien hinzufügen]**.

1. Fügen Sie im _[!UICONTROL Ereignis bearbeiten]_ ein -Ereignis hinzu und legen Sie die Begrenzungen fest, denen Sie für den Trigger entsprechen möchten.

   Ziehen Sie den Ereignis -Trigger per Drag-and-Drop in den Builder-Bereich und legen Sie die Definition fest. Klicken Sie **[!UICONTROL Begrenzung hinzufügen]** für jede Begrenzung, die Sie zum Verfeinern der Ereignisübereinstimmung verwenden möchten.

   ![Ereignis bearbeiten - Ereignis-Trigger ](./assets/edit-event-triggers.png){width="700" zoomable="yes"}

   Sie können mehrere Ereignisse hinzufügen, die übereinstimmen. Das erste Qualifizierungsereignis bringt das Personenprofil auf der Journey voran.

1. (Optional) Wählen Sie die **[!UICONTROL Filter]** und fügen Sie Filterkriterien für die Trigger hinzu.

   Ziehen Sie den Filter per Drag-and-Drop in den Builder-Bereich und legen Sie die Definition fest. Klicken Sie **[!UICONTROL Begrenzung hinzufügen]** für jede Begrenzung, die Sie zum Verfeinern der Filterübereinstimmung verwenden möchten.

   ![Ereignis bearbeiten - Ereignisfilterung](./assets/edit-event-filters.png){width="700" zoomable="yes"}

1. Klicken Sie auf **[!UICONTROL Speichern]**.

   Sie können jederzeit auf **[!UICONTROL Ereignis bearbeiten]** klicken, um die Ereigniskriterien für den Knoten zu ändern.

1. Legen Sie bei Bedarf die Option **[!UICONTROL Timeout]** fest, um den Zeitraum für die Überwachung des Ereignisses zu begrenzen.

   >[!NOTE]
   >
   >Der Journey endet nach einer Zeitüberschreitung, es sei denn, Sie definieren einen Zeitüberschreitungspfad, über den Sie weitere Knoten hinzufügen können.

   Aktivieren Sie die Option **[!UICONTROL Zeitüberschreitung]** und wählen Sie die Dauer aus, für die der Journey auf ein Ereignis wartet, bevor eine Zeitüberschreitung eintritt.

   ![Zeitüberschreitungsoptionen für den Knoten „Lauschen auf Ereignis-Journey&quot; aktiviert](./assets/person-journey-event-node-timeout.png){width="550" zoomable="yes"}

   Sie können den Pfad hier beenden oder eine andere Aktion ausführen, indem Sie einen anderen Pfad festlegen. Um einen neuen Pfad auf der Journey zu erstellen, in dem Sie Aktionen und Ereignisse hinzufügen können, die für Profile gelten, wenn das Ereignis nicht eintritt, aktivieren Sie das Kontrollkästchen **[!UICONTROL Zeitüberschreitungspfad festlegen]**.
