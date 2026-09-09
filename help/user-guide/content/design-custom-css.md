---
title: Hinzufügen von benutzerdefiniertem CSS für Inhalte
description: Hinzufügen von benutzerdefiniertem CSS zu E-Mails und Landingpages für erweiterte Formatierung und präzise Designkontrolle über Standardkomponenten in Marketo Optimizer hinaus.
feature: Content Design Tools, Email Authoring, Landing Pages
role: User
TQID: 'https://experienceleague.adobe.com/RLYXBvEepwNcQ9B9W3Sao-RP49HtbxFomlgu7R8APAg'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c1579802-ddd4-4214-8a91-97b2066abe11id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 561
ht-degree: 9%

---

# Hinzufügen von benutzerdefiniertem CSS für Inhalte

Sie können Ihr eigenes benutzerdefiniertes CSS direkt im E-Mail- oder Landingpage-Design-Bereich hinzufügen. Verwenden Sie benutzerdefiniertes CSS, um erweiterte und spezifische Stile anzuwenden, um die Flexibilität und Kontrolle über das Erscheinungsbild Ihrer Inhalte zu erhöhen.

Das benutzerdefinierte CSS wird innerhalb eines `<style>`-Tags mit dem `data-name="global-custom"`-Attribut an den `<head>`-Abschnitt angehängt. Diese Struktur stellt sicher, dass die benutzerdefinierten Stile global auf den Inhalt angewendet werden.

+++ Beispielimplementierung

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="content-version" content="3.3.31">
    <meta name="x-apple-disable-message-reformatting">
    <meta name="viewport" content="width=device-width,initial-scale=1.0">
    <style data-name="default" type="text/css">
      td { padding: 0; }
      th { font-weight: normal; }
    </style>
    <style data-name="grid" type="text/css">
      .acr-grid-table { width: 100%; }
    </style>
    <style data-name="acr-theme" type="text/css" data-theme="default" data-variant="0">
      body { margin: 0; font-family: Arial; }
    </style>
    <style data-name="media-default-max-width-500px" type="text/css">
      @media screen and (max-width: 500px) {
        body { width: 100% !important; }
      }
    </style>
    <style data-name="global-custom" type="text/css">
      /* Add you custom CSS here */
    </style>
  </head>
  <body>
    <!-- Minimal content -->
  </body>
</html>
```

+++

>[!NOTE]
>
>Das benutzerdefinierte CSS wird für eine ausgewählte Komponente im Bedienfeld _[!UICONTROL Stile]_ nicht angezeigt oder validiert. Sie ist völlig unabhängig und kann nur durch die Option [!UICONTROL Benutzerdefiniertes CSS hinzufügen] auf der Ebene der Hauptteilkomponente geändert werden.

## Hinzufügen von benutzerdefiniertem CSS

1. Wenn mindestens eine Inhaltskomponente auf der Arbeitsfläche hinzugefügt wurde, wählen Sie die **[!UICONTROL Hauptteil]** in der linken Navigationsleiste aus.

1. Wählen Sie auf _rechten Seite die_ „Stile“ und klicken Sie auf **[!UICONTROL Benutzerdefiniertes CSS hinzufügen]**.

   ![Zugriff auf Textkörperstile](assets/email-body-styles.png){width="800" zoomable="yes"}

   >[!NOTE]
   >
   >Die Schaltfläche _[!UICONTROL Benutzerdefiniertes CSS hinzufügen]_ ist nur verfügbar, wenn die Komponente _[!UICONTROL Hauptteil]_ ausgewählt ist. Sie können jedoch benutzerdefinierte CSS-Stile auf alle darin enthaltenen Komponenten anwenden.

   Der _[!UICONTROL Benutzerdefinierte CSS hinzufügen]_ Popup-Editor wird mit Platzhalter-Code-Kommentaren angezeigt.

1. Geben Sie Ihren CSS-Code im Editor ein.

   Stellen Sie sicher, dass das benutzerdefinierte CSS gültig ist und der richtigen Syntax folgt. Wenn die eingegebene CSS-Datei ungültig ist, wird eine Fehlermeldung angezeigt und die CSS-Datei kann nicht gespeichert werden. Weitere Informationen finden Sie unter [CSS-Gültigkeit](#css-validity).

   ![Benutzerdefiniertes CSS im Editor eingeben](assets/content-design-add-custom-css.png){width="450"}

1. Klicken Sie **[!UICONTROL Speichern]**, um das benutzerdefinierte CSS zu speichern.

   Das benutzerdefinierte Stylesheet wird auf den vorhandenen Inhalt angewendet. Sie können überprüfen, ob Ihr benutzerdefiniertes CSS Ihren Anforderungen entspricht. Informationen zum Vornehmen von Änderungen und Anpassen der Stylesheet-Anwendung finden Sie unter [Fehlerbehebung](#troubleshooting).

   ![Benutzerdefiniertes CSS auf Inhalte angewendet](assets/email-body-custom-css-applied.png){width="600" zoomable="yes"}

## CSS-Gültigkeit {#css-validity}

>[!CAUTION]
>
>Benutzende sind für die Sicherheit ihres benutzerdefinierten CSS verantwortlich. Stellen Sie sicher, dass durch Ihr CSS keine Sicherheitslücken entstehen und dass es nicht mit dem vorhandenen Content in Konflikt steht.
>
>Vermeiden Sie die Verwendung von CSS, das unbeabsichtigt das Layout oder die Funktionen des Contents beeinträchtigen könnte.

+++ Beispiele für gültiges CSS

```css
.acr-component[data-component-id="form"] {
  display: flex;
  justify-content: center;
  background: none;
}

