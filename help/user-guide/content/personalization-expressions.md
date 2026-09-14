---
title: Personalization-Editor
description: Erfahren Sie, wie Sie mit dem Personalisierungseditor in Marketo Optimizer Profilattribut-Token in E-Mails, WhatsApp-Nachrichten, Landingpages und URL-Feldern auswählen, anordnen, anpassen und validieren können.
feature: Content Design Tools
role: User
TQID: 'https://experienceleague.adobe.com/5aPDp4kMpQo7LtE6CEUQWf2IbyeSMoW6iN5ZR-f-kLI'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: '1002'
ht-degree: 55%
---
# Personalisierungseditor

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_personalization_editor"
>title="Informationen zum Personalisierungseditor"
>abstract="Mit dem Personalisierungseditor können Sie Profilattribute auswählen, anordnen, anpassen und validieren, um personalisierte Inhalte zu erstellen."

Der Personalisierungseditor ist das Herzstück der Personalisierung in [!DNL Marketo Optimizer]. Verwenden Sie sie überall dort, wo Sie dynamische Inhalte benötigen - in E-Mails, WhatsApp-Nachrichten, Landingpages und URL-Feldern.

In der Benutzeroberfläche des Personalisierungseditors können Sie Profilattribute auswählen, anordnen, anpassen und validieren, um personalisierte Inhalte zu erstellen.

![Ausdruckseditor für Personalisierung](./assets/personalization-editor.png){width="700" zoomable="yes"}

