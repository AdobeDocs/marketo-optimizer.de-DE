---
title: Konfiguration der Landingpage
description: Platzhalter
TQID: 'https://experienceleague.adobe.com/wowFSf32UsmDemN6Iy5-IgGOPmuocHHLRb4vvTUDt0U'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 3cf5f37e-e87e-5179-812b-53ce05d7eebbid: a659ad61-de21-559d-a901-02e2fb329ff5id: d4203578-d294-5145-b397-f26f4488a904
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 971
ht-degree: 42%

---


# Konfiguration einer Landingpage

Admins sollten sicherstellen, dass die Landingpage-Konfigurationen für die Marketer vorhanden sind, die diese Seiten erstellen und veröffentlichen. Es gibt zwei Konfigurationstypen, die erforderlich sind, um Landingpages zu erstellen, die eine Marke widerspiegeln und die Interaktion effektiv verfolgen:

* **_Subdomains_** - Legen Sie fest, wo Landingpages gehostet werden. Verwalten Sie Landingpage-Subdomains zum Delegieren, Konfigurieren oder Aufheben der Delegierung von Domain-Einstellungen.
* **_Voreinstellungen_** - Definieren Sie wiederverwendbare Konfigurationen (einschließlich Subdomain- und anderen Kanaleinstellungen), damit Marketing-Experten Landingpages konsistent erstellen und verwalten können.

## Subdomains {#lp-subdomains}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin_subdomain_lp_header"
>title="Delegieren einer Subdomain der Landingpage"
>abstract="Richten Sie eine Subdomain für eine Landingpage ein. Es kann eine Subdomain verwendet werden, die bereits an Adobe delegiert ist, oder eine andere Subdomain konfiguriert werden."

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin_subdomain_lp"
>title="Delegieren einer Subdomain der Landingpage"
>abstract="Sie müssen eine Landingpage-Subdomain konfigurieren, bevor Sie eine Landingpage-Voreinstellung erstellen. Sie können eine Subdomain verwenden, die bereits an Adobe delegiert ist, oder eine andere Subdomain konfigurieren."

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin_config_lp_subdomain"
>title="Erstellen einer Landingpage-Voreinstellung"
>abstract="Um eine Landingpage-Voreinstellung zu erstellen, müssen Sie zuvor mindestens eine Landingpage-Subdomain konfiguriert haben, die aus der Liste „Name der Subdomain“ ausgewählt werden kann."

Um die konfigurierten Landingpage-Subdomains zu überprüfen, gehen Sie zu **[!UICONTROL Administration]** > **[!UICONTROL Kanäle]**. Wählen _[!UICONTROL im]_ unter „Landingpages“ die Option **[!UICONTROL Landingpage-Subdomains]** aus.

<!-- ![Channel configurations - landing page subdomains](./assets/config-channels-landing-pages-subdomains.png){width="800" zoomable="yes"} -->

Die Spalte **Status** enthält Informationen zum Prozess der Erstellung und Zuweisung von Subdomains:

* _[!UICONTROL Entwurf]_: Die Subdomain-Zuweisung wird als Entwurf gespeichert. Klicken Sie auf den Namen der Subdomain, um den Erstellungsprozess fortzusetzen.
* _[!UICONTROL Verarbeitung]_: Die Subdomain wird durch mehrere Konfigurationsprüfungen überprüft, die erforderlich sind, bevor sie verwendet werden kann.
* _[!UICONTROL Erfolg]_: Die Subdomain, die die Prüfungen erfolgreich durchlaufen hat und zum Versand von Nachrichten verwendet werden kann.
* _[!UICONTROL Fehlgeschlagen]_: Eine oder mehrere Prüfungen sind fehlgeschlagen, nachdem die Subdomain-Zuweisung übermittelt wurde.

