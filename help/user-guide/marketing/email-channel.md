---
title: Hinzufügen von E-Mails zu Journeys
description: Fügen Sie E-Mail-Aktionsknoten zu Personen-Journey hinzu und erstellen Sie neue E-Mails für zielgerichtete Kommunikation in Marketo Optimizer.
feature: Email Authoring, Person Journeys
role: User
TQID: 'https://experienceleague.adobe.com/tCJStmR66eVoB8cvzcQWc5UO-klwTjnNfK-4K5Nz-S0'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
topic_v2: id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 1048
ht-degree: 20%

---

# Hinzufügen von E-Mails zu Journeys

[!DNL Adobe Marketo Optimizer] bietet B2B-Marketern ein modernes, für Unternehmen geeignetes Erlebnis für E-Mail-Authoring und -Versand.

>[!NOTE]
>
>Wenn Sie zum ersten Mal eine E-Mail senden, stellen Sie sicher, dass [E-Mail-Zustellbarkeit](../start/email-deliverability.md) und der erforderliche [E-Mail-Kanal](../admin/email-channel-configuration.md) konfiguriert sind.

<!-- 
* **Email channel configurations** - Manage the sender identity, reply behavior, marketing vs. transactional message types, and tracking.
* **Email deliverability controls** - Set up your email deliverability channel, including subdomain delegation (Fully Delegated and CNAME methods), DMARC, SPF/DKIM auto-configuration, and shared IP pool support.
* **Send Email action** - From a journey, add a _Send email_ action node, including personalization using profile attributes (Handlebars syntax).
* **Visual drag-and-drop email design tools** -  Design your email content with structures, content components, themes, dark-mode support, and reusable visual fragments.
* **Marketo Design Studio assets** — Choose images and assets from a one-time copy of your Marketo Engage asset library directly inside the email canvas.
* **Reusable templates and fragments** — Save common headers, footers, CTAs, and full email layouts and reuse them across journeys.
* **Role-Based Access Control (RBAC)** — Apply granular permissions for creating, editing, approving, and sending email. 
-->

## Aktuelle Einschränkungen {#limitations}

* **Testprofile, Inhalt simulieren und Testversand durchführen** sind in dieser Version nicht verfügbar. Litmus-Rendering- und SpamAssassin-basierte Spam-Berichte stehen auf der GA-Roadmap.
* **Personalisierung auf Kontoebene und benutzerdefinierte Objektdaten** sind in dieser Version nicht verfügbar. Verwenden von Profilattributen.
* **Automatisierte Migration von Velocity zu Handlebars** bestehender Marketo Engage-Vorlagen wird über GA ausgeliefert.
* **Kommentare und Zusammenarbeit bei E** Mails (Inline-Kommentare, @mentions, Workflow für die Überprüfung von Anfragen) werden in einer kommenden Version bereitgestellt.
* Integrationen mit **AEM Assets, AEM-Inhaltsfragmenten und Adobe Express** stehen auf der _Fast Follow-up_-Roadmap.

## Schlüsselkonzepte {#key-concepts}

Bevor Sie E-Mails für Personen-Journey erstellen und E-Mail-Inhalte verfassen, sollten Sie die folgenden Konzepte überprüfen:

| Konzept | in [!DNL Adobe Marketo Optimizer] |
| ------- | ---------------------- |
| **_E-Mail-Design-Bereich_** | Die visuelle Arbeitsfläche und Design-Tools, die zum Erstellen von E-Mail-Inhalten verwendet werden. Es enthält Layout-Komponenten, Vorlagen, Fragmente und Designs per Drag-and-Drop und einen Personalisierungseditor. |
| **_Vorlage_** | Ein wiederverwendbares E-Mail-Layout, das zum Erstellen einer neuen E-Mail verfügbar ist. Dabei kann es sich entweder um eine integrierte Beispielvorlage handeln, die von Adobe bereitgestellt wird, oder um eine benutzerdefinierte Vorlage, die von Ihrem Team erstellt wurde. |
| **_Visuelles Fragment_** | Ein wiederverwendbarer Inhaltsblock (z. B. Kopf- und Fußzeile, CTA, Haftungsausschluss), der in mehrere E-Mails eingefügt werden kann. Beim Aktualisieren eines Fragments wird die Änderung an jede E-Mail weitergegeben, die es verwendet. |
| **_Design_** | Eine wiederverwendbare Stilvorgabe (Farben, Typografie, Abstände, Schaltflächenstile), die auf eine E-Mail angewendet wird. |
| **_Personalization-Token_** | Ein Handlebars-Ausdruck, z. B. `{{profile.firstName}}`, wird zum Sendezeitpunkt mithilfe der Profildaten jedes Empfängers aufgelöst. |
| **_Aktion „E-Mail senden“_** | Der Journey-Aktionsknoten, der eine Kanalkonfiguration und E-Mail-Inhalt zum Versand einer E-Mail verwendet. |

## Hinzufügen einer E-Mail von einer Journey