>[!NOTE]
>
>In dieser Beta-Version sind im Personalisierungseditor nur Profilattribute verfügbar. Personalisierung auf Kontoebene und Daten über benutzerdefinierte Objekte sind nicht verfügbar. Siehe [Aktuelle Einschränkungen](../marketing/email-channel.md#limitations).

Sie können Personalisierung in jedem Feld mit dem Symbol _Personalisieren_ ( ![Personalisierungssymbol](../assets/do-not-localize/icon-personalize.svg) ) hinzufügen. Erweitern Sie die folgenden Abschnitte für weitere Details.

+++E-Mails und WhatsApp-Nachrichten

In [E](./email-authoring.md#personalize-content)Mails und [WhatsApp-Nachrichten](./whatsapp-authoring.md#personalize-message-content) kann die Personalisierung an verschiedenen Stellen hinzugefügt werden, wie z. B. im Feld **[!UICONTROL Betreffzeile]** in einer E-Mail oder mit dynamischen Parametern in einer genehmigten WhatsApp-Vorlage.

Sie können sie auch in anderen Bereichen Ihres Inhalts hinzufügen, einschließlich E-Mail-Text, Preheadern und Schaltflächen-URLs.

+++

+++Inhaltsdesign-Bereich

Beim Bearbeiten visueller Inhalte können Sie die meisten Textelemente mithilfe des Symbols in der kontextuellen Symbolleiste personalisieren.

<!-- ![](assets/perso_insert.png) -->

+++

+++URLs

[!DNL Marketo Optimizer] können Sie auch **URLs** in Ihren Nachrichten personalisieren. Personalisierte URLs führen Empfangende je nach den Profilattributen zu bestimmten Seiten einer Website oder zu einer personalisierten Microsite.

<!-- ![](assets/perso-url.png){width="50%"} -->

>[!NOTE]
>
>Die Personalisierung von URLs ist für diese Link-Typen verfügbar: **Externer Link**, **Abmelde-Link** und **Ausschluss**.

+++

+++E-Mail-Konfiguration

Beim Erstellen einer [E-Mail](../admin/email-channel-configuration.md)Kanalkonfiguration können Sie personalisierte Werte für Subdomains, Header und URL-Tracking-Parameter definieren.

+++

## Hinzufügen von Personalisierung {#add}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_perso_editor_autocomplete"
>title="Automatisches Vervollständigen"
>abstract="Wenn diese Option über den Umschalter aktivieret ist, kann das System den Code während der Eingabe automatisch vervollständigen und Vorschläge unterbreiten. Diese Funktion ist nur für HTML- und Textformate verfügbar und unterstützt Profilattribute. Wenn die Option über den Umschalter deaktiviert wird, ermöglicht der Editor stattdessen die automatische Vervollständigung von nativem HTML-Code."

Im zentralen Arbeitsbereich erstellen Sie Ihre Personalisierungssyntax. Um ein Attribut zur Personalisierung Ihrer Nachricht zu verwenden, suchen Sie es im linken Navigationsbereich und klicken Sie auf die Schaltfläche `+`, um es zum Ausdruck hinzuzufügen.

<!-- ![](assets/personalization-add-attribute.png) -->

Über das Menü mit den Auslassungspunkten neben dem Symbol `+` können Sie weitere Details für jedes Attribut abrufen und Ihre am häufigsten verwendeten Attribute zu den Favoriten hinzufügen. Zu Favoriten hinzugefügte Attribute sind über das Menü **[!UICONTROL Favoriten]** im Navigationsbereich zugänglich.

>[!NOTE]
>
>Im Bereich „Attribute“ werden standardmäßig nur ausgefüllte Attribute angezeigt. Um alle Attribute anzuzeigen, wählen Sie die Schaltfläche **[!UICONTROL Einstellungen]** im Attributbereich und schalten Sie die Option **[!UICONTROL Nur ausgefüllte Attribute anzeigen]** aus.

Darüber hinaus können Sie einen standardmäßigen Fallback-Text definieren, der angezeigt wird, wenn ein Profilattribut vom Typ Zeichenfolge leer ist. Klicken Sie dazu auf die Schaltfläche mit den Auslassungspunkten neben dem Attribut und wählen Sie **[!UICONTROL Einfügen mit Fallback-Text]**. Schreiben Sie den Text, der standardmäßig angezeigt werden soll, wenn der Wert des Attributs für ein Profil leer ist, und klicken Sie dann auf **[!UICONTROL Hinzufügen]**.

<!-- ![](assets/attribute-details.png) -->

Sie können beispielsweise jeden Empfänger mit dem Vornamen begrüßen, indem Sie `{{profile.firstName}}` mit einem Fallback versehen, wenn der Wert fehlt: `{{profile.firstName | default: "there"}}`.

## Optionen für die Ausdrucksbearbeitung {#options}

Der zentrale Arbeitsbereich bietet verschiedene Tools, mit denen Sie Ihren Personalisierungsausdruck schreiben können.

<!-- ![](assets/perso-workspace.png) -->

Verfügbare Optionen sind:

1. **[!UICONTROL Suchen]**/**[!UICONTROL Suchen und Ersetzen]**: Durchsuchen Sie Ihren Ausdruck und ersetzen Sie automatisch Teile des Codes.
1. **[!UICONTROL Rückgängig machen]**/**[!UICONTROL Wiederholen]**: Machen Sie den letzten Vorgang rückgängig oder wiederholen Sie ihn.
1. **[!UICONTROL Automatisch vervollständigen]**: Vervollständigt Code automatisch während der Eingabe und unterbreitet Vorschläge. Diese Funktion ist nur für HTML- und Textformate verfügbar und unterstützt Profilattribute. Wenn die Option über den Umschalter deaktiviert wird, ermöglicht der Editor stattdessen die automatische Vervollständigung von nativem HTML-Code.

   <!-- ![](assets/perso-complete.png){width="70%" align="center" zoomable="yes"} -->

1. **[!UICONTROL HTML]**/**[!UICONTROL JSON]**/**[!UICONTROL Text]**: Identifizieren Sie das Format Ihres Codes. Dadurch kann das System die Funktion zur Validierung und automatischen Vervollständigung basierend auf der ausgewählten Sprache anpassen.
1. **[!UICONTROL Validieren]**: Überprüfen Sie die Syntax Ihres Ausdrucks.
1. **[!UICONTROL Schriftgrad]**: Passt den Schriftgrad für den Content im Editor an, um die Lesbarkeit zu verbessern.
1. **[!UICONTROL Zeilenumbruch]**: Aktiviert oder deaktiviert den Zeilenumbruch, sodass lange Ausdrücke in einer einzelnen Zeile angezeigt oder im Editor umgebrochen werden können. Zu den Optionen gehören:
   * **Aus** (Standard): Kein Zeilenumbruch. Lange Zeilen gehen über die Ansicht des Editors hinaus und erfordern einen horizontalen Bildlauf.
   * **Ein**: Passt Zeilen mit Umbrüchen an die Breite des Editors an.
   * **Zeilenumbruch-Spalte** - Bettet Zeilen ein, wenn eine Zeile 80 Zeichen erreicht.
   * **Begrenzt**: Fügt Zeilenumbrüche angepasst an die Editor-Breite oder bei Erreichen von 80 Zeichen ein, je nachdem, welcher Wert kleiner ist.
1. **[!UICONTROL Pillen]**: Attribute werden als kompakte „Pillen“ angezeigt, um die Lesbarkeit zu verbessern, indem lange Attributpfade ausgeblendet werden. Klicken Sie auf ein Attribut, um dessen vollständigen Pfad anzuzeigen.

   >[!NOTE]
   >
   >Diese Option ist nur für Profilattribute verfügbar.

Im Navigationsbereich stehen zusätzliche Funktionen zur Verfügung, mit denen Sie Ihren Personalisierungsausdruck erstellen können.

<!-- ![](assets/perso-features.png) -->

* **[!UICONTROL Hilfsfunktionen]**: Listet alle Hilfsfunktionen auf, die für die Durchführung von Datenoperationen wie Berechnungen, Datenformatierungen oder -konvertierungen, Bedingungen und die Bearbeitung von Daten im Rahmen der Personalisierung verfügbar sind.

* **[!UICONTROL Favoriten]**: Attribute, die Sie den Favoriten hinzugefügt haben, werden in dieser Liste angezeigt. Auf diese Weise können Sie schnell auf Ihre am häufigsten verwendeten Elemente zugreifen. Um ein Attribut zu Ihren Favoriten hinzuzufügen, klicken Sie auf das Menü mit den Auslassungspunkten und wählen Sie **[!UICONTROL Zu Favoriten hinzufügen]** aus.

Der Mitarbeiter kann Handlebars-Ausdrücke aus Beschreibungen in einfacher Sprache generieren, vorhandene Ausdrücke erklären und potenzielle Probleme identifizieren.

Wenn Ihr Personalisierungsausdruck fertig ist, klicken Sie auf **[!UICONTROL Bestätigen]** oder **[!UICONTROL Einfügen]** um ihn zu Ihrem Inhalt hinzuzufügen.

## Mechanismen der Validierung {#validation-mechanisms}

Die Validierung Ihres Ausdrucks wird automatisch ausgeführt, wenn Sie auf **[!UICONTROL Bestätigen]** oder **[!UICONTROL Einfügen]** klicken, um den Editor zu schließen. Sie können auch auf **[!UICONTROL Validieren]** klicken, um Ihre Personalisierungssyntax vor dem Schließen zu überprüfen.

Informationen zu Inhaltswarnhinweisen, die die Journey-Aktivierung blockieren, finden Sie unter [Validieren von E-Mail-Inhalten](./email-authoring.md#validation).

Erweitern Sie den folgenden Abschnitt, um häufige Fehler bei der Validierung der Personalisierung anzuzeigen.

+++Häufige Fehler

* **Pfad „XYZ“ nicht gefunden**

Dieser Fehler tritt auf, wenn Sie auf ein Feld verweisen, das nicht im Schema definiert ist.

In diesem Fall **firstName1** nicht als Attribut im Profilschema definiert:

```handlebars
{{profile.firstName1}}
```

* **Typ für Variable „XYZ“ stimmt nicht überein. Array erwartet, Zeichenfolge gefunden.**

Dieser Fehler tritt auf, wenn Sie versuchen, über eine Zeichenfolge statt über ein Array zu iterieren.

In diesem Fall **jobTitle** eine Zeichenfolge, kein Array:

```handlebars
{{#each profile.jobTitle as |item|}}
  {{item}}
{{/each}}
```

* **Ungültige Handlebars-Syntax.`'[XYZ}}'`** gefunden

Dieser Fehler tritt auf, wenn eine ungültige Handlebars-Syntax verwendet wird.

```handlebars
{{[profile.firstName}}
```

+++
