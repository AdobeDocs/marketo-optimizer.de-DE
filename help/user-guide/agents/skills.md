---
title: Mitarbeiterqualifikationen
description: Überprüfen Sie die CX Enterprise Coworker-Fähigkeiten in Marketo Optimizer - gepackte Workflows für Programme, Journey, Zielgruppen, Bewertung, Inhalte und Sendezeitoptimierung.
TQID: 'https://experienceleague.adobe.com/nNFB9UEghfqVvnBrNtTDnpnLUKKKMAU2nY1Pqt0KkUQ'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3cf5f37e-e87e-5179-812b-53ce05d7eebb
    internal-label: Setup
  - id: 46e599c6-e20f-5f67-9824-93415016f66b
    internal-label: Audiences
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
  - id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4
    internal-label: Programs
  - id: d4203578-d294-5145-b397-f26f4488a904
    internal-label: Channels
topic_v2:
  - id: b4dd41a7-ccf8-4e9d-918e-acaab534a307
    internal-label: Data quality
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 6e03e2dc6abb00d288f5684e9ea9b6489c6517e4
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 7%
---
# Mitarbeiterqualifikationen

Eine _Qualifikation_ ist ein gepackter Workflow, den ein Kollege ausführen kann - die Bausteine hinter dem `/` und den Anforderungen in natürlicher Sprache. Jede Qualifikation umfasst schrittweise Anweisungen und die spezifischen Tools, die für einen Auftrag erforderlich sind (z. B. „Veröffentlichen eines Journey&quot;, „Vergleichen von zwei Personenlisten“, „Erstellen eines Bewertungsmodells„).

>[!NOTE]
>
>Jede Qualifikation wird danach klassifiziert, ob die Qualifikation den [!DNL Marketo Optimizer]- oder [!DNL Marketo Engage] mutiert (**Write**), nur Abfragen/Analysen/Generierungen (**Read**) oder gleichrangige Abfrage- und Mutationsfunktionen aufweist (**Read+Write**).

## Programme und Planung {#programs-planning}

| Skill | Funktion | Zugriff | Produktoberfläche | Auswirkungen/Datenfluss |
|---|---|---|---|---|
| `adapt-program` | Generieren Sie Migrationsgeschichten aus [!DNL Marketo Engage] Programmen zur [!DNL Marketo Optimizer]. | Lesen | [!DNL Marketo Optimizer] | Liest [!DNL Marketo Engage], schreibt [!DNL Marketo Optimizer] |
| `folder-creation` | Erstellen Sie Organisationsordner in der Asset-Baumstruktur. | Schreiben | [!DNL Marketo Optimizer] | Lese- und Schreibvorgänge [!DNL Marketo Optimizer] |
| `program-creation` *(Erstellen von Programmen)* | Erstellen von Marketo-Programmen aus einer Kampagnenbeschreibung.  <p>Siehe _[Erstellen eines Programms aus einer](./program-from-brief.md)_. | Schreiben | [!DNL Marketo Engage] | Lese- und Schreibvorgänge [!DNL Marketo Engage] |
| `program-planning` *(Kampagnen planen)* | Umwandeln von Briefs in Einrichtungs-/Implementierungsdokumente. | Lesen | [!DNL Marketo Engage] | Liest [!DNL Marketo Engage] |
| `program-qa` *(Programme validieren)* | Programme validieren/überprüfen (nur Regeln, Testplan oder Kurzbeschreibung). | Lesen | [!DNL Marketo Engage] | Liest [!DNL Marketo Engage] |

## Journeys {#journeys}

| Skill | Funktion | Zugriff | Produkt | Backend (Datenfluss) |
|---|---|---|---|---|
| `journey-creation` | Erstellen und bearbeiten Sie Journey aus natürlicher Sprache. | Schreiben | [!DNL Marketo Optimizer] | Lese- und Schreibvorgänge [!DNL Marketo Optimizer] |
| `journey-edit-dates` | Ändern des Start-/Enddatums einer Journey ohne Veröffentlichung. | Schreiben | [!DNL Marketo Optimizer] | Lese- und Schreibvorgänge [!DNL Marketo Optimizer] |
| `journey-publish` | Personen-Journey veröffentlichen/starten/planen. | Schreiben | [!DNL Marketo Optimizer] | Lese- und Schreibvorgänge [!DNL Marketo Optimizer] |
| `journey-stop` | Abbrechen, schließen, stoppen, stoppen oder Journey töten. | Schreiben | [!DNL Marketo Optimizer] | Lese- und Schreibvorgänge [!DNL Marketo Optimizer] |
| `journey-reentry` | Erneuten Eintrag konfigurieren: Zulassen/Verweigern, Abklingzeit, Max. Einträge. | Schreiben | [!DNL Marketo Optimizer] | Lese- und Schreibvorgänge [!DNL Marketo Optimizer] |
| `journey-trafficcontrol` | Führen Sie eine Traffic-Steuerungssimulation aus, die das Profil-Routing anzeigt. | Lesen | [!DNL Marketo Optimizer] | Liest [!DNL Marketo Optimizer] (Simulation) |
| `journey-observability` | Debug/Überwachung des Fortschritts - Pfade, Timing, Aufspaltungen, Verzögerungen, Verweildauer. <p>Siehe _[Debuggen und Überwachen des Journey-Fortschritts](./journey-observability.md)_. | Lesen | [!DNL Marketo Optimizer] | Liest [!DNL Marketo Optimizer] + [!DNL Marketo Engage] (statische Listenüberprüfung) |

## Zielgruppen und Personen {#audiences-people}

