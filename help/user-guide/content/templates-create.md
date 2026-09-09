---
title: E-Mail-Vorlagen erstellen
description: Erfahren Sie, wie Sie E-Mail-Vorlagen in Marketo Optimizer erstellen - neu erstellen, eine E-Mail von einer Journey als Vorlage speichern oder ein Design-Bild in eine E-Mail-Vorlage konvertieren.
TQID: 'https://experienceleague.adobe.com/Hag-o6Hu-82rqnWHnDBgPD-dKApy5JGsPMD5cGFOCfA'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2:
  - id: 8881ff95-1653-5fea-82af-ce1549c0d99d
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: cc72dcf1-72e1-48cc-b434-e7c27d62d67c
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 873
ht-degree: 1%

---


# E-Mail-Vorlagen erstellen

Sie haben drei Möglichkeiten, um eine E-Mail-Vorlage in [!DNL Adobe Marketo Optimizer] zu erstellen:

* **Neue Vorlage erstellen** - Erstellen Sie eine Vorlage in der Vorlagenbibliothek mithilfe des visuellen E-Mail-Design-Bereichs.
* **Von einer Journey-E-Mail speichern** - Speichern Sie eine E-Mail, die Sie auf einer Journey verfasst haben, als wiederverwendbare Vorlage.
* **Bild konvertieren** - Laden Sie ein Designbild hoch und verwenden Sie generative KI, um es in eine bearbeitbare E-Mail-Vorlage zu konvertieren.

## Neue Vorlage erstellen {#build-new}

1. Erweitern Sie in der linken Navigation **[!UICONTROL Content-Management]** und wählen Sie **[!UICONTROL Vorlagen]**.
1. Klicken Sie auf **[!UICONTROL Vorlage erstellen]**.
1. Geben Sie einen **[!UICONTROL Vorlagennamen“]** optional &quot;**[!UICONTROL &quot;]**.
1. Legen Sie den **[!UICONTROL Kanal]** (Typ) für die Vorlage fest.

   >[!NOTE]
   >
   >In dieser Beta-Version werden nur E-Mail-Vorlagen unterstützt.

   <!-- 1. Optionally add **[!UICONTROL Tags]** to categorize the template. -->

1. Klicken Sie **[!UICONTROL Erstellen]**, um den E-Mail-Design-Bereich zu öffnen.

1. Klicken Sie **[!UICONTROL E-Mail-Text bearbeiten]**, um auf den Bereich für das Inhalts-Design zuzugreifen.

   Siehe [E-Mail-Authoring](email-authoring.md) für detaillierte Informationen zur Inhaltserstellung.

1. Aktivieren Sie optional **[!UICONTROL Governance]** und konfigurieren Sie [Inhaltssperrung](template-content-governance.md), um festzulegen, welche Teile der Vorlagen von Vorlagenautoren beim Anwenden der Vorlage bearbeitet werden können.

1. Klicken Sie auf **[!UICONTROL Speichern]**.

## Speichern einer E-Mail als Vorlage {#save-as-template}

Wenn Sie den E-Mail-Inhalt öffnen, den Sie wiederverwenden möchten, speichern Sie ihn direkt in der Vorlagenbibliothek auf der E-Mail-Inhaltsseite.

1. Klicken Sie **[!UICONTROL oben]** der Seite auf „Inhaltsvorlage“.
1. Wählen **[!UICONTROL Als Inhaltsvorlage speichern]**.
1. Geben Sie einen **[!UICONTROL Namen]** und optional **[!UICONTROL Beschreibung]** ein.
1. Fügen Sie optional **[!UICONTROL Tags]** hinzu.
1. Klicken Sie auf **[!UICONTROL Erstellen]**.

Die ursprüngliche Journey-E-Mail ist nicht betroffen. Die gespeicherte Vorlage ist in der Vorlagenbibliothek für alle Benutzer in der Sandbox verfügbar. Sie können die erstellte Vorlage aktualisieren, um die Wiederverwendung zu optimieren:

