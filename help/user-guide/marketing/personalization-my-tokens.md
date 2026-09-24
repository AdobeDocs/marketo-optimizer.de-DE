---
title: Benutzerdefinierte Token für Personalization
description: Erstellen und verwalten Sie benutzerdefinierte „Meine Token“ für die dynamische Personalisierung Ihrer Marketing-Artefakte - definieren Sie Text- und Zahlenvariablen für Programme in Marketo Optimizer.
TQID: 'https://experienceleague.adobe.com/utVM69g7aQSuF-V3XQIdVBqvBXyiDz1ZWr0WtE67UCg'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
  - id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4
    internal-label: Programs
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 177e7c3d0806febd730104b19787ba3cbea2914a
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 3%
---
# Benutzerdefinierte Token für die Personalisierung

Die Inhaltspersonalisierung verwendet Token als Platzhalter oder Variablen, die beim Generieren des Inhaltsartefakts aufgefüllt werden. Standard-Personalisierungs-Token sind für E-Mails, Landingpages, Fragmente und Vorlagen verfügbar. Sie können auch einen Satz benutzerdefinierter Token mit Werten definieren, die für das Programm oder den Ordner spezifisch sind. Dieser Satz benutzerdefinierter Token wird als &quot;_Token“_. Alle diese benutzerdefinierten Token können personalisiert werden.

<!-- 
When you add a custom token to an email, it is displayed as `{{my.TokenName}}`. For example, you might have `{{my.EventDate}}` or `{{my.WebinarSpeaker}}` tokens created to manage email content related to upcoming webinars in your program.
-->

Zusätzlich zu _Meine Token_ die spezifisch für das Programm oder den Ordner sind, können Sie jedes der standardmäßigen (integrierten) Token für die Personalisierung verwenden.

>[!IMPORTANT]
>
>In der ersten Marketo Optimizer-Version _Meine Token_ für die Aktionsknoten zum Ändern des Datenwerts unterstützt und sind auf die Verwendung in Zeichenfolgen- und Textattributen beschränkt. _Meine Token_ sind **nicht** derzeit im Personalization-Editor aktiviert.

## Zugriffstoken {#access-tokens}

1. Erweitern Sie in der linken Navigation **[!UICONTROL Marketing-Verwaltung]**.

1. Wählen Sie rechts in der **[!UICONTROL Marketing]**-Ressourcenliste **[!UICONTROL Programme]** aus.

1. Wählen Sie in der Baumstruktur das Programm oder den Ordner aus, um die Details im mittleren Arbeitsbereich zu öffnen.

1. Klicken Sie auf die **[!UICONTROL Token]**.

   ![Registerkarte Token im ausgewählten Programm](./assets/program-tokens-tab.png){width="800" zoomable="yes"}

   Auf der Registerkarte werden alle benutzerdefinierten Token angezeigt, die im Ordner oder Programm definiert sind, sowie alle für übergeordnete Ordner oder Programme definierten.

### Tokentypen {#my-tokens}

Die _Meine Token_ sind benutzerdefinierte Variablen, die Sie für ein Programm oder einen Ordner erstellen oder ändern. Dieser benutzerdefinierte Token-Satz unterstützt die folgenden Token-Typen:

| Token-Typ | Beschreibung |
| ---------- | ----------- |
| Text | Dieser Typ enthält eine standardmäßige Textzeichenfolge. Die Größenbeschränkung für Text-Token beträgt 524.288 Zeichen (UTF-8) oder 2 MB. |
| Datum | Dieser Typ enthält einen Datumswert. Das Datum wird als Monat-Tag-Jahr angezeigt (z. B. 09-23-2026). |
| Datum und Uhrzeit | Dieser Typ enthält einen Datums- und Uhrzeitwert. |
| Zahl | Dieser Typ enthält einen ganzzahligen Standardwert. |
| E-Mail | Dieser Typ enthält eine gültige E-Mail-Adresse. |
| Ergebnis | Verwenden Sie dieses Token, um die Punktzahl für einen Journey-Aktionsknoten zu ändern. |
| Boolesch | Dieser Typ enthält den booleschen Standardwert true oder false. |
| RTF | Dieser Typ enthält formatierten Text. |

### Token-Verschachtelung {#nesting}

Wenn Sie ein Token in einem Programm oder Ordner erstellen, ist es für Verweise durch Objekte innerhalb der Hierarchie verfügbar.

