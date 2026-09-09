---
title: Persona-Zuordnung
description: Erfahren Sie, wie Sie in Marketo Optimizer die Persona-Zuordnung einrichten. Ordnen Sie Personenattribute zu, um Personas zu definieren, und verwenden Sie die Filterung abgeleiteter Personas in Personenlisten und Journey von Personen.
TQID: 'https://experienceleague.adobe.com/JCBtJN4DgQZROVDamM4eKuCiGTwJQPQY3wMxmBPFj74'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2:
  - id: 46e599c6-e20f-5f67-9824-93415016f66b
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
  - id: a659ad61-de21-559d-a901-02e2fb329ff5
  - id: d4203578-d294-5145-b397-f26f4488a904
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 1216
ht-degree: 1%

---

# Persona-Mapping

<!-- not available until GA -->

Personas sind ein wichtiger Aspekt in einem Account-Based Marketing (ABM)-Ansatz, da sie Marketing-Experten dabei helfen, ihre Strategien an die spezifischen Bedürfnisse, Präferenzen und Schmerzpunkte von Personen in Zielkonten anzupassen. Marketing-Experten können für jede Rolle ein detailliertes Profil erstellen, einschließlich Hintergrund, Zuständigkeiten, Probleme und bevorzugter Kommunikationskanäle. Mit diesen Definitionen können Admins Personas anhand von Personenattributen in Marketo Optimizer konfigurieren, sodass Personenlisten und Journey optimierte und konsistente Filter verwenden können, mit denen diese Personas erfasst werden.

In Marketo Optimizer bietet die Rollenzuordnung eine zusätzliche Funktion, die über die Bedingungen für Rollenvorlagen hinausgeht: Sie können [Personenlisten](../audiences/people-lists.md) und [Personen-Journey](../marketing/person-journeys.md) mithilfe von **[!UICONTROL Abgeleitete]** als Filterkriterium filtern. Eine _abgeleitete Persona_ ist die Persona, die das System für einen Personendatensatz ableitet, indem es seine Attribute mit allen konfigurierten Persona-Definitionen vergleicht.

Definition der Persona und Nutzungsbeschränkungen:

* Es können bis zu 20 Personas in der Liste „Persona _[!UICONTROL Zuordnung“ definiert]_.
* Jede Rolle kann bis zu fünf Attribute in ihre Definition aufnehmen.
* Sie können für alle definierten Personas bis zu zehn verschiedene Personenattribute verwenden.

>[!BEGINSHADEBOX]

**Anwendungsfall: Varianten der Auftragstitel**

Viele Marketing- und Verkaufsteams verwenden Jobtitel als Möglichkeit, verschiedene Rollen innerhalb eines Kontos zu identifizieren. Titel für Kontakte können jedoch inkonsistent sein und zahlreiche Varianten für ähnliche Rollen verwenden. Beim Erstellen von Personenlistenfiltern oder Personen-Journey-Zielgruppenbedingungen kann es erforderlich sein, dass Sie jede mögliche zugehörige Stellenbezeichnung für eine bestimmte Rolle definieren. Sie können diese Definitionen vereinfachen und Personen mit ähnlichen Stellenbezeichnungen unter eine abgeleitete Rolle bringen, die Sie dann ansprechen können, indem Sie nach „Abgeleitete _ist Produktverwaltung“ filtern_ anstatt einzelne Stellenbezeichnungswerte abzugleichen.

>[!ENDSHADEBOX]

## Zugreifen auf die konfigurierten Personas {#access}

1. Wählen Sie in der linken Navigation **[!UICONTROL Administration]** > **[!UICONTROL Konfigurationen]**.