* Bearbeiten von Text und Hinzufügen [Personalisierungs](email-authoring.md#personalize-content)Token.
* Bilder aktualisieren oder ersetzen und Links hinzufügen.
* Konfigurieren Sie [Inhaltssperrung](template-content-governance.md).

## Konvertieren eines Bildes in eine Vorlage {#image-to-template}

[!DNL Adobe Marketo Optimizer] können ein statisches Bild - z. B. ein Mockup aus Figma oder Photoshop - mithilfe von generativer KI in eine bearbeitbare E-Mail-Vorlage konvertieren. Dadurch entfällt die Notwendigkeit, Layouts aus Design-Dateien manuell neu zu erstellen, und es ist ideal für die Migration vorhandener E-Mail-Designs von anderen Plattformen. Diese Funktion ist nur für E-Mail-Inhaltsvorlagen verfügbar.

>[!BEGINSHADEBOX]

### Voraussetzungen

Bevor Sie beginnen:

* Ihr Unternehmen muss das Generative AI-Addendum mit Adobe unterzeichnet haben.
* Sie müssen über die Berechtigung **[!UICONTROL Inhalt generieren]** zusätzlich zu **[!UICONTROL Inhaltsvorlagen verwalten]** verfügen.
* Die Bilddatei muss den folgenden Spezifikationen entsprechen:
  * Format: JPEG (.jpg, .jpeg) oder PNG (.png)
  * Maximale Dateigröße: 10 MB
  * Empfohlene Breite: 600-800 Pixel
  * Klare, hochwertige Bilder mit lesbarem Text und ausgeprägten visuellen Elementen

>[!IMPORTANT]
>
>Das Bild darf keine personenbezogenen oder vertraulichen Daten enthalten.

>[!ENDSHADEBOX]

### Erstellen der Vorlage

1. Erweitern Sie in der linken Navigation **[!UICONTROL Content-Management]** und wählen Sie **[!UICONTROL Vorlagen]**.
1. Klicken Sie auf **[!UICONTROL Vorlage erstellen]**.
1. Geben Sie einen **[!UICONTROL Vorlagennamen“]** optional &quot;**[!UICONTROL &quot;]**.
1. Setzen Sie **[!UICONTROL Kanal]** auf E-Mail.

   <!--  Optionally add **[!UICONTROL Tags]** to categorize the template. -->

1. Klicken Sie auf **[!UICONTROL Erstellen]**.

### Generieren des Vorlageninhalts

1. Im Abschnitt **[!UICONTROL Bild in Vorlage konvertieren]**:

   * Wählen Sie optional ein **[!UICONTROL Markendesign]**, um die Farben, Schriftarten und Abstände Ihrer Marke auf die generierte Ausgabe anzuwenden.
   * Aktivieren Sie das Kontrollkästchen Bestätigung , um zu bestätigen, dass Ihr Bild keine personenbezogenen oder anderen sensiblen Daten enthält.
   * Klicken Sie **[!UICONTROL Bild hochladen]** und wählen Sie Ihre Bilddatei aus.

   >[!CAUTION]
   >
   >Beim Hochladen eines Bildes wird der gesamte aktuell in der E-Mail enthaltene Inhalt gelöscht und durch die generierte Vorlage ersetzt.

1. Überprüfen und akzeptieren Sie bei Aufforderung die Benutzerhandbücher für die generative KI von Adobe.

1. Klicken Sie **[!UICONTROL Öffnen]**, um den Konvertierungsprozess zu starten.

   Die Konvertierung wird in der Regel innerhalb von etwa fünf Minuten abgeschlossen. Komplexe oder große Bilder können bis zu zehn Minuten dauern. Die Konvertierung wird im Hintergrund ausgeführt - Sie können die Seite verlassen und die Entwurfsvorlage wird nach Abschluss der Konvertierung automatisch gespeichert.

1. Aktualisieren Sie die Seite, um die fertige Vorlage anzuzeigen.

   >[!NOTE]
   >
   >Das Ergebnis wird nicht automatisch angezeigt. Aktualisieren Sie die Seite oder kehren Sie zur Vorlagenbibliothek zurück, um die fertige Vorlage anzuzeigen.

1. Optional können Sie den Abschnitt **[!UICONTROL Feedback zur Konvertierung von Bildern in Vorlagen]** verwenden, um Vorschläge für Adobe freizugeben.

1. Klicken Sie auf **[!UICONTROL E-Mail-Text bearbeiten]**, um die konvertierte Vorlage im E-Mail-Design-Bereich zur Bearbeitung zu öffnen.

1. Klicken Sie auf **[!UICONTROL Speichern]**.

### Bearbeiten des konvertierten Inhalts

Der konvertierte Vorlageninhalt wird im Design-Bereich als vollständig bearbeitbare E-Mail-Vorlage geöffnet. Verwenden Sie die standardmäßigen Inhaltserstellungs-Tools für Folgendes:

* Bearbeiten von Text und Hinzufügen [Personalisierungs](email-authoring.md#personalize-content)Token.
* Bilder aktualisieren oder ersetzen und Links hinzufügen.
* Farben, Schriftarten und Abstände anpassen.
* Hinzufügen, Entfernen oder Neuanordnen von Inhaltskomponenten.
* Aktivieren Sie Governance und konfigurieren Sie [Inhaltssperrung](template-content-governance.md).

>[!IMPORTANT]
>
>Die generative KI erzeugt statische HTML basierend auf dem visuellen Bild. Überprüfen Sie den gesamten Text auf Genauigkeit und fügen Sie nach der Konvertierung Personalisierung, dynamische Inhalte und Tracking manuell hinzu.

Die konvertierte Vorlage wird nach Abschluss der Konvertierung automatisch in der Vorlagenbibliothek gespeichert.

### Tipps für optimale Ergebnisse

Verwenden Sie die folgenden Richtlinien, um die besten Ergebnisse aus der Konvertierung von Bildern in Vorlagen zu erzielen:

**Vor der Konvertierung:**

* Verwenden Sie die Version mit der höchsten Auflösung Ihrer Design-Datei.
* Entwerfen Sie mit standardmäßigen E-Mail-Breiten (600-800 Pixel) und fügen Sie das vollständige Layout - Kopf- und Fußzeile - in ein einziges Bild ein.
* Achten Sie auf einen ausreichenden Kontrast zwischen Text und Hintergrund und verwenden Sie lesbare Schriftgrößen.

**Design für genaue Konvertierung:**

* Verwenden Sie einfache, gut strukturierte Layouts mit klarer Trennung zwischen Abschnitten.
* Folgen Sie standardmäßigen E-Mail-Mustern - Kopfzeile, Hauptteil, Aktionsaufrufe, Fußzeile - anstelle von komplexen mehrschichtigen Designs.
* Halten Sie visuelle Elemente getrennt, damit die KI Strukturgrenzen korrekt identifizieren kann.

**Nach der Konvertierung:**

* Testen des Renderings auf E-Mail-Clients und Geräten, bevor die Vorlage auf einer Journey verwendet wird.
* Überprüfen Sie die Ausrichtung anhand von Markenfarben, Schriftarten und Stilrichtlinien.
* Überprüfen und verbessern Sie die Barrierefreiheit, einschließlich Bild-Alt-Text.