* **Lokales**: Das Token wird im selben Programm oder Ordner definiert.
* **Vererbtes Token** - Das Token wird in einem übergeordneten Programm oder Ordner definiert und liegt eine oder mehrere Ebenen über dem aktuellen Programm oder Ordner.
* **Überschriebenes Token** - Das Token wird in einem übergeordneten Programm oder Ordner definiert, aber im aktuellen Programm oder Ordner wird ein anderer Wert definiert. Der Token-Status ändert sich in _Überschrieben_ und alle untergeordneten Ordner, Programme und Marketing-Artefakte übernehmen den neuen Wert.

![Token-Typen und Vererbung](./assets/program-tokens-inherited-overridden.png){width="600" zoomable="yes"}

### Erstellen eines Tokens {#create}

1. Klicken Sie auf der _[!UICONTROL Token]_-Registerkarte auf **[!UICONTROL Erstellen]**.

1. Geben Sie im Dialogfeld den **[!UICONTROL Namen]** für das Token ein.

   ![Geben Sie einen Namen und einen Wert für das Text-Token ein](./assets/token-create-dialog.png){width="400"}

   Sie können im Token-Namen keine Leerzeichen oder Sonderzeichen verwenden. Sie können _Binnenmajuskel-Schreibweise_ wie `EventType` verwenden, um einen Namen mit mehreren Wörtern zu verwenden, der leicht zu identifizieren ist.

1. Wählen Sie den **[!UICONTROL Typ]** für das Token.

1. Legen Sie den **[!UICONTROL Wert]** für das Token fest.

1. Klicken Sie auf **[!UICONTROL Erstellen]**.

### Token bearbeiten {#edit}

Sie können den Wert für jedes der definierten Token bearbeiten, wodurch der Wert für ein geerbtes Token überschrieben wird.

<!-- (How does this affect live person journeys? ) -->

1. Klicken Sie auf _[!UICONTROL Token]_ auf das Symbol _Bearbeiten_ neben dem Token-Namen.

1. Ändern Sie im Feld den Wert nach Bedarf.

   ![Ändern Sie den Namen und den Wert für das Token](assets/my-tokens-edit-text-token-dialog.png){width="400"}

1. Klicken Sie auf das _Speichern_-Symbol.

### Token löschen {#delete}

Sie können ein benutzerdefiniertes Token aus der Liste löschen, wenn es derzeit nicht zum Journey von E-Mail-Inhalten verwendet wird.

1. Klicken Sie auf _[!UICONTROL Token]_ auf das Symbol _Löschen_ neben dem Token-Namen.

1. Klicken Sie im Bestätigungsdialog auf **[!UICONTROL Löschen]**.

## AutoSuggest und Preview {#autosuggest}

Wenn Sie einen _Datenwert ändern_-[-Knoten ](./action-nodes.md) Ihrem Journey einfügen, können Sie `{{` in das Feld **[!UICONTROL Neuer Wert]** eingeben, um das Menü Token _AutoSuggest_ anzuzeigen. In der angezeigten Liste werden unterstützte Namespaces und einzelne Token angezeigt. Es werden nur Token eines kompatiblen Datentyps aufgelistet.

Bei _Meine Token_ wird eine Vorschau des Token-Werts mit dem Token-Namen angezeigt, um die Auswahl des richtigen Werts zu vereinfachen.

![Syntax im Feld Neuer Wert, um das Menü für automatische Vorschläge für Token anzuzeigen](./assets/program-tokens-change-data-value-autosuggest.png){width="500" zoomable="yes"}

<!--

## Use custom tokens in your content

When you are authoring email content for your programs, you can use any of the tokens from the _My Tokens_ list when you use the personalization tools in the visual design space.

1. Select the text component and click the _Add personalization_ ( ![Add personalization icon](../assets/do-not-localize/icon-personalization-field.svg) ) icon in the toolbar.

   ![Click the Add personalization icon](assets/email-personalize-text.png){width="600"}

   This action opens the _Edit Personalization_ dialog. The dialog includes a _[!UICONTROL My tokens]_ folder in the _[!UICONTROL Personalization Tokens]_ library if there are custom tokens defined for the account journey.

1. To add one of your custom tokens to the blank space, expand the **[!UICONTROL My tokens]** folder, then click **+** or **...**.

   You can add any additional static text as needed.

   ![Construct personalized text using My tokens](assets/personalization-edit-dialog-my-tokens.png){width="700" zoomable="yes"}

1. Click **[!UICONTROL Save]**.

-->
