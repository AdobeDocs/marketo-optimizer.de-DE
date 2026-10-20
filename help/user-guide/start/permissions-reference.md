---
title: Produktberechtigungen
description: Referenzliste der Experience Platform-Berechtigungen, die den Zugriff auf Marketo Optimizer-Funktionen steuern, mit Beschreibungen und empfohlenen Berechtigungen für Admin-, All-Access- und Read-Only-Benutzende.
TQID: https://experienceleague.adobe.com/Q4HnGxPkiE0dsZUjIgPvVJHgs0dPwLJiOKVSL1edS4Y
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3cf5f37e-e87e-5179-812b-53ce05d7eebb
    internal-label: Setup
  - id: a659ad61-de21-559d-a901-02e2fb329ff5
    internal-label: Administration
subfeature_v2:
  - id: b6434e31-d7bb-5416-960c-1c77bb1a2e8d
    internal-label: User Access
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
autotag-review: '2026-10-20T17:03:48.312Z'
source-git-commit: e80513284d179a9b27d0505463d07d5e15facabb
workflow-type: tm+mt
source-wordcount: '1577'
ht-degree: 6%
---
# Produktberechtigungen

Die folgenden Berechtigungen steuern den Zugriff auf Funktionen in [!DNL Adobe Marketo Optimizer]. Fügen Sie sie zu Rollen _[!UICONTROL Bereich]_ Berechtigungen“ von [!DNL Adobe Experience Platform] hinzu. Ausführliche Informationen zum Erstellen von Rollen und Zuweisen zu Benutzern finden Sie unter [_Benutzerzugriff und Berechtigungen_](./user-management.md).

