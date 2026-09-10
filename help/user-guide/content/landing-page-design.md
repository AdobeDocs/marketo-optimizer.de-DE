---
title: Landingpage-Design
description: Entwerfen von Landingpages mit visuellen Tools - Hinzufügen von Inhaltskomponenten, Formularen, benutzerdefiniertem CSS, Personalisierung und Gerätevorschau für Personen-Journey in Marketo Optimizer.
feature: Landing Pages, Content Design Tools
role: User
TQID: 'https://experienceleague.adobe.com/zb7rXCj7iWnk8Src1sWLZaYgRa35GjqGxXXu0pTJ-ds'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2:
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 556
ht-degree: 2%

---

# Landingpage-Design

Nachdem Sie [Landingpage erstellt haben](./landing-pages-create-publish.md#create-landing-page) verwenden Sie den visuellen Design-Bereich, um die Struktur- und Inhaltskomponenten in Ihrer Seite zu erstellen.

## Hinzufügen von Struktur und Content&#x200B; {#structure-content-landing-page}

{{$include /help/_includes/content-design-components-prime.md}}

### Hinzufügen von benutzerdefiniertem CSS {#add-custom-css}

Sie können Ihr eigenes benutzerdefiniertes CSS direkt im Design-Bereich der Landingpage hinzufügen. Verwenden Sie benutzerdefiniertes CSS, um erweiterte und spezifische Stile anzuwenden, um die Flexibilität und Kontrolle über das Erscheinungsbild Ihrer Inhalte zu erhöhen. Es empfiehlt sich, diese Formatierung auf höchster Ebene hinzuzufügen, bevor Sie Komponenten wie Bilder, Schaltflächen und Text einbeziehen.

Wählen Sie bei mindestens einer Inhaltskomponente auf der Arbeitsfläche die Komponente **[!UICONTROL Hauptteil]** in der linken Navigationsstruktur aus, um auf den benutzerdefinierten CSS-Editor zuzugreifen.

![Zugriff auf Textkörperstile](assets/landing-page-body-styles-css.png){width="800" zoomable="yes"}

Anweisungen[&#x200B; Syntaxregeln und Fehlerbehebung finden Sie unter „Hinzufügen von benutzerdefiniertem &#x200B;](./design-custom-css.md) für Ihre Inhalte“.

### Hinzufügen von Assets {#add-assets}

Wählen Sie im visuellen Design-Bereich das Symbol _Assets_ ( ![Assets-Symbol](../assets/do-not-localize/icon-assets-me.svg) ) in der linken Navigationsleiste aus, um Bild-Assets in der [!DNL Marketo Optimizer] Asset-Bibliothek zu suchen und auszuwählen.

Anweisungen zum Auswählen, Ersetzen oder Hochladen von Bild-Assets finden Sie unter [Verwenden von Assets für die Inhaltserstellung](./digital-asset-management.md#assets-authoring).

### Formulare hinzufügen {#add-forms}

{{$include /help/_includes/content-design-add-forms.md}}

### Navigieren in den Ebenen, Einstellungen und Stilen {#navigate-layers-settings-styles}

{{$include /help/_includes/content-design-navigation.md}}

### Personalisieren von Inhalten {#personalize-content}

[!DNL Marketo Optimizer] verwendet die Handlebars-Syntax für die Personalisierung. Token werden bei der Anzeige der Landingpage durch Werte aus den Profildaten der einzelnen Besucher ersetzt.

_Personalisierung hinzufügen :_

1. Wählen Sie die Textkomponente aus und klicken Sie auf das Symbol _Personalisierung hinzufügen_ ( ![Personalisierungssymbol](../assets/do-not-localize/icon-personalize.svg) ) in der Symbolleiste.
1. Durchsuchen Sie im Personalisierungsdialog die Schemastruktur auf der linken Seite und wählen Sie ein Attribut aus. Der Editor fügt den entsprechenden Handlebars-Ausdruck ein.
1. Fügen Sie bei Bedarf einen Fallback-Wert hinzu, um fehlende Daten zu verarbeiten.
1. Klicken Sie **[!UICONTROL Bestätigen]** oder **[!UICONTROL Einfügen]**. Der Ausdruck wird inline im Feld angezeigt.

Weitere Informationen zu den Tools und der Syntax des Ausdruckseditors finden Sie unter [Personalization-Editor](./personalization-expressions.md).

### Verknüpftes URL-Tracking bearbeiten {#linked-url-tracking}

{{$include /help/_includes/content-design-links.md}}

![Klicken Sie auf das Symbol Bearbeiten , um auf das Linktracking zuzugreifen](assets/landing-page-link-tracking.png){width="400"}

Verwenden Sie den **[!UICONTROL Tracking-Typ]**, um das Tracking für den Link zu steuern:

* **[!UICONTROL Verfolgt]** - Aktiviert das Tracking der Link-URL.
* **[!UICONTROL Nie]** - Das Tracking der Link-URL wird nie aktiviert.

### Speichern Sie Ihre Arbeit {#save-your-work}

Klicken Sie **[!UICONTROL auf]**, um den Entwurf der Landingpage zu speichern.

Sie können die Entwurfsseite weiterhin bearbeiten. Wenn Sie bereit sind, die Seite anzuzeigen und für die Verknüpfung in einer E-Mail oder SMS-Nachricht verfügbar zu machen, können Sie die Seite veröffentlichen.

### Optionen anzeigen {#view-options}

Nutzen Sie die Ansicht- und Inhaltsvalidierungsoptionen, die im visuellen Design-Bereich verfügbar sind.

* Vergrößern/Verkleinern des Inhalts in allen vordefinierten Zoom-Optionen.

* Wechseln der Anzeige von Inhalten zwischen Desktop, Mobilgerät oder Nur-Text-/Nur-Text-Ansicht.
  * Klicken Sie auf das _Anzeigen_-Symbol für die geräteübergreifende Inhaltsvorschau.
  * Wählen Sie eines der standardmäßigen Geräte aus oder geben Sie benutzerdefinierte Dimensionen ein, um eine Vorschau des Inhalts anzuzeigen.

### Mehr Optionen {#more-options}

Im Menü _[!UICONTROL Mehr …]_ oben im visuellen Design-Bereich können Sie die folgenden Aktionen ausführen:

![Klicken Sie auf Mehr , um auf Landingpage-Aktionen zuzugreifen](assets/landing-page-designer-more-menu.png){width="500"}

* **[!UICONTROL Landingpage zurücksetzen]** - Klicken Sie auf diese Option, um die visuelle Design-Arbeitsfläche zu leeren und die Erstellung Ihres Seiteninhalts neu zu starten.
* **[!UICONTROL Design ändern]** - Kehren Sie zur Startseite von _[!UICONTROL Erstellen]_ primären Landingpage“ zurück. Dort können Sie eine andere Vorlage auswählen, um den Design-Prozess neu zu starten, oder die Seite von Grund auf auf auf einer leeren Arbeitsfläche entwerfen.
* **[!UICONTROL HTML exportieren]** - Laden Sie den Inhalt auf der visuellen Arbeitsfläche in HTML im Format herunter, das als ZIP-Datei verpackt ist.
