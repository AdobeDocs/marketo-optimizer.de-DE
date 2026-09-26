---
title: Persona-Zuordnung
description: Erfahren Sie, wie Sie in Marketo Optimizer die Persona-Zuordnung einrichten. Ordnen Sie Personenattribute zu, um Personas zu definieren, und verwenden Sie die Filterung abgeleiteter Personas in Personenlisten und Journey von Personen.
TQID: 'https://experienceleague.adobe.com/JCBtJN4DgQZROVDamM4eKuCiGTwJQPQY3wMxmBPFj74'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 46e599c6-e20f-5f67-9824-93415016f66b
    internal-label: Audiences
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
  - id: a659ad61-de21-559d-a901-02e2fb329ff5
    internal-label: Administration
  - id: d4203578-d294-5145-b397-f26f4488a904
    internal-label: Channels
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: fd79d458ef033e4485ba5e8a8c8fbe56b7cd559b
workflow-type: tm+mt
source-wordcount: '1287'
ht-degree: 1%
---
# Persona-Mapping

Personas sind ein wichtiger Aspekt in einem Account-Based Marketing (ABM)-Ansatz, da sie Marketing-Experten dabei helfen, ihre Strategien an die spezifischen Bedürfnisse, Präferenzen und Schmerzpunkte von Personen in Zielkonten anzupassen. Marketing-Experten können für jede Rolle ein detailliertes Profil erstellen, einschließlich Hintergrund, Zuständigkeiten, Probleme und bevorzugter Kommunikationskanäle. Mit diesen Definitionen können Admins Personas anhand von Personenattributen in [!DNL Adobe Marketo Optimizer] konfigurieren, sodass Personenlisten und Journey optimierte und konsistente Filter verwenden können, mit denen diese Personas erfasst werden.

In [!DNL Marketo Optimizer] bietet die Zuordnung von Rollen eine zusätzliche Funktion, die über die Bedingungen von Rollenvorlagen hinausgeht: Sie können [Personenlisten](../audiences/people-lists.md) und [Personen-Journey](../marketing/person-journeys.md) mithilfe von **[!UICONTROL Abgeleitete Persona]** als Filterkriterium filtern. Eine _abgeleitete Persona_ ist die Persona, die das System für einen Personendatensatz ableitet, indem es seine Attribute mit allen konfigurierten Persona-Definitionen vergleicht.

Definition der Persona und Nutzungsbeschränkungen:

* Es können bis zu 20 Personas in der Liste „Persona _[!UICONTROL Zuordnung“ definiert]_.
* Jede Rolle kann bis zu fünf Attribute in ihre Definition aufnehmen.
* Sie können für alle definierten Personas bis zu zehn verschiedene Personenattribute verwenden.

>[!BEGINSHADEBOX]

**Anwendungsfall: Varianten der Auftragstitel**

Viele Marketing- und Verkaufsteams verwenden Jobtitel als Möglichkeit, verschiedene Rollen innerhalb eines Kontos zu identifizieren. Titel für Kontakte können jedoch inkonsistent sein und zahlreiche Varianten für ähnliche Rollen verwenden. Beim Erstellen von Personenlistenfiltern oder Personen-Journey-Zielgruppenbedingungen müssen Sie möglicherweise jede mögliche zugehörige Stellenbezeichnung für eine bestimmte Rolle definieren. Sie können diese Definitionen vereinfachen und Personen mit ähnlichen Berufsbezeichnungen unter einer abgeleiteten Rolle gruppieren, die Sie dann ansprechen können, indem Sie nach „Abgeleitete _ist Führung“ filtern_ anstatt einzelne Werte für die Berufsbezeichnung abzugleichen.

>[!ENDSHADEBOX]

## Zugreifen auf die konfigurierten Personas {#access}