1. Klicken Sie **[!UICONTROL Zwischenbereich auf]** Persona-Zuordnung“, um die Liste der Personas anzuzeigen.

   ![Zugriff auf die konfigurierten Personas](assets/configuration-persona-mapping.png){width="800" zoomable="yes"}

   Auf dieser Seite können Sie [erstellen](#create-a-persona), [bearbeiten](#edit-a-persona) oder [löschen](#delete-a-persona).

   Die Persona-Zuordnungsliste ist als Tabelle organisiert und zeigt oben die zuletzt aktualisierten Personas an (sortiert nach _[!UICONTROL Letzte Aktualisierung]_). Sie können die angezeigte Tabelle anpassen, indem Sie auf das Symbol _Spalteneinstellungen_ ( ![Spalteneinstellungen](../assets/do-not-localize/icon-column-settings.svg) ) in der oberen rechten Ecke klicken und die Kontrollkästchen für die Spalten aktivieren oder deaktivieren.

   ![Spalten für die Anzeige in der Persona-Zuordnungsliste](assets/configuration-persona-mapping-list-columns.png){width="300"}

1. Um auf die Details einer Rolle zuzugreifen, klicken Sie auf den Namen.

### Standard-Personas

Die _Persona-Zuordnung_ enthält fünf standardmäßige Personas, die anhand des Attributs für die Auftragstitel definiert werden. Sie können jede dieser Standardpersonas entsprechend den Anforderungen Ihres Unternehmens bearbeiten:

| Persona | Stellenbezeichnungen |
| ------- | ---------- |
| CXO / EVP - CXO / Executive Vice President | CEO, CIO, CTO, CMO, CFO, Executive Vice President of Strategy |
| SVP / VP - Senior Vice President / Vice President | SVP Marketing, VP Sales, SVP Operations, VP Product, VP IT |
| Senior Director / Director - Senior Director / Director | Director of Engineering, Senior Director of Product, Director of Finance, Director of Customer Success |
| Senior Manager/Manager - Senior Manager/Manager | Senior Marketing Manager, IT Manager, Operations Manager, Sales Manager, HR Manager |
| Einzelner Mitwirkender - Einzelner Mitwirkender | Kundenbetreuer, Software-Ingenieur, Marketing-Spezialist, Customer Success-Vertreter |
| Analyst - Analyst | Business Analyst, Data Analyst, Market Research Analyst, Financial Analyst, Operations Analyst |
| Entwickler - Entwickler | Frontend-Entwickler, Backend-Entwickler, Full-Stack-Entwickler, Mobile-App-Entwickler, DevOps-Ingenieur |
| Professionelles Personal - Professionelles Personal | HR Specialist, Legal Counsel, Compliance Officer, Project Manager, Procurement Specialist |
| Berater - Berater | Unternehmensberater, IT-Berater, Business Process Consultant, Marketing Consultant |
| Andere - Andere | Branchenspezialist, unabhängiger Berater, freiberuflicher Berater, Fachexperte |

### Filtern von Listen

Um die gewünschte Persona zu finden, geben Sie eine Textzeichenfolge in die Suchleiste ein, um Personas anhand des Namens zuzuordnen.

![Filtern der angezeigten Rollenzuordnungen](assets/configuration-persona-mapping-search.png){width="700" zoomable="yes"}

## Persona erstellen {#create-a-persona}

1. Wählen Sie in der linken Navigation **[!UICONTROL Administration]** > **[!UICONTROL Konfiguration]** aus.

1. Klicken Sie **[!UICONTROL Zwischenbereich auf]** Persona-Zuordnung“.

1. Klicken Sie **[!UICONTROL Persona erstellen]**.

1. Geben Sie einen eindeutigen **[!UICONTROL Namen]** und **[!UICONTROL Beschreibung]** (optional) für die Rolle ein.

   ![Persona-Zuordnung erstellen](assets/configuration-persona-mapping-new.png){width="700" zoomable="yes"}

1. Wählen Sie die Attribute aus, die für die Zuordnung der Rolle verwendet werden sollen.

   * Klicken Sie **[!UICONTROL Personenattribute auswählen]**.

   * Aktivieren Sie im Dialogfeld das Kontrollkästchen für jedes Attribut, das Sie zuordnen möchten (maximal fünf).

     Sie können die angezeigte Tabelle anpassen, indem Sie auf das Symbol _Spalteneinstellungen_ ( ![Spalteneinstellungen](../assets/do-not-localize/icon-column-settings.svg) ) in der oberen rechten Ecke klicken.

     Um die Attributliste nach Namen zu filtern, geben Sie eine Textzeichenfolge in die Suchleiste ein. Sie können auch auf das Symbol _Filter_ ( ![Filtersymbol](../assets/do-not-localize/icon-filter.svg) ) oben links klicken, um die angezeigte Liste nach Typ, _Standard_ oder _Benutzerdefiniert_ zu filtern.

     ![Dialogfeld „Persönliche Attribute auswählen“](assets/configuration-persona-mapping-select-attributes.png){width="700" zoomable="yes"}

   * Klicken Sie auf **[!UICONTROL Speichern]**.

     Die ausgewählten Attribute werden im Abschnitt &quot;_[!UICONTROL -Attribute]_ ausgefüllt.

1. Geben Sie für jedes Attribut die kommagetrennten Werte ein, denen Sie für das Attribut entsprechen möchten.

1. Klicken Sie auf **[!UICONTROL Senden]**.

## Persona bearbeiten {#edit-a-persona}

Klicken Sie auf den Personennamen, um auf die Details der Rolle zuzugreifen und sie zu bearbeiten.

Sie können den Namen oder die Beschreibung ändern, Attribute hinzufügen oder die Attributwerte aktualisieren. Klicken Sie **[!UICONTROL Senden]** wenn Ihre Änderungen abgeschlossen sind.

## Persona löschen {#delete-a-persona}

Wenn Sie eine Rolle löschen, wird sie aus der Liste _Persona-Zuordnung_ entfernt und ist nicht mehr als abgeleiteter Personenfilter in Personenlisten oder Journey-Listen verfügbar.

1. Suchen Sie auf _[!UICONTROL Seite]_ Persona-Zuordnung“ die Persona, die Sie löschen möchten.

1. Klicken Sie neben dem Namen auf die Auslassungspunkte (**…**) und wählen Sie **[!UICONTROL Löschen]**.

1. Klicken Sie im Bestätigungsdialog auf **[!UICONTROL Löschen]**.

## Nach abgeleiteter Persona filtern {#derived-persona-filter}

Nachdem Personas konfiguriert wurden, leitet Marketo Optimizer ein Persona für jeden Personendatensatz ab, indem die Attribute des Datensatzes mit den definierten Persona-Zuordnungen verglichen werden. Sie können das abgeleitete Ergebnis - die _abgeleitete Persona_ - als Filter verwenden, wenn Sie die Audience für eine Personen-Liste oder eine Personen-Journey definieren.

Der Filter Abgeleitete Persona wird im Filterbedienfeld unter der Kategorie **[!UICONTROL Spezielle Filter]** zusammen mit anderen abgeleiteten Attributen wie z. B. der Journey-Mitgliedschaft angezeigt.

### Personenlisten

Wenn Sie Mitglieder zu einer statischen Personenliste hinzufügen oder daraus entfernen oder wenn Sie die Mitgliedschaftsregeln für eine dynamische Personenliste definieren, können Sie nach Abgeleiteter Rolle filtern, um alle Personen anzusprechen, deren Attribute einer bestimmten konfigurierten Rolle entsprechen.

**Statische Liste - Mitglieder hinzufügen**

1. Öffnen Sie die statische Liste und klicken Sie **[!UICONTROL oben]** auf „Personen hinzufügen“.

1. Erweitern Sie im Filterdialogfeld **[!UICONTROL Sonderfilter]** und ziehen Sie **[!UICONTROL Abgeleitete Persona]** auf die Arbeitsfläche.

1. Wählen Sie in der Filterbedingung **[!UICONTROL ist]** und wählen Sie eine oder mehrere Rollen aus der Liste aus.

1. Klicken Sie **[!UICONTROL Fertig]**, um den Filter anzuwenden und passende Personen für die Liste zu qualifizieren.

**Dynamische Liste - Festlegen von Mitgliedschaftsregeln**

1. Öffnen Sie die dynamische Liste und wählen Sie die Registerkarte **[!UICONTROL Regeln]** aus.

1. Klicken Sie **[!UICONTROL Regeln bearbeiten]**.

1. Erweitern Sie im Filterdialogfeld **[!UICONTROL Sonderfilter]** und ziehen Sie **[!UICONTROL Abgeleitete Persona]** auf die Arbeitsfläche.

1. Wählen Sie in der Filterbedingung **[!UICONTROL ist]** und wählen Sie eine oder mehrere Rollen aus der Liste aus.

1. Klicken Sie **[!UICONTROL Fertig]**, um die Regel zu speichern.

   Die Mitgliedschaft wird automatisch aktualisiert, wenn Personendatensätze anhand der Regel ausgewertet werden.

### Personen-Journey

Wenn Sie die Zielgruppe für eine Personen-Journey mit einer Ereignis-Zielgruppe konfigurieren, können Sie die abgeleitete Persona als Personenprofilfilter verwenden, um zu steuern, welche Personen auf die Journey zugreifen.

1. Klicken Sie auf **[!UICONTROL Journey-Arbeitsfläche auf]** Knoten „Zielgruppe Person“.

1. Wählen Sie im Bedienfeld Knoteneigenschaften als Zielgruppentyp **[!UICONTROL Ereigniszielgruppe]** aus.

1. Klicken **[!UICONTROL unter „Personenprofilfilter]** auf **[!UICONTROL Filter hinzufügen]**.

1. Erweitern Sie **[!UICONTROL Spezialfilter]** und ziehen Sie **[!UICONTROL Abgeleitete Persona]** auf die Filterarbeitsfläche.

1. Wählen Sie in der Filterbedingung **[!UICONTROL ist]** und wählen Sie eine oder mehrere Rollen aus der Liste aus.

   Nur Personen, deren abgeleitete Rolle mit den ausgewählten Werten übereinstimmt, können die Journey aufrufen.