.acr-Form {
  width: 100%;
  padding: 20px 100px;
  border-spacing: 0px 8px;
  box-sizing: border-box;
  margin: 0;
}

.acr-Form .spectrum-FieldLabel {
  width: 20%;
}

.acr-Form.spectrum-Form--labelsAbove .spectrum-FieldLabel,
.acr-Form [data-form-item="checkbox"] .spectrum-FieldLabel {
  width: auto;
}

.acr-Form .spectrum-Textfield {
  width: 100%;
}

#acr-form-error,
#acr-form-confirmation {
  width: 100%;
  padding: var(--spectrum-global-dimension-static-size-500);
  display: flex;
  align-items: center;
  flex-direction: column;
  justify-content: center;
  gap: var(--spectrum-global-dimension-static-size-200);
}

.spectrum-Form-item.is-required .spectrum-FieldLabel:after{
  content: '*';
  font-size: 1.25rem;
  margin-left: 5px;
  position: absolute;
}

/* Error field placeholder */
.spectrum-HelpText {
  display: none !important;
}

.spectrum-HelpText.is-invalid,
.is-invalid ~ .spectrum-HelpText {
  display: flex !important;
}
```

```css
@media only screen and (min-width: 600px) {
  .acr-paragraph-1 {
    width: 100% !important;
  }
}
```

+++

+++ Beispiele für ungültiges CSS

Die Verwendung von `<style>`-Tags wird nicht akzeptiert:

```html
<style type="text/css">
  .acr-Form {
    width: 100%;
    padding: 20px 100px;
    border-spacing: 0px 8px;
    box-sizing: border-box;
    margin: 0;
  }
</style>
```

Ungültige Syntax wie fehlende Klammern wird nicht akzeptiert:

```css
body {
  background: red;
```

+++

## CSS in importierten Inhalten {#imported-content}

Wenn Sie benutzerdefiniertes CSS mit Inhalten verwenden möchten, die in den Design-Bereich für E-Mails oder Landingpages importiert wurden, sollten Sie Folgendes beachten:

* Wenn Sie externe HTML-Inhalte einschließlich CSS importieren, werden diese im [!UICONTROL Kompatibilitätsmodus] aufgefüllt und der Abschnitt [!UICONTROL CSS-]&quot; ist nicht verfügbar.

* Wenn Sie Inhalte importieren, die ursprünglich im Design-Bereich der E-Mail oder Landingpage mit der Option [!UICONTROL Benutzerdefiniertes CSS hinzufügen] erstellt wurden, ist die angewendete CSS-Datei von derselben Option aus sichtbar und bearbeitbar.

## Fehlerbehebung {#troubleshooting}

Wenn Ihr benutzerdefiniertes CSS nicht wie erwartet angewendet wird, verwenden Sie die Browser-Entwickler-Tools, um den Inhalt zu überprüfen und sicherzustellen, dass Ihr CSS auf die richtigen Selektoren abzielt. Beachten Sie beim Überprüfen des Stilcodes Folgendes:

* Überprüfen Sie, ob Ihr CSS gültig und frei von Syntaxfehlern (z. B. fehlende Klammern, falsche Eigenschaftsnamen) ist.

* Vergewissern Sie sich, dass Ihre CSS-Datei dem `<style>`-Tag mit dem `data-name="global-custom"` hinzugefügt wurde.

* Überprüfen Sie, ob für das Stil-Tag des `global-custom` das Attribut auf „true“ festgelegt `data-disabled`, z. B.:

  `<style data-name="global-custom" type="text/css" data-disabled="true"> body: { color: red; } </style>`

* Vergewissern Sie sich, dass Ihr CSS nicht an einer beliebigen Stelle im Inhalt überschrieben wird, z. B. beim Anwenden von Inline-Stilen.

* Fügen Sie Ihren -Deklarationen `!important` hinzu, um sicherzustellen, dass sie Vorrang haben, z. B.:

  ```
  .acr-Form {
  background: red !important;
  }
  ```