Um E-Mails von einer Journey zu senden[ fügen Sie &quot;_Aktion durchführen“_ Knoten ](action-nodes.md#add-an-action-node) und konfigurieren Sie ihn so, dass E-Mails gesendet werden.

1. Klicken Sie auf der Journey-Arbeitsfläche auf das Symbol **+** und wählen Sie **[!UICONTROL Aktion ausführen]**.

1. Legen Sie in den Knoteneigenschaften auf der rechten Seite die Aktion auf **[!UICONTROL E-Mail senden]** fest.

   ![Aktion durchführen - E-Mail senden](./assets/person-action-node-send-email.png){width="500"}

1. E-Mail-Quelle auswählen:

   * **E-Mail erstellen/bearbeiten** - Wählen Sie diese Option, um den E-Mail-Inhalt einschließlich Betreffzeile, Absenderinformationen und E-Mail-Textkörper im E-Mail-Design-Bereich zu definieren.

   * **[!UICONTROL KI-personalisierte E-Mail verwenden]** - (_Für Beta nicht verfügbar_) Wählen Sie diese Option, um eine von KI generierte E-Mail im E-Mail-Design-Bereich zu verfeinern. Diese E-Mails sind so optimiert, dass KI-unterstützte Posteingangskunden ihre Zusammenfassungen und Antworten in Ihren Angeboten und Aktionsaufrufen vermitteln.

1. Klicken Sie **[!UICONTROL E-Mail erstellen]**.

1. Geben _[!UICONTROL im Dialogfeld „E]_ Mail erstellen“ einen eindeutigen **[!UICONTROL Name]** (erforderlich) und einen **[!UICONTROL Beschreibung]** (optional) ein.

   ![Dialogfeld „E-Mail erstellen“](./assets/email-channel-create-email-dialog.png){width="400"}

1. Klicken Sie auf **[!UICONTROL Erstellen]**.

Für die optionale [Sendezeitoptimierung](email-send-time-optimization.md) konfigurieren Sie den Journey-Aktionsknoten, nachdem Sie die E-Mail erstellt haben.

## Definieren der E-Mail-Eigenschaften und -Aktionen {#define-email-properties}

Die E-Mail-Seite wird geöffnet, wenn Sie eine E-Mail für einen _[!UICONTROL E-Mail senden]_-Knoten erstellen. Sie können auf diese Seite auch zugreifen, nachdem die E-Mail erstellt wurde, indem **[!UICONTROL E-Mail bearbeiten]** in den Knoteneigenschaften auf der rechten Seite klicken.

1. (Optional) Geben Sie auf der **[!UICONTROL Eigenschaften]** alle beschreibenden Informationen ein, die Sie für die E-Mail erfassen möchten.

1. Wählen Sie die Registerkarte **[!UICONTROL Aktionen]** und füllen Sie die Funktionseinstellungen für die E-Mail aus:

   * **[!UICONTROL E]** Mail: Wählen oder erstellen Sie eine **[!UICONTROL E-Mail-Kanalkonfiguration]**, um sie zu verwenden.

     Hierbei handelt es sich um den wiederverwendbaren Satz von E-Mail-Versandeinstellungen, der die Absenderidentität, die Antwortadresse, die Subdomain, den IP-Pool, den E-Mail-Typ (Marketing oder Transaktion) und das Tracking definiert. Klicken Sie auf _Anzeigen_-Symbol, um die Einstellungen für die ausgewählte Konfiguration zu überprüfen.

     Administratoren erstellen Konfigurationen in [E-Mail-Kanalkonfiguration](../admin/email-channel-configuration.md).

   * **[!UICONTROL Geschäftsregeln]** - (Optional) Wenden Sie Begrenzungs- oder Ruhezeitenregeln auf Ihre E-Mail-Aktion an, indem Sie einen Regelsatz auswählen.

     Weitere Informationen zu Geschäftsregeln und zum Definieren und Aktivieren von Regelsätzen für die Kanalkommunikation finden Sie unter [_Geschäftsregeln_](../admin/business-rules.md).

   * **[!UICONTROL Aktions-Tracking]** - Aktivieren Sie die Kontrollkästchen für die Aktionen, die Sie für die E-Mail verfolgen möchten.

   ![E-Mail-Kanal - Registerkarte „Aktionen“](./assets/email-channel-actions-tab.png){width="600" zoomable="yes"}

1. Klicken Sie **[!UICONTROL Inhalt bearbeiten]** oder wählen Sie die Registerkarte **[!UICONTROL Inhalt]** aus.

1. Geben Sie **[!UICONTROL Text „Betreffzeile]** ein, den Sie im Feld Betreff für die E-Mail anzeigen möchten.

   Klicken Sie auf das _Personalisieren_-Symbol ( ![Personalisieren-Symbol](../assets/do-not-localize/icon-personalize.svg) ), um ein Personalisierungs-Token in diesem Feld zu verwenden.

1. (Optional) Aktivieren Sie das Kontrollkästchen **[!UICONTROL Größe der HTML optimieren]**, um die Größe Ihrer E-Mail-HTML während des Veröffentlichungsprozesses zu reduzieren.

   Dadurch wird verhindert, dass E-Mails in Clients wie Gmail abgeschnitten werden, wodurch Nachrichten mit einer Größe von mehr als 100 KB gekürzt werden. Weitere Informationen finden [_unter „Optimieren der E_](#optimize-html-size) Mail-HTML-Größe“.

1. Klicken Sie auf **[!UICONTROL E-Mail-]** bearbeiten), um auf die visuellen Design-Tools zuzugreifen und mit der [Erstellung Ihres Inhalts](../content/email-authoring.md) zu beginnen.

   Alternativ können Sie auf **[!UICONTROL Code-Editor]** klicken, um Ihren eigenen Inhalt im HTML-Format zu codieren. Wenn Sie über HTML verfügen, das Sie für Ihr E-Mail-Design wiederverwenden können, können Sie es kopieren und in den Editor einfügen.

### Prüfen von Warnhinweisen {#alerts}

[!DNL Adobe Marketo Optimizer] Probleme werden oben rechts auf der E-Mail-Seite angezeigt. Beheben Sie alle Fehler, bevor Sie die Journey aktivieren. Warnungen sind nur Empfehlungen.

**Fehler** (Journey-Aktivierung verhindern):

* Absendername ist leer
* Betreffzeile fehlt
* E-Mail-Inhalt ist leer

**Warnungen** (Empfehlungen):

* Der Opt-out-Link ist nicht im Text der E-Mail enthalten
* Textversion von HTML ist leer
* Leere Links erkannt
* E-Mail überschreitet 100 KB

## Optimieren der HTML-Größe von E-Mails {#optimize-html-size}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_email_minification"
>title="HTML-Größe reduzieren"
>abstract="Diese Option aktivieren, um die E-Mail-HTML während der Veröffentlichung zu komprimieren, indem unnötige Leerzeichen und Einzüge entfernt werden. Dadurch wird verhindert, dass E-Mails in Clients wie Gmail abgeschnitten werden, wodurch Nachrichten mit einer Größe von mehr als 100 KB gekürzt werden."

[!DNL Marketo Optimizer] ermöglicht das Komprimieren der HTML-Version Ihrer E-Mail während des Veröffentlichungsprozesses durch Entfernen unnötiger Leerzeichen, Einrückungen und nicht erforderlicher Kommentare. Eine geringe HTML-Größe bietet folgende Vorteile:

* Verhindern des **Abschneidens von E-Mails** – einige E-Mail-Clients wie Gmail kürzen Nachrichten mit einer Größe von mehr als ca. 100 KB, sodass Empfangende den vollständigen Inhalt nicht sehen können.
* Verbessern der **Ladezeit von E-Mails** im Posteingang der Empfangenden.
* Verbessern der **Zustellbarkeit** und Reduzieren der Bandbreitennutzung.

Diese Optimierung wird nicht automatisch angewendet - Sie müssen sie auf der Registerkarte _[!UICONTROL Inhalt]_ aktivieren.

<!-- ![](assets/email-optimize-html-size.png) -->

>[!IMPORTANT]
>
> Die Größenreduzierung von HTML wird nur zum Zeitpunkt der Veröffentlichung angewendet.

Die Optimierung ist E-Mail-Client-sicher:

* Bedingte MSO/Outlook-Kommentare werden beibehalten.
* Ihre tatsächlichen Inhalte, Bilder oder Videos werden nicht geändert.

>[!NOTE]
>
>Die Reduzierung der E-Mail-Größe hängt von der ursprünglichen HTML-Struktur Ihrer E-Mail ab. Wenn der Inhalt bereits kompakt oder die E-Mail-Payload sehr groß ist, kann die Reduzierung minimal sein und das Abschneiden möglicherweise nicht in allen Fällen vollständig verhindern.

<!-- 
Proof and simulate workflows are not available in this release. See [Current limitations](#limitations).

### Test HTML size optimization {#optimize-html-proof}

If you have enabled the [HTML size optimization](#optimize-html-size) option, you can evaluate its impact before publishing when sending proofs. Follow the following steps.

1. In the email design space, click the _Issues_ icon on the top right. If the rendered email size exceeds 100 KB, a message is displayed to warn you that this may cause truncation in some email clients.

1. Click **[!UICONTROL Simulate content]**.

1. To test the optimized version, click the **[!UICONTROL Send proof]** button and select the **[!UICONTROL Optimize HTML size]** option. This will send a proof with the reduced HTML size to your test recipients.

    >[!NOTE]
    >
    >This setting is independent from the email editor — the proof reflects what you select in the proof, regardless of whether the option is enabled or disabled in the email itself.

1. Select the test recipients and click **[!UICONTROL Send proof]**.

1. Back in the **[!UICONTROL Simulate]** screen, click the **[!UICONTROL View Proof]** button.

1. Click the _Information_ icon next to the status of the proof.

   The optimization details are displayed in a pop-up window, including the original HTML size, the optimized HTML size, and the size reduction percentage.
    
    Use this information to validate the optimized output and confirm the email stays within the recommended 100 KB threshold before publishing.

-->