>[!NOTE]
>
>Bevor Sie [Landingpage-Voreinstellungen erstellen](#lp-presets) müssen Sie die Subdomains einrichten, die für Landingpages verwendet werden sollen. Sie können eine Subdomain verwenden, die bereits an Adobe delegiert wurde, oder eine andere Subdomain konfigurieren.

Eine Landingpage-Subdomain-Konfiguration ist **in allen Umgebungen**. Daher gilt:

* Um auf Landingpage-Subdomains zuzugreifen und diese zu bearbeiten, benötigen Sie die Berechtigung zum **[!UICONTROL Verwalten von Landpingpage-Subdomains]** in der Produktions-Sandbox.

* Jede Änderung an einer Landingpage-Subdomain wirkt auch auf die Produktions-Sandboxes aus.

<!-- 
### Use an existing subdomain {#lp-existing-subdomain}

To use a subdomain that is already delegated to Adobe:

1. Click **[!UICONTROL Set up landing page subdomain]**.

    ![](assets/lp_set-up-subdomain.png)

1. For _[!UICONTROL Configuration type]_, choose **[!UICONTROL Use delegated domain]**.

    ![](assets/lp_use-delegated-subdomain.png)

1. Enter the prefix that you want to display in the landing page URL.

    Only alpha-numeric characters and hyphens are allowed.

    >[!CAUTION]
    >
    >Do not use `cdn` or `data` prefixes as these are reserved for internal use. You should also avoid other restricted or reserved prefixes, such as `dmarc` or `spf`.

1. Select a delegated subdomain from the list.

    You cannot select a subdomain that is already used as landing page subdomain.
    
    ![](assets/lp_prefix-and-subdomain.png)

    You cannot use multiple delegated subdomains of the same parent domain. For example, if 'marketing1.yourcompany.com' is already delegated to Adobe for your landing pages, you cannot use 'marketing2.yourcompany.com'. However, when multi-level subdomains are supported for landing pages, you may proceed using a subdomain of 'marketing1.yourcompany.com' (such as 'email.marketing1.yourcompany.com'), or a different parent domain.

    >[!CAUTION]
    >
    >If you select a domain that was delegated to Adobe using the [CNAME method](../configuration/delegate-subdomain.md#cname-subdomain-setup), you must create the DNS record on your hosting platform. To generate the DNS record, the process is the same as when you configure a new landing page subdomain.

1. Click **[!UICONTROL Submit]**.

   The subdomain is displayed in the list with the _[!UICONTROL Processing]_ status. For more on subdomains' statuses, see TBD.

    ![](assets/lp_subdomain-processing.png)

   >[!IMPORTANT]
   >
   >The subdomain is not ready for use until Adobe performs the required checks, which can take **_up to 4 hours_**.

   When the checks are successful, the subdomain is listed with the _[!UICONTROL Success]_ status and it is ready to use for creating landing page presets.
-->

### Konfigurieren einer neuen Subdomain {#lp-new-subdomain}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin_lp_subdomain_dns"
>title="Erstellen des passenden DNS-Eintrags"
>abstract="Um eine neue Landingpage-Subdomain zu konfigurieren, müssen Sie die auf der Journey Optimizer-B2B-Benutzeroberfläche angezeigten Adobe-Nameserver-Informationen kopieren und in Ihre Domain-Hosting-Lösung einfügen, um den passenden DNS-Eintrag zu generieren. Wenn die Prüfungen erfolgreich waren, kann die Subdomain zur Erstellung von Landingpage-Voreinstellungen verwendet werden."

1. Klicken Sie **[!UICONTROL Landingpage-Subdomain einrichten]**.

1. Wählen Sie für _[!UICONTROL Konfigurationstyp]_ die Option **[!UICONTROL Eigene Domain hinzufügen]**.

1. Geben Sie die zu delegierende Subdomain an.

   >[!IMPORTANT]
   >
   >* Sie können keine schon vorhandene Landingpage-Subdomain verwenden.
   >
   >* Großbuchstaben sind in Subdomains nicht zulässig.

   <!-- ![Landing page subdomain set up](./assets/config-channels-landing-pages-subdomain-setup.png){width="500" zoomable="yes"} -->

   Es ist nicht zulässig, Adobe eine ungültige Subdomain zuzuweisen. Vergewissern Sie sich, dass Sie eine gültige Subdomain eingeben, die Ihrem Unternehmen gehört, z. B. marketing.ihrunternehmen.com.

   Bei Landingpages werden mehrstufige Subdomains unterstützt. Sie können beispielsweise `email.marketing.yourcompany.com` verwenden.

1. Kopieren Sie den angezeigten Eintrag oder laden Sie eine CSV-Datei herunter und navigieren Sie dann zu Ihrer Domain-Hosting-Lösung, um den entsprechenden DNS-Eintrag zu generieren.

   Die Liste der Einträge, die auf Ihren DNS-Servern gespeichert werden sollen, wird angezeigt.

1. Stellen Sie sicher, dass der DNS-Eintrag in Ihrer Domain-Hosting-Lösung generiert wurde.

   Wenn alles ordnungsgemäß konfiguriert ist, aktivieren Sie das Bestätigungskontrollkästchen und klicken Sie auf **[!UICONTROL Senden]**.

   <!-- ![Landing page subdomain set up with DNS records](./assets/config-channels-landing-pages-subdomain-setup-dns.png){width="500" zoomable="yes"} -->

   Wenn Sie eine neue Landingpage-Subdomain konfigurieren, verweist sie immer auf einen CNAME-Eintrag.

   Wenn die Subdomain-Zuweisung übermittelt wird, wird die Subdomain in der Liste mit dem Status _[!UICONTROL Verarbeitung]_ angezeigt.

   >[!IMPORTANT]
   >
   >Die Subdomain kann erst verwendet werden, wenn Adobe die erforderlichen Prüfungen durchgeführt hat, was **_bis zu 4 Stunden)_** kann.

   Wenn die Prüfungen erfolgreich abgeschlossen wurden, wird die Subdomain mit dem Status _[!UICONTROL Erfolg]_ aufgeführt und kann für die Erstellung von Landingpage-Voreinstellungen verwendet werden.

   Die Subdomain wird als _[!UICONTROL Fehlgeschlagen“ markiert]_ wenn Sie den Validierungseintrag nicht in Ihrer Hosting-Lösung erstellt haben.

### Aufheben der Delegierung einer Subdomain {#undelegate-subdomain}

1. Heben Sie die Veröffentlichung aller mit der Subdomain verknüpften Landingpages in [!DNL Journey Optimizer] auf.

1. Wenn die Landingpage-Subdomain auf einen CNAME-Eintrag verweist, löschen Sie den CNAME-Eintrag aus Ihrer Hosting-Lösung (löschen Sie ggf. nicht die ursprüngliche E-Mail-Subdomain).

   <!--
    >[!NOTE]
    >
    >A landing page subdomain can point to a CNAME record because it was either an [existing subdomain](#lp-use-existing-subdomain) delegated to Adobe using the [CNAME method](../configuration/delegate-subdomain.md#cname-subdomain-setup), or a [new landing page subdomain](#lp-configure-new-subdomain) that you configured. 
    -->

1. Wenden Sie sich mit der Subdomain, deren Delegierung Sie aufheben möchten, an den Adobe-Support.

Nachdem Adobe Ihre Anfrage bearbeitet hat, wird auf der Subdomain-Inventarseite die nicht delegierte Domain nicht mehr angezeigt.

<!-- 
old marketo way for Prime?

A landing page subdomain should help to identify the content type, product name, or campaign, and reinforce the page authenticity. Before you configure the subdomains, define one or more CNAMEs to use for your landing pages. For example:

* **product**.[CompanyDomain].com
* **go**.[CompanyDomain].com
* **signup**.[CompanyDomain].com

In these examples, the first part (in bold) is the `LandingPageCNAME`.

Add a new subdomain for each unique brand URL that you want to host on Adobe Journey Optimizer B2B Edition. You can add a maximum number of 50 subdomains.

>[!IMPORTANT]
>
>Delegating an invalid subdomain to Adobe is not allowed. Make sure you enter a valid subdomain that your organization owns, such as _marketing.yourcompany.com_.

To review your subdomains and add new ones, go to **[!UICONTROL Administration]** > **[!UICONTROL Channels]**. Under _[!UICONTROL Landing Pages]_ in the navigation panel, select **[!UICONTROL Subdomains]**.

![Landing page subdomains](./assets/config-landing-pages-settings.png){width="800" zoomable="yes"}

_To add a landing page subdomain:_

1. Click **[!UICONTROL Add subdomain]** at the top right.

1. In the _[!UICONTROL Subdomain details]_, enter the subdomain information:

   * **[!UICONTROL Subdomain]** - The subdomain URL to use, such as `marketing.yourcompany.com`
   * **[!UICONTROL Default page]** - The URL for the default subdomain page, such as `marketing.yourcompany.com/products`
   * **[!UICONTROL Fallback page]** - The URL for the fallback page to be used if a landing page on the subdomain is not active, such as `marketing.yourcompany.com/expired`

   ![Add landing page subdomain](./assets/config-landing-pages-add-subdomain.png){width="700" zoomable="yes"}

1. Click **[!UICONTROL Save]**.

-->

## Voreinstellungen {#lp-presets}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin_config_lp_subdomain_header"
>title="Erstellen einer Landingpage-Voreinstellung"
>abstract="Um eine Landingpage erstellen und über Journey Optimizer B2B Edition nutzen zu können, müssen Sie eine Landingpage-Voreinstellung erstellen, die die zu verwendende Subdomain enthält."

Wenn Marketing-Experten eine Landingpage erstellen, müssen sie eine Landingpage-Voreinstellung auswählen, damit sie die Landingpage erstellen und über [!DNL Journey Optimizer B2B Edition] nutzen können. Die Voreinstellung enthält die Subdomain, die für die Landingpage verwendet werden soll.

Bevor Sie eine Voreinstellung konfigurieren, stellen Sie sicher, dass mindestens eine konfigurierte Landingpage-Subdomain mit dem Status _[!UICONTROL Erfolg]_ vorhanden ist.

Um sich die konfigurierten Landingpage-Voreinstellungen anzusehen, gehen Sie zu **[!UICONTROL Administration]** > **[!UICONTROL Kanäle]**. Wählen _[!UICONTROL im]_ unter „Landingpages“ die Option **[!UICONTROL Landingpage-Voreinstellungen]** aus.

<!-- ![Channel configurations - landing page presets](./assets/config-channels-landing-pages-presets.png){width="800" zoomable="yes"} -->

Klicken Sie auf einen beliebigen Voreinstellungsnamen, um auf die Voreinstellungsdetails der Landingpage zuzugreifen.

### Erstellen einer Landingpage-Voreinstellung {#lp-create-preset}

1. Klicken Sie **[!UICONTROL Landingpage-Voreinstellung erstellen]**.

1. Geben Sie einen Namen und eine Beschreibung für die Voreinstellung ein.

   Namen müssen mit einem Buchstaben (A–Z) beginnen und dürfen nur alphanumerische Zeichen, Unterstriche `_`, Punkte`.` und Bindestriche `-` enthalten.

1. Eine Landingpage-Subdomain auswählen.

   <!-- ![Landing page preset with name, description, and subdomain](./assets/config-channels-landing-pages-preset-create.png){width="500" zoomable="yes"} -->

   >[!NOTE]
   >
   >Um eine Subdomain auswählen zu können, müssen Sie zuvor mindestens eine Landingpage-Subdomain konfiguriert haben.

   Die der ausgewählten Subdomain entsprechenden Einstellungen werden angezeigt.

1. Sie können die Landingpage-Subdomain für die **[!UICONTROL Tracking-URL]** auswählen, indem Sie die Option **[!UICONTROL Gleiche Subdomain wie Landingpage]** aktivieren.

   <!-- [Learn more about tracking](../email/message-tracking.md) -->

   <!-- ![Landing page preset with subdomain settings](./assets/config-channels-landing-pages-preset-subdomain-settings.png){width="500" zoomable="yes"} -->

   Wenn beispielsweise die Landingpage-URL `pages.mail.luma.com` und die Tracking-URL `data.mail.luma.com` ist, können Sie `pages.mail.luma.com` als Tracking-Subdomain auswählen.

   <!-- 
    >[!CAUTION]
    >
    >The selected landing page subdomain is used to specify the **[!UICONTROL Tracking URL]**and **[!UICONTROL Image Delivery URL]** if that subdomain was created using an [existing subdomain](#use-an-existing-subdomain).
    >
    >If the subdomain was created using the [Add your own domain](#configure-a-new-subdomain) option, the primary subdomain (such as the first delegated subdomain) is used instead. We don't have the existing option right now.
    -->

1. Klicken Sie **[!UICONTROL Senden]**, um die Erstellung der Landingpage-Voreinstellung zu bestätigen.

   <!--You can also save the preset as draft and resume its configuration later on.-->

   Wenn die Landingpage-Voreinstellung erstellt wird, wird sie in der Liste mit dem Status _[!UICONTROL Aktiv]_ angezeigt und kann zum Erstellen von Landingpages verwendet werden.