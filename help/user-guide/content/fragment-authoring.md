---
title: Erstellen von Fragmenten
description: Erstellen wiederverwendbarer Inhaltsfragmente mit visuellen Design-Tools - Hinzufügen von Struktur, Assets, Personalisierung, bedingten Inhalten und Linktracking-URLs für E-Mails und Vorlagen in Marketo Optimizer.
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 3%

---

# Erstellen von Fragmenten

Nachdem Sie [ein Fragment erstellt haben](./fragments.md#create-fragments) verwenden Sie den visuellen Design-Bereich, um die Struktur- und Inhaltskomponenten in Ihrem Fragment zu erstellen.

## Hinzufügen von Struktur und Inhalten {#design-fragment}

{{$include /help/_includes/content-design-components-prime.md}}

## Hinzufügen von Assets {#add-assets}

Wählen Sie im visuellen Design-Bereich das Symbol _Assets_ ( ![Assets-Symbol](../assets/do-not-localize/icon-assets-me.svg) ) in der linken Navigationsleiste aus, um Bild-Assets in der [!DNL Marketo Optimizer] Asset-Bibliothek zu suchen und auszuwählen.

Anweisungen zum Auswählen, Ersetzen oder Hochladen von Bild-Assets finden Sie unter [Verwenden von Assets für die Inhaltserstellung](./digital-asset-management.md#assets-authoring).

## Navigieren in den Ebenen, Einstellungen und Stilen {#navigate-layers-settings-styles}

{{$include /help/_includes/content-design-navigation.md}}

## Personalisieren von Inhalten {#personalize-content}

[!DNL Marketo Optimizer] verwendet die Handlebars-Syntax für die Personalisierung. Token werden zum Zeitpunkt des Versands durch Werte aus den Profildaten jedes Empfängers ersetzt.

_Personalisierung hinzufügen :_

1. Wählen Sie die Textkomponente aus und klicken Sie auf das Symbol _Personalisierung hinzufügen_ ( ![Personalisierungssymbol](../assets/do-not-localize/icon-personalize.svg) ) in der Symbolleiste.
1. Durchsuchen Sie im Personalisierungsdialog die Schemastruktur auf der linken Seite und wählen Sie ein Profilattribut aus. Der Editor fügt den entsprechenden Handlebars-Ausdruck ein, z. B. `{{profile.firstName}}`.
1. Fügen Sie bei Bedarf einen Fallback-Wert hinzu, um fehlende Daten zu verarbeiten - z. B. `{{profile.firstName | default: "there"}}`.
1. Klicken Sie **[!UICONTROL Bestätigen]** oder **[!UICONTROL Einfügen]**. Der Ausdruck wird inline im Feld angezeigt.

Weitere Informationen zu den Tools und der Syntax des Ausdruckseditors finden Sie unter [Personalization-Editor](./personalization-expressions.md).

## Verknüpftes URL-Tracking bearbeiten {#edit-linked-url-tracking}

{{$include /help/_includes/content-design-links.md}}