| Skill | Funktion | Zugriff | Produkt | Backend (Datenfluss) |
|---|---|---|---|---|
| `audience-creation` | Passen Sie eine [!DNL Marketo Engage] SmartList an, erstellen Sie eine Personenliste oder fügen Sie Regeln hinzu bzw. aktualisieren Sie sie. <p>Siehe _[Erstellen von Zielgruppen für Programme](./audience-creation.md)_. | Schreiben | [!DNL Marketo Optimizer] | Liest [!DNL Marketo Engage] + liest/schreibt [!DNL Marketo Optimizer]. |
| `people-list-comparison` | Vergleichen Sie zwei Personenlisten und zeigen Sie sich überschneidende Elemente an. | Lesen | [!DNL Marketo Optimizer] | Liest [!DNL Marketo Optimizer] |
| `import-leads` | Überprüfen Sie die CSV-Datenqualität und übertragen Sie Importe auf [!DNL Marketo Engage]. | Lese- und Schreibzugriff | Beide | Lese- und Schreibvorgänge [!DNL Marketo Engage] |
| `lead-investigation` *(Leads untersuchen)* | Untersuchen der Aktivität, Bewertung, Qualifizierung und des Lebenszyklus eines Leads. | Lesen | [!DNL Marketo Engage] | Liest [!DNL Marketo Engage] |

## Inhalt und Kanäle {#content-channels}

| Skill | Funktion | Zugriff | Produkt | Backend (Datenfluss) |
|---|---|---|---|---|
| `content-personalization` | Vorlagen durchsuchen/in der Vorschau anzeigen und Inhalte bearbeiten/Varianten erzeugen. | Lese- und Schreibzugriff | [!DNL Marketo Optimizer] | [!DNL Marketo Optimizer] mit Lese- und Schreibzugriff. Siehe _[Personalisieren von E-Mail-Inhalten nach](./personalize-content.md)_). |
| `asset-tokens` | Vollständiges CRUD-Token für Programme/Ordner/Journey. | Lese- und Schreibzugriff | [!DNL Marketo Optimizer] | Lese- und Schreibvorgänge [!DNL Marketo Optimizer] |
| `fcs-channels` | Kanalsuchen und CRUD + Publish/Stopp/Delete. | Lese- und Schreibzugriff | [!DNL Marketo Optimizer] | Lese- und Schreibvorgänge [!DNL Marketo Optimizer] |

## Scoring und Signale {#scoring-signals}

| Skill | Funktion | Zugriff | Produkt | Backend (Datenfluss) |
|---|---|---|---|---|
| `scoring-studio` | Bewertungsmodelle auflisten/abrufen und erstellen/veröffentlichen. <p>Siehe _[Erstellen benutzerdefinierter Bewertungsmodelle](./lead-scoring-model.md)_. | Lese- und Schreibzugriff | [!DNL Marketo Optimizer] | Liest und schreibt [!DNL Marketo Optimizer] (Scoring-Service); liest [!DNL Marketo Engage] Lead-Felder/Aktivitätstypen. |
| `engagementconfiguration` | Interaktionskonfiguration anzeigen und Gewichtungen bearbeiten/aktualisieren. | Lese- und Schreibzugriff | [!DNL Marketo Optimizer] | Lese- und Schreibvorgänge [!DNL Marketo Optimizer] |
| `intentconfiguration` | Absichtskonfiguration anzeigen und Gewichtung festlegen/aktualisieren. | Lese- und Schreibzugriff | [!DNL Marketo Optimizer] | Lese- und Schreibvorgänge [!DNL Marketo Optimizer] |
| `intent-query` | Abfrage und Erläuterung der Absichtsergebnisse nach Person/Segment/Liste. | Lesen | [!DNL Marketo Optimizer] | Liest [!DNL Marketo Optimizer] |

## Versandzeitoptimierung {#sto}

| Skill | Funktion | Zugriff | Produkt | Backend (Datenfluss) |
|---|---|---|---|---|
| `send-time-optimization` | Überprüfen Sie den STO-Status und aktivieren/deaktivieren Sie ihn auf einem E-Mail-Knoten. | Lese- und Schreibzugriff | [!DNL Marketo Optimizer] | Lese- und Schreibvorgänge [!DNL Marketo Optimizer] |
| `send-time-report` | Abrufen/Anzeigen des STO-Leistungsberichts. | Lesen | [!DNL Marketo Optimizer] | Liest [!DNL Marketo Optimizer] |

## Kenntnisse {#knowledge}

| Skill | Funktion | Zugriff | Produkt | Backend (Datenfluss) |
|---|---|---|---|---|
| `product-knowledge` | Beantworten Sie Anleitungen/Konzeptfragen in [!DNL Marketo Optimizer] Dokumentation zu Experience League. | Lesen | Beide | Liest externe Dokumente - keine Produktdaten |

## Cross-Backend {#cross-backend}

Diese Fähigkeiten umfassen mehr als ein Backend:

- **`adapt-program`** — `gather_program_assets` liest [!DNL Marketo Engage] (`get_program`, `get_smart_campaign`, `list_emails`) und schreibt dann über `falcomcp_create_journey` — klassisches Backend.
- **`audience-creation`** - liest [!DNL Marketo Engage] Smart Lists (`get_smart_list`/`get_smart_campaign`) und schreibt dann [!DNL Marketo Optimizer] Personenlisten.
- **`journey-observability`** - [!DNL Marketo Optimizer] Lesevorgänge und ein `check_lead_in_marketo_static_list` [!DNL Marketo Engage].
- **`scoring-studio`** - liest [!DNL Marketo Engage] Lead-Felder/Aktivitätstypen zusammen mit [!DNL Marketo Optimizer] Scoring-Service.

Alle `falco-mcp_*`- und Journey/Token/Scoring/STO/FCS-Tools treffen auf [!DNL Marketo Optimizer] Services; CSV/Programm/Lead-Tools auf [!DNL Marketo Engage].