Öffnen Sie das Bedienfeld _Persona-_&quot; über die [-Oberfläche &#x200B;](../agents/chat-interface.md).

1. Geben Sie im Chatbedienfeld `/persona-mapping` ein und drücken Sie die **Eingabetaste**.

   Dieser Befehl ist ein Navigationsbefehl, der unter **[!UICONTROL Seite öffnen]** im Schrägstrich aufgeführt ist.

   ![Screenshot des Schrägmenüs der Chat-Oberfläche mit dem Befehl /persona-mapping unter Seite öffnen.](assets/persona-mapping-open-chat.png){width="800" zoomable="yes"}

1. Coworker öffnet das Bedienfeld **[!UICONTROL Persona-Zuordnung]** als Registerkarte Workspace und zeigt die Liste der Personas an.

   In diesem Bedienfeld können Sie [erstellen](#create-a-persona), [bearbeiten](#edit-a-persona) oder [löschen](#delete-a-persona).

   Die Personalliste ist als Tabelle organisiert, die den jeweiligen Personennamen, das Erstellungsdatum und das Datum der letzten Änderung enthält. <!-- You can customize the displayed table by clicking the _Column settings_ ( ![Column settings](../assets/do-not-localize/icon-column-settings.svg) ) icon in the top-right corner and selecting or clearing the column checkboxes. --> Sie können das Chat-Bedienfeld minimieren, um die Größe des Bedienfelds _Persona-Zuordnung_ zu erhöhen.

   ![Das Bedienfeld „Persona-Zuordnung“ mit einer Tabelle mit Standardpersonas und der Schaltfläche „Persona erstellen“.](assets/persona-mapping-list.png){width="700" zoomable="yes"}

1. Um auf die Details einer Rolle zuzugreifen, klicken Sie auf den Namen.

### Standard-Personas

Die _Persona-Zuordnung_ enthält zehn standardmäßige Personas, die gemäß dem Attribut für die Auftragstitel definiert sind. Sie können jede dieser Standardpersonas entsprechend den Anforderungen Ihres Unternehmens bearbeiten:

| Persona | Stellenbezeichnungen |
| ------- | ---------- |
| CXO/EVP | CEO, CIO, CTO, CMO, CFO, Executive Vice President of Strategy |
| SVP/VP | SVP Marketing, VP Sales, SVP Operations, VP Product, VP IT |
| Senior Director/Director | Director of Engineering, Senior Director of Product, Director of Finance, Director of Customer Success |
| Senior Manager | Senior Marketing Manager, IT Manager, Operations Manager, Sales Manager, HR Manager |
| Einzelner Beitragender | Kundenbetreuer, Software-Ingenieur, Marketing-Spezialist, Customer Success-Vertreter |
| Analytiker | Business Analyst, Data Analyst, Market Research Analyst, Financial Analyst, Operations Analyst |
| Entwickler | Frontend-Entwickler, Backend-Entwickler, Full-Stack-Entwickler, Mobile-App-Entwickler, DevOps-Ingenieur |
| Professionelles Personal | HR Specialist, Legal Counsel, Compliance Officer, Project Manager, Procurement Specialist |
| Berater | Unternehmensberater, IT-Berater, Business Process Consultant, Marketing Consultant |
| Andere | Branchenspezialist, unabhängiger Berater, freiberuflicher Berater, Fachexperte |

### Filtern von Listen

Um die gewünschte Persona zu finden, geben Sie eine Textzeichenfolge in die Suchleiste ein, um Personas anhand des Namens zuzuordnen.

![Suchfeld, das die Rollenliste nach Namen filtert und zwei übereinstimmende Ergebnisse anzeigt.](assets/configuration-persona-mapping-search.png){width="680" zoomable="yes"}

## Persona erstellen {#create-a-persona}

1. Klicken Sie **[!UICONTROL Persona erstellen]**.

1. Geben Sie einen eindeutigen **[!UICONTROL Namen]** und **[!UICONTROL Beschreibung]** (optional) für die Rolle ein.

   ![Erstellen Sie ein persönliches Bedienfeld mit Feldern Name und Beschreibung und einem Abschnitt Regeln zur Auswahl von Attributen.](assets/configuration-persona-mapping-new.png){width="680" zoomable="yes"}

1. Wählen **[!UICONTROL unter „Regeln]** die Attribute aus, die für die Zuordnung der Rolle verwendet werden sollen.

   * Klicken Sie **[!UICONTROL Regeln bearbeiten]**.

   * Aktivieren Sie im Dialogfeld das Kontrollkästchen für jedes Attribut, das Sie zuordnen möchten (maximal fünf).

     Sie können die angezeigte Tabelle anpassen, indem Sie auf das Symbol _Spalteneinstellungen_ ( ![Spalteneinstellungen](../assets/do-not-localize/icon-column-settings.svg) ) in der oberen rechten Ecke klicken.

     Um die Attributliste nach Namen zu filtern, geben Sie eine Textzeichenfolge in die Suchleiste ein. Sie können auch auf das Symbol _Filter_ ( ![Filtersymbol](../assets/do-not-localize/icon-filter.svg) ) oben links klicken, um die angezeigte Liste nach Typ, _Standard_ oder _Benutzerdefiniert_ zu filtern.

     ![Dialogfeld, in dem Personenattribute mit Kontrollkästchen, Nutzungsstatus und Spalten vom Typ „Attribut“ aufgelistet werden.](assets/configuration-persona-mapping-select-attributes.png){width="450" zoomable="yes"}

   * Klicken Sie auf **[!UICONTROL Fertig]**.

     Die ausgewählten Attribute werden im Abschnitt &quot;_[!UICONTROL -Attribute]_ ausgefüllt.

   * Geben Sie für jedes Attribut die kommagetrennten Werte ein, denen Sie für das Attribut entsprechen möchten.

1. Klicken Sie **[!UICONTROL Persona erstellen]**.

## Persona bearbeiten {#edit-a-persona}

Klicken Sie auf den Personennamen, um auf die Details der Rolle zuzugreifen und sie zu bearbeiten.

Sie können den Namen oder die Beschreibung ändern, Attribute hinzufügen oder die Attributwerte aktualisieren. Klicken Sie **[!UICONTROL Senden]** wenn Ihre Änderungen abgeschlossen sind.

## Persona löschen {#delete-a-persona}

Wenn Sie eine Rolle löschen, wird sie aus der Liste _Persona-Zuordnung_ entfernt und ist nicht mehr als abgeleiteter Personenfilter in Personenlisten oder Journey-Listen verfügbar.

1. Suchen Sie auf _[!UICONTROL Seite]_ Persona-Zuordnung“ die Persona, die Sie löschen möchten.

1. Klicken Sie neben dem Namen auf die Auslassungspunkte (**…**) und wählen Sie **[!UICONTROL Löschen]**.

1. Klicken Sie im Bestätigungsdialog auf **[!UICONTROL Löschen]**.

## Nach abgeleiteter Persona filtern {#derived-persona-filter}

Nachdem Personas konfiguriert wurden, leitet [!DNL Marketo Optimizer] für jeden Personendatensatz eine Persona ab, indem die Attribute des Datensatzes mit den definierten Persona-Zuordnungen verglichen werden. Sie können das abgeleitete Ergebnis - die _abgeleitete Persona_ - als Filter verwenden, wenn Sie die Audience für eine Personen-Liste oder eine Personen-Journey definieren.

Der Filter Abgeleitete Persona wird im Filterbedienfeld unter der Kategorie **[!UICONTROL Personenattribute]** zusammen mit anderen abgeleiteten Attributen wie z. B. der Journey-Mitgliedschaft angezeigt.

### Personenlisten

Um Personen anzusprechen, die bei der Verwaltung von Personenlisten einer bestimmten konfigurierten Rolle entsprechen, können Sie nach abgeleiteter Rolle filtern.

**Statische Liste - Mitglieder hinzufügen**

1. Öffnen Sie die statische Liste und klicken Sie **[!UICONTROL oben]** auf „Personen hinzufügen“.

1. Erweitern Sie im Filterdialogfeld **[!UICONTROL Personenattribute]** und ziehen Sie **[!UICONTROL Abgeleitete Persona]** auf die Arbeitsfläche.

   Sie können auch den Filternamen in das Suchfeld eingeben, um ihn schnell zu finden.

   ![Abgeleiteter Rollenfilter wurde zur Arbeitsfläche des Personenlisten-Filters hinzugefügt und bietet Personenoptionen zur Auswahl.](assets/persona-mapping-derived-persona-filter.png){width="680" zoomable="yes"}

1. Wählen Sie in der Filterbedingung **[!UICONTROL ist]** und wählen Sie eine oder mehrere Rollen aus der Liste aus.

1. Klicken Sie **[!UICONTROL Fertig]**, um den Filter anzuwenden und passende Personen für die Liste zu qualifizieren.

**Dynamische Liste - Festlegen von Mitgliedschaftsregeln**

1. Öffnen Sie die dynamische Liste und wählen Sie die Registerkarte **[!UICONTROL Regeln]** aus.

1. Klicken Sie **[!UICONTROL Regeln bearbeiten]**.

1. Erweitern Sie im Filterdialogfeld **[!UICONTROL Personenattribute]** und ziehen Sie **[!UICONTROL Abgeleitete Persona]** auf die Arbeitsfläche.

   Sie können auch den Filternamen in das Suchfeld eingeben, um ihn schnell zu finden.

1. Wählen Sie in der Filterbedingung **[!UICONTROL ist]** und wählen Sie eine oder mehrere Rollen aus der Liste aus.

1. Klicken Sie **[!UICONTROL Fertig]**, um die Regel zu speichern.

   Die Mitgliedschaft wird automatisch aktualisiert, wenn Personendatensätze anhand der Regel ausgewertet werden.

### Personen-Journey

Wenn Sie die Zielgruppe für eine Personen-Journey mit einer Ereignis-Zielgruppe konfigurieren, können Sie die abgeleitete Persona als Personenprofilfilter verwenden, um zu steuern, welche Personen auf die Journey zugreifen.

1. Klicken Sie auf **[!UICONTROL Journey-Arbeitsfläche auf]** Knoten „Zielgruppe Person“.

1. Wählen Sie im Bedienfeld Knoteneigenschaften als Zielgruppentyp **[!UICONTROL Ereigniszielgruppe]** aus.

1. Klicken **[!UICONTROL unter „Personenprofilfilter]** auf **[!UICONTROL Filter hinzufügen]**.

1. Erweitern Sie **[!UICONTROL Personenattribute]** und ziehen Sie „Abgeleitete **[!UICONTROL &quot;]** die Filterarbeitsfläche.

   Sie können auch den Filternamen in das Suchfeld eingeben, um ihn schnell zu finden.

   ![Abgeleiteter Personenfilter wurde zur Arbeitsfläche des Personen-Journey-Ereignis-Zielgruppenfilters hinzugefügt.](assets/persona-mapping-derived-persona-event-filter.png){width="680" zoomable="yes"}

1. Wählen Sie in der Filterbedingung **[!UICONTROL ist]** und wählen Sie eine oder mehrere Rollen aus der Liste aus.

   Nur Personen, deren abgeleitete Rolle mit den ausgewählten Werten übereinstimmt, können die Journey aufrufen.

1. Klicken Sie **[!UICONTROL Speichern]**, um die Ereigniskriterien zu speichern.