Die letzten drei Spalten zeigen die Berechtigungen, die für jeden der [vorgeschlagenen Benutzertypen“ empfohlen werden](#suggested-user-types) Admin, Alle Zugriffsbenutzer und Nur-Lese-Zugriff-Benutzer. Ein Häkchen (✔) bedeutet, dass die Berechtigung für diesen Benutzertyp empfohlen wird, und ein Bindestrich (-) bedeutet, dass dies nicht der Fall ist. Passen Sie die Empfehlungen an Ihre Organisation an.

>[!IMPORTANT]
>
>[!DNL Marketo Optimizer] Zugriff erfordert, dass Sie eine bestimmte Sandbox aktivieren, die mithilfe der folgenden Namenskonvention bereitgestellt wird: `Mktoaep` + [!DNL Marketo Engage] Abonnementpräfix. Wenn Ihr verknüpftes [!DNL Marketo Engage]-Abonnementpräfix beispielsweise _AcmeAssoc_ lautet, ist die für den [!DNL Marketo Optimizer] erforderliche Sandbox _MktoaepAcmeAssoc_. Diese Sandbox zu jeder Rolle hinzufügen.

>[!NOTE]
>
>Sie müssen Systemadministrator sein, um die Kachel _[!UICONTROL Berechtigungen]_ in Experience Platform sehen zu können.

Einige Berechtigungen gelten für Funktionen, die noch nicht im Produkt verfügbar sind. Admins können diese Berechtigungen jetzt hinzufügen, damit Benutzende den entsprechenden Zugriff haben, wenn die Funktionen verfügbar werden.

## Vorgeschlagene Benutzertypen {#suggested-user-types}

Verwenden Sie die Berechtigungsempfehlungen in den Tabellen auf dieser Seite als Ausgangspunkt für die Rollen, die Sie erstellen. Dies sind Vorschläge für jeden Benutzertyp. Passen Sie sie an Ihre Organisation an.

| Attribut | Admin | All Access User | Schreibgeschützter Benutzerzugriff |
| --- | ----- | --------------- | --------------------- |
| **Für wen ist es** | Personen, die [!DNL Marketo Optimizer] für Ihr Team einrichten und verwalten. | Marketer und Benutzer, die täglich in [!DNL Marketo Optimizer] arbeiten. | Personen, die [!DNL Marketo Optimizer] sehen müssen, aber nichts ändern müssen, z. B. Führungskräfte, Analysten und Prüfer. |
| **Was können sie tun** | Alles, einschließlich Einrichtung und Admin-Einstellungen. | Verwenden Sie alle Funktionen: Journey, Programme, Inhalte, Listen, Berichte und den Assistenten. | Zeigen Sie Journey, Programme, Inhalte, Listen und Berichte an und stellen Sie Fragen an den Assistenten. |
| **Berechtigungen zum Zuweisen** | Jede Berechtigung auf dieser Seite (wählen Sie **[!UICONTROL Alle hinzufügen]** im Rolleneditor aus). | Die Berechtigungen mit einem ✔ in der Spalte _Alle Zugriff_ der Tabellen auf dieser Seite. | Berechtigungen mit einem ✔ in der Spalte _Schreibgeschützt_ der Tabellen auf dieser Seite. |
| **Nicht enthalten** | – | <li>Admin-Konfigurationen<li>Kanalkonfigurationen, einschließlich E-Mail-Einstellungen, Formularvorgaben, Landingpage-Einstellungen und WhatsApp-Vorgaben und -Einstellungen<li>Programmtypen (anzeigen und verwalten) | <li>Erstellen, Bearbeiten, Löschen, Veröffentlichen oder Exportieren (alle _Verwalten_ und _Veröffentlichen_-Berechtigungen außer Chat-Zugriff)<li>Aktivieren von Zielgruppen für Ziele<li>Admin-Konfigurationen und Kanalkonfigurationen, einschließlich der Anzeige von E-Mail-Einstellungen und Formularvorgaben<li>Programmtypen anzeigen |
| **Empfohlene Benutzergruppe** | Marketo Optimizer-Administratorgruppe | Marketo Optimizer-Benutzergruppe | Marketo Optimizer-Benutzergruppe „Schreibgeschützt“ |
| **Vorgeschlagene Rolle** | Marketo Optimizer-Administrator | Marketo Optimizer All Access-Benutzer | Marketo Optimizer-Benutzer mit Lesezugriff |

Eine Anleitung zum Erstellen dieser Gruppen und Rollen finden Sie unter [Erstellen von Benutzergruppen und Rollen für vorgeschlagene Benutzertypen](./user-management.md#create-suggested-roles).

## Inhalte und Assets {#content-assets}

| Kategorie | Berechtigung | Beschreibung | Admin | Zugriff auf alle | Schreibgeschützt |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| B2B-Assets | Verwalten von B2B-Assets | Erstellen, Bearbeiten und Löschen von Asset-Dateien. | ✔ | ✔ | – |
| | Verwalten von B2B-E-Mails | Erstellen, Bearbeiten und Löschen von E-Mail-Nachrichten. | ✔ | ✔ | – |
| | Verwalten von B2B-Forms | Erstellen, Bearbeiten und Löschen von Formularen. | ✔ | ✔ | – |
| | Verwalten von B2B-Fragmenten | Erstellen, Bearbeiten und Löschen von Inhaltsfragmenten. | ✔ | ✔ | – |
| | B2B-Landingpage verwalten | Landingpages erstellen, bearbeiten und löschen. | ✔ | ✔ | – |
| | Export von B2B-Nachrichten verwalten | Exportieren Sie Nachrichtenberichte unter dem Abschnitt _E-Mail_. | ✔ | ✔ | – |
| | B2B-Vorlagen verwalten | Erstellen, Bearbeiten und Löschen von Inhaltsvorlagen. | ✔ | ✔ | – |
| | Verwalten von B2B-Webinaren | Erstellen, Bearbeiten und Löschen interaktiver Webinare. | ✔ | ✔ | – |
| | B2B-Forms veröffentlichen | Veröffentlichen Sie Formulare zur Verwendung auf Landingpages. | ✔ | ✔ | – |
| | Veröffentlichen von B2B-Fragmenten | Veröffentlichen Sie Inhaltsfragmente zur Verwendung in Vorlagen, E-Mails und Landingpages. | ✔ | ✔ | – |
| | B2B-Landingpage veröffentlichen | Veröffentlichen von Landingpages | ✔ | ✔ | – |
| | B2B-Assets anzeigen | Zeigen Sie Details zur Assets-Bibliothek und Asset-Datei an. | ✔ | ✔ | ✔ |
| | B2B-E-Mails anzeigen | E-Mail-Nachrichten anzeigen. | ✔ | ✔ | ✔ |
| | B2B-Forms anzeigen | Formulare anzeigen. | ✔ | ✔ | ✔ |
| | Anzeigen von B2B-Fragmenten | Anzeigen der Liste und Details von Inhaltsfragmenten. | ✔ | ✔ | ✔ |
| | B2B-Landingpage anzeigen | Landingpages anzeigen. | ✔ | ✔ | ✔ |
| | B2B-Vorlagen anzeigen | Anzeigen der Liste der Inhaltsvorlagen und Details. | ✔ | ✔ | ✔ |
| | B2B-Webinare anzeigen | Interaktive Webinare anzeigen. | ✔ | ✔ | ✔ |

## Kanalkonfiguration und -verwaltung {#channels-admin}

| Kategorie | Berechtigung | Beschreibung | Admin | Zugriff auf alle | Schreibgeschützt |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| B2B-Administratorkonfigurationen | Verwalten von B2B-Admin-Konfigurationen | Konfigurieren Sie Administrationseinstellungen, z. B. Verbindungen für Digital Asset Management, Asset-Repositorys und Ereignisse. | ✔ | – | – |
| B2B-Kanal-Konfigurationen | Verwalten von B2B-Kanalkonfigurationen | Zugriff auf den _Kanäle_ im linken Navigationsbereich und alle Kanalkonfigurationsvorgänge. | ✔ | – | – |
| | B2B-E-Mail-Einstellungen verwalten | Konfigurieren Sie E-Mail-Einstellungen. Diese Einstellungen sind erforderlich, damit Benutzer E-Mails senden können. | ✔ | – | – |
| | Verwalten der B2B-Forms-Voreinstellung | Erstellen, Bearbeiten und Löschen von Formularvorgaben. | ✔ | – | – |
| | Einstellungen für B2B-Landingpages verwalten | Konfigurieren Sie Landingpage-Einstellungen wie Subdomains. | ✔ | – | – |
| | Verwalten von B2B-WhatsApp-Voreinstellungen | Erstellen, Anzeigen und Löschen von WhatsApp-Nachrichtenvoreinstellungen und zugehörigen SMS-Einstellungen. | ✔ | – | – |
| | B2B-WhatsApp-Einstellungen verwalten | Konfigurieren Sie die Einstellungen des WhatsApp-Kanals. | ✔ | – | – |
| | Veröffentlichen der B2B-Forms-Voreinstellung | Veröffentlichen von Formularvorgaben. | ✔ | – | – |
| | B2B-E-Mail-Einstellungen anzeigen | E-Mail-Einstellungen anzeigen (Subdomains, PTR-Einträge, IP-Pools, Unterdrückungslisten, Seed-Listen, IP-Aufwärmpläne). | ✔ | – | – |
| | B2B-Forms-Voreinstellung anzeigen | Anzeigen von Formularvorgaben. | ✔ | – | – |

## Journey, Programme und Ordner {#journeys-programs}

| Kategorie | Berechtigung | Beschreibung | Admin | Zugriff auf alle | Schreibgeschützt |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| B2B-Ordner-Token | Verwalten von B2B-Ordner-Token | Erstellen, Bearbeiten und Löschen von Token in Ordnern. Änderungen gelten für alle Elemente im Ordner. Weisen Sie diese daher getrennt von „B2B-_verwalten“_. | ✔ | ✔ | – |
| | Anzeigen von B2B-Ordner-Token | In Ordnern definierte Token anzeigen. | ✔ | ✔ | ✔ |
| B2B-Ordner | B2B-Ordner verwalten | Erstellen, Bearbeiten und Löschen von Ordnern | ✔ | ✔ | – |
| | B2B-Ordner anzeigen | Ordner anzeigen. | ✔ | ✔ | ✔ |
| B2B-Journey | Verwaltung der Traffic-Steuerung für B2B-Journey | Konfigurieren Sie die Traffic-Steuerung für Journey, einschließlich der Simulation ihrer Wirkung. | ✔ | ✔ | – |
| | Verwalten von B2B-Personen-Journey | Zugriff auf die _Personen-Journey_-Liste und alle Personen-Journey-Vorgänge. | ✔ | ✔ | – |
| | Veröffentlichen von B2B-Personen-Journey | Personen-Journey veröffentlichen. | ✔ | ✔ | – |
| | Anzeigen der B2B-Journey-Traffic-Steuerung | Journey-Traffic-Steuerungsparameter anzeigen. | ✔ | ✔ | ✔ |
| | B2B-Personen-Journey-Berichte anzeigen | Zeigen Sie Berichte zum Journey von Personen an, einschließlich des _Personen-Journey_ Berichts. | ✔ | ✔ | ✔ |
| | B2B-Personen-Journey anzeigen | Schreibgeschützter Zugriff auf die Liste _Personen-Journey_ und Journey-Details. | ✔ | ✔ | ✔ |
| B2B-Programm-Token | Verwalten von B2B-Programm-Token | Erstellen, Bearbeiten und Löschen von Token für Programme und Programmtypen. | ✔ | ✔ | – |
| | Anzeigen von B2B-Programm-Token | Zeigen Sie Token an, die in Programmen und Programmtypen definiert sind. | ✔ | ✔ | ✔ |
| B2B-Programmtypen | B2B-Programmtypen verwalten | Erstellen, Bearbeiten und Löschen von Marketing-Programmtypen. | ✔ | – | – |
| | B2B-Programmtypen anzeigen | Typen von Marketing-Programmen anzeigen. | ✔ | – | – |
| B2B-Programme | Verwalten von B2B-Programmen | Erstellen, Bearbeiten und Löschen von Marketing-Programmen. | ✔ | ✔ | – |
| | B2B-Programme anzeigen | Marketing-Programme anzeigen. | ✔ | ✔ | ✔ |

## Zielgruppen, Absicht und Ziele {#audiences-intent}

| Kategorie | Berechtigung | Beschreibung | Admin | Zugriff auf alle | Schreibgeschützt |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| B2B-Ziele | Aktivieren von B2B-Zielen | Zielgruppen für B2B-Ziele aktivieren. | ✔ | ✔ | – |
| | Verwalten von B2B-Zielen | Erstellen, Bearbeiten und Löschen von B2B-Zielen. | ✔ | ✔ | – |
| | B2B-Ziele anzeigen | Schreibgeschützter Zugriff auf B2B-Ziele. | ✔ | ✔ | ✔ |
| Konfiguration der B2B-Absicht | Konfiguration der B2B-Absicht verwalten | Erstellen, Bearbeiten und Löschen von Absichtskonfigurationen. | ✔ | ✔ | – |
| | Konfiguration der B2B-Absicht anzeigen | Anzeigen von Absichtskonfigurationen (Absichtsgewichtungsmodelle). | ✔ | ✔ | ✔ |
| B2B-Organisationsregeln | Verwalten von B2B-Organisationsregeln | Erstellen, Bearbeiten und Löschen von Organisationsregeln. | ✔ | ✔ | – |
| | B2B-Organisationsregeln anzeigen | Organisationsregeln anzeigen. | ✔ | ✔ | ✔ |
| B2B-Personenlisten | B2B-Personenlisten verwalten | Erstellen, Bearbeiten und Löschen von Personenlisten und Verwalten der Listenmitgliedschaft. | ✔ | ✔ | – |
| | B2B-Personenlisten anzeigen | Anzeigen von statischen und dynamischen Personenlisten. | ✔ | ✔ | ✔ |

## Berichte, Labs und Chat {#reports-labs-chat}

| Kategorie | Berechtigung | Beschreibung | Admin | Zugriff auf alle | Schreibgeschützt |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| B2B-Gesprächserlebnis | Verwalten von B2B-Gesprächserlebnissen | Zugang zum Chat-Panel und zum Assistenten. Für Aktionen im Bereich ist außerdem die Berechtigung für die entsprechende Funktion erforderlich. Um beispielsweise eine Journey zu erstellen, benötigen Sie _B2B-Personen-Journey verwalten_. Siehe [Chat-Berechtigungen](#chat-permissions). | ✔ | ✔ | ✔ |
| B2B-Labs | Verwalten von B2B-Labs | Aktivieren und Konfigurieren von Labs-Funktionen. | ✔ | ✔ | – |
| | B2B-Labs anzeigen | Zeigen Sie die verfügbaren und aktivierten Labs-Funktionen an. | ✔ | ✔ | ✔ |
| B2B-Reporting | Anzeigen von eingebetteten B2B-Berichten | Die Berichte werden auf der Registerkarte _Berichte_ angezeigt. | ✔ | ✔ | ✔ |
| | B2B-Absichtsberichte anzeigen | Anzeigen von Absichtsberichten. | ✔ | ✔ | ✔ |

## Chat-Berechtigungen {#chat-permissions}

Chatberechtigungen folgen den Berechtigungen auf Funktionsebene. _Verwalten von B2B Conversational Experience_ bietet Zugriff auf das [!DNL CX Coworker] Chat-Bedienfeld, gewährt jedoch keinen Zugriff auf Funktionen. Ein Mitarbeiter prüft alle Kenntnisse oder Aktionen im Chat mit derselben Berechtigung, die die Funktion außerhalb des Chat benötigt: _Verwalten_-Berechtigungen zum Erstellen, Bearbeiten oder Veröffentlichen und _Anzeigen_-Berechtigungen für schreibgeschützte Fähigkeiten. Wenn Benutzenden die Berechtigung für die Funktion fehlt, können [!DNL Coworker] diese Aktion nicht für sie durchführen. Um beispielsweise eine Journey zu erstellen, ist _B2B-Personen-Journey verwalten_ und für die Auflistung von Formularen ist _B2B-Forms anzeigen_ erforderlich.

## Berechtigungen für externe Ziele {#external-destinations-permissions}

Um Benutzern in [!DNL Marketo Optimizer] Zugriff auf externe Ziele zu gewähren, sind die folgenden Berechtigungen erforderlich. Die Spalten befolgen für jeden Benutzertyp die gleichen Empfehlungen, die unter [Vorgeschlagene Benutzertypen](#suggested-user-types) beschrieben werden.

| Kategorie | Berechtigung | Beschreibung | Admin | Zugriff auf alle | Schreibgeschützt |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| Dashboards | Standard-Dashboards verwalten | Fügen Sie benutzerdefinierte Attribute hinzu, die sich noch nicht im Data Warehouse befinden. | ✔ | ✔ | – |
| | Standard-Dashboards anzeigen | Schreibgeschützter Zugriff auf die Dashboards _Profile_, _Ziele_ und _Segmente_. Ermöglicht auch den Zugriff auf _Dashboards_ im linken Navigationsbereich. | ✔ | ✔ | ✔ |
| Ziele | Aktivieren von Zielen | Aktivieren von Daten für aktive Ziele. _Ziele anzeigen_ oder _Ziele verwalten_ ist ebenfalls erforderlich. | ✔ | ✔ | – |
| | Segment ohne Zuordnung aktivieren | Aktivieren von Zielgruppen für vorhandene Ziele ohne den Zuordnungsschritt. Benutzende können Zielgruppen zu Aktivierungs-Workflows hinzufügen und welche daraus entfernen, jedoch keine zugeordneten Attribute oder Identitäten. _Ziele anzeigen_ ist ebenfalls erforderlich. | ✔ | ✔ | – |
| | Ziel-Authoring | Erstellen Sie Ziele mit der Experience Platform Destination SDK. | ✔ | ✔ | – |
| | Verwalten und Aktivieren des Datensatzziels | Datensatz-Exportflüsse anzeigen, erstellen, bearbeiten und deaktivieren und Daten für Datensätze aktivieren. _Ziele anzeigen_ ist ebenfalls erforderlich. | ✔ | ✔ | – |
| | Verwalten von Zielen | Anzeigen, Erstellen und Löschen von Zielverbindungen und Zielkonten. | ✔ | ✔ | – |
| | Anzeigen von Zielen | Sie können verfügbare Ziele auf der Registerkarte _Katalog_ und authentifizierte Ziele auf der Registerkarte _Durchsuchen_ anzeigen. | ✔ | ✔ | ✔ |
| Data Governance | Verwalten von B2B-Löschkennzeichnungen | Anzeigen, Erstellen und Löschen von Datennutzungskennzeichnungen (Data Usage Labels, DULE), die auf Datensätze und Schemata angewendet werden. | ✔ | ✔ | – |
| | Verwalten von Datennutzungsrichtlinien | Anzeigen, Erstellen, Bearbeiten und Löschen von Datennutzungsrichtlinien. | ✔ | ✔ | – |
| | Anzeigen von Datennutzungsrichtlinien | Schreibgeschützter Zugriff auf Datennutzungsrichtlinien Ihrer Organisation. | ✔ | ✔ | ✔ |
| Datenaufnahme | Verwalten von Quellen | Anzeigen, Erstellen, Bearbeiten und Deaktivieren von Quellen. | ✔ | ✔ | – |
| | Anzeigen von Quellen | Anzeigen verfügbarer Quellen auf der Registerkarte _Katalog_ und authentifizierter Quellen auf der Registerkarte _Durchsuchen_. | ✔ | ✔ | ✔ |
| Profilverwaltung | Profileinstellungen verwalten | Alle Profileinstellungen anzeigen und bearbeiten. | ✔ | ✔ | – |
| | Profileinstellungen anzeigen | Schreibgeschützter Zugriff auf alle Profileinstellungen. | ✔ | ✔ | ✔ |

<!-- 

## Planned permissions {#planned-permissions}

The following permissions are for features that are not yet available in [!DNL Marketo Optimizer]. Adobe Marketo Qualifier permissions are not currently enforced. The estimated enforcement date is November 2026. Accounts and buying groups are targeted for delivery in Q1 2027.

| Category | Permission | Description | Admin | All Access | Read Only |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| Marketo Qualifier Configurations | Manage Marketo Qualifier Configurations | Create, edit, and delete Marketo Qualifier configurations. | ✔ | – | – |
| | View Marketo Qualifier Configurations | View Marketo Qualifier configurations. | ✔ | ✔ | ✔ |
| Marketo Qualifier Outbound | View Marketo Qualifier Outbound | View Marketo Qualifier outbound workflows and outbound reporting. | ✔ | ✔ | ✔ |
| Marketo Qualifier Research | Manage Marketo Qualifier Research | Use and manage research capabilities. | ✔ | ✔ | – |
| | View Marketo Qualifier Research | View research: conversational interface, prospect view, and account and lead research. | ✔ | ✔ | ✔ |
| B2B Account Lists | Manage B2B Account Lists | Create, edit, and delete account lists, including adding, removing, and importing accounts. | ✔ | ✔ | – |
| B2B Buying Groups | Manage B2B Buying Groups | Create, edit, and delete buying groups. | ✔ | ✔ | – |
| | Manage B2B Role Templates | Manage the role templates used in buying groups. | ✔ | ✔ | – |
| | Manage B2B Solution Interests | Manage the solution interests used in buying groups. | ✔ | ✔ | – |
| | Manage B2B Stages | Manage buying group stages. | ✔ | ✔ | – |
| | View B2B Buying Groups | View buying groups. | ✔ | ✔ | ✔ |

-->
