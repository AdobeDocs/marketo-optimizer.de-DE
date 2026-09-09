---
title: Erstellen eines Programms aus einer Zusammenfassung
description: Verwenden Sie die Kenntnisse zur Programmerstellung in Marketo Optimizer, um Programme, Token, Personenlisten und Journey aus einer Kampagnenübersicht zu erstellen.
TQID: 'https://experienceleague.adobe.com/Bi7ZemHiGpKwxsYZkrfCyT5IzFAJ8ZTyFr8KxwO4z6w'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 1650dadf-b034-5ac9-a309-77ad1e2f5035id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 1110
ht-degree: 4%

---

# Erstellen eines Programms aus einer Zusammenfassung

[!DNL Adobe Marketo Optimizer] ist [_program_](../marketing/programs.md) der Container der obersten Ebene für Journey, Personenlisten, Token und Konfigurationen innerhalb einer Kampagne. In der [Chat](./chat-interface.md)-Oberfläche wird die gesamte Programmerstellung von Anfang bis Ende in einer geführten Konversation erstellt - vom Programm selbst, von Unterordnern, Token, Personenlisten und Journey-Personen.

* **Kenntnisse** - `program-creation`
* **Aufruf** - Laden Sie eine Zusammenfassung hoch und geben Sie _Erstellen eines Programms aus dieser Zusammenfassung_/_Erstellen eines Programms aus einer Zusammenfassung_ oder beschreiben Sie die Kampagne direkt.
* **Lese-/Schreibvorgänge in** - [!DNL Marketo Optimizer]; liest auch die Konfiguration des Programmtyps von Ihrem Mandanten

## Kurzer Upload

Klicken Sie auf _Anhängen_-Symbol in der Chat-Eingabe, um die Datei hochzuladen, und beschreiben Sie dann, was Sie möchten. Der Text des Briefs wird extrahiert und an einen Kollegen als Kontext übergeben (im Chat wird die Anzeige „Kampagnenbeschreibung hochgeladen: Dateiname (NkB)“ angezeigt).

### Unterstützte Dateitypen

| Format | Verhalten |
|---|---|
| `.txt`, `.md` | Direkt im Browser lesen |
| `.pdf`, `.docx`, `.xlsx`, `.json`, `.csv` | An den Backend-Textextraktions-Service gesendet |

Eine Datei mit einem Namen, der *Brief* enthält, wird automatisch als Kampagnenübersicht mit Tags versehen. Andernfalls leitet Coworker sie aus dem Kontext ab.

### Größenbeschränkung

Kurzer Text wird auf ca. 30.000 Zeichen (~7,5 K Token) gekürzt, bevor er den Kollegen erreicht. Sehr lange Slips werden an dieser Stelle abgeschnitten (durch einen `(truncated to 29KB)` Hinweis angedeutet). Legen Sie wichtige Kampagnendetails in den Vordergrund.

## Empfohlene Kurzinhalte

Die Flusseingabe liest die Kurzbeschreibung für die folgenden Eingaben - umfasst so viele wie möglich:

* Programmname und kurze Beschreibung/Zweck
* Signaltyp des Programms (z. B. Messe, Veranstaltung, Webinar, Roadshow, Konferenz oder Pflege)
* Zielgruppenkriterien für die Personenlisten
* Journey-Design - Anzahl, Einstiegskriterien, Touchpoints/Timing und Tag der Live-Schaltung
* Token (wiederverwendbare Werte wie Ereignisdatum, Veranstaltungsort, Betreffzeile)

Ein Mitarbeiter fordert vor dem Erstellen alle fehlenden Elemente an.

## Build-Phasen

Die Qualifikation läuft in drei Phasen: **AUFNAHME → GENEHMIGUNG → BUILD**. Es wird nichts erstellt, bis Sie die Genehmigung erteilen.

### Zulauf

Coworker extrahiert Folgendes aus der Zusammenfassung und fordert Sie auf, wenn etwas fehlt:

* Programmname
* Übergeordneter Ordner (standardmäßig Workspace-Stamm, falls nicht angegeben)
* Beschreibung
* Programmtyp (möglichst aus einer kurzen Formulierung abgeleitet)
* Zu erstellende Token (Name, Typ, Wert)
* Zielgruppenkriterien auflisten
* Journey - Anzahl, Einstiegskriterien, Touchpoints, Tag der Live-Schaltung

### Genehmigen

Der Kollege zeigt eine Zusammenfassung zur Bestätigung an, bevor er fortfährt:

`I'll create {program} in folder {id}, with {N} token(s), {N} dynamic people list(s), and {N} journey(s). Shall I proceed?`

Das Erstellungs-Tool wird erst aufgerufen, wenn Sie mit einer eindeutigen Genehmigung antworten (z _B._, _Weiter_, _Erstellen_, _Genehmigt_ und _Ja_).

### Build

Die Build-Schritte werden in einer festen Reihenfolge ausgeführt. Jeder hängt von den IDs ab, die im vorherigen Schritt generiert wurden.

| Schritt | Beschreibung | Tools | Ausgabe |
|---|---|---|---|
| **1. Ordner** | Löst den übergeordneten Ordner nach Namen auf oder verwendet den Workspace-Stamm; kann einen neuen Unterordner erstellen | `getRootTree`, `browseFolders`, `createFolder` | Ordnername + ID |
| **1.5. Programmtyp** | Sucht nach Mandantenprogrammtypen und wählt die Übereinstimmung für die Zusammenfassung aus | `browseProgramTypes` | Name + `programTypeId` eingeben |
| **2. Programm** | Erstellt das Programm unter dem aufgelösten Ordner und ist an den ausgewählten Typ gebunden. | `createProgram` | Programmname, ID, Typ |
| **3. Token** | Erstellt jedes `my.*`-Token im Programm | `createProgramToken` | Token-Namen |
| **4. Personenlisten** | Generiert attributbasierte Regeln aus Zielgruppenkriterien und erstellt die Liste der dynamischen Personen | `generate_ruleset`, `createSmartListWithRules` | Listenname + `smartListId` |
| **5. Journey** | Erstellt jede Personen-Journey mit einem Personen-Zielgruppen-Eintragsknoten, der mit der Schritt-4-Liste verknüpft ist. | `create_journey` | Journey-Namen, IDs |
| **6. Veröffentlichen** | Veröffentlicht oder plant die Journey, wenn ein Aufschaltdatum festgelegt und bestätigt wurde | `publish_journey_with_dates` | Live-/geplante Journey |
| **7. QA** | Optionale Validierungsvorschau und vollständige QA-Prüfung | `qa_program_preview`, `qa_program` | Bericht „Bestanden/Fehlgeschlagen/Warnungen“ |

**_step-Abhängigkeiten:_**

* Die Programm-ID (Schritt 2) ist erforderlich, bevor Token, Listen oder Journey angehängt werden können.
* Der `smartListId` aus Schritt 4 wird in Schritt 5 an `create_journey` übergeben - wenn er weggelassen wird, bleibt der Eintragsknoten für die Journey-Zielgruppe leer.
* Die Journey-Eingabeaufforderung beginnt immer mit _Mit dem Zielgruppenknoten Person als Einstiegspunkt beginnen_ um sicherzustellen, dass der Einstiegsknoten ausgefüllt ist.

## Ausgabe-Assets

### Programm

Der Container der obersten Ebene. Die Detailansicht zeigt die folgenden Registerkarten an:

| Tab | Inhalt |
|---|---|
| **Übersicht** | Name, Beschreibung, Programmtyp, Status, Ordnerspeicherort, Zeitstempel |
| **Attribute** | Benutzerdefinierte Felder vom Typ (nur wenn sie vom Programmtyp aktiviert werden) |
| **Token** | Für dieses Programm vorgesehene Token `my.*` |
| **Journeys** | Im Programm enthaltene Journey |

### Token

Wiederverwendbare `my.*` im Umfang des Programms (z. B. `my.eventDate`). Jeder hat einen -Typ - einen von `text`, `date`, `rich text`, `score` oder `number` - und einen -Wert. Sie werden innerhalb von E-Mails und Inhalten im Rahmen des Programms aufgelöst.

### Personenliste

Eine dynamische (intelligente) Personenliste, die aus Zielgruppenkriterien über generierte, attributbasierte Regeln erstellt wurde, die im Rahmen des Programms erstellt wurden.

### Journey

Ein Personen-Journey, der mit einem Einstiegsknoten für die Zielgruppe einer Person beginnt, der an die Personenliste in Schritt 4 gebunden ist, gefolgt von den Touchpoints der Zusammenfassung (z. B. _Begrüßungs-E-Mail nach einem Tag senden, Nachbereitung nach drei Tagen_). Ist ein Tag für die Live-Schaltung festgelegt, kann die Journey sofort veröffentlicht oder geplant werden.

## Auflösung des Programmtyps

Programme sind bei **Erstellung** einem vom Mandanten definierten Programmtyp gebunden. Dies kann nachträglich nicht mehr geändert werden. Der Fluss löst den Typ in jedem Fall explizit über `browseProgramTypes` auf.

| Fall | Verhalten |
|---|---|
| **Mehrere Typen verfügbar** | Passt kurze Formulierungen an einen Typ an (z. B. Messe/Stand/Ausstellung = *Messe*/*Event*; Webinar = *Webinar*/*Event*; Nurture/Drip = *Nurture*; kein klares Signal = *Default*). Wenn keine Übereinstimmung gefunden wird, listet Coworker verfügbare Typen und Aufgaben auf. |
| **Nur-Standard-Mandant** | Verwendet *Standard* und merkt an, dass ein Administrator benutzerdefinierte [Programmtypen“ hinzufügen ](../admin/program-types.md). |
| **Keine Typen konfiguriert** | Stoppt — die Erstellung würde fehlschlagen. fordert einen Administrator auf, Programmtypen bereitzustellen, bevor es erneut versucht wird. |

## Standardwerte

| Einstellung | Standard |
|---|---|
| **Ordner** | Workspace-Stammordner (wenn kein Ordner angegeben ist) |
| **Programmtyp** | *Standard* (wenn kein kurzes Signal und keine manuelle Auswahl) |
| **Personalization-Attribute** | Abgeleitete Rolle, Abgeleitete Absicht, Interaktionsstufe standardmäßig enthalten (Opt-out verfügbar) |
| **Wird veröffentlicht** | Nicht automatisch für zukünftige Live-Schaltungstermine - Wird als manueller `ACTIVATE journey by {date}`-Schritt angegeben. Sofortige Veröffentlichung nur bei sofortigem Start und Bestätigung |
| **Validierungs-Gate** | Vor der expliziten Genehmigung wird kein Asset erstellt |

## Einschränkungen

| Einschränkung | Detail |
|---|---|
| **Kurze Längenbegrenzung** | ~30.000 Zeichen; abgeschnittene Slips verlieren nachfolgenden Inhalt - stellen Sie Essentials an die erste Stelle |
| **Unveränderlicher Programmtyp** | Kann nach der Erstellung nicht mehr geändert werden. Überprüfen Sie vor der Genehmigung den richtigen Typ. |
| **Erforderliche interne Felder** | `parent` und `programTypeId` sind immer festgelegt. Das Auslassen von `parent` führt dazu, dass der Zugriff verweigert wird. Das Auslassen des Typs fällt unbeaufsichtigt auf *Standard* zurück. |
| **Journey benötigt eine Personenliste** | Die `smartListId` aus Schritt 4 ist für Schritt 5 obligatorisch. Der Fluss erzwingt dies |
| **Async list membership** | Statische Listen (aus Kriterien) werden über mehrere Minuten hinweg gefüllt - nicht sofort |
| **Fehlerbehandlung** | Tool-Fehler werden mit dem exakten Fehler gemeldet. Der Mitarbeiter wird aufgefordert, die Eingabe zu bestätigen und es erneut zu versuchen |
| **Namenskollisionen** | Nicht automatisch aufgelöst — es wird ein anderer Name angefordert |
| **Perimeter** | Nur Marketo Optimizer. [!DNL Marketo Engage] Benutzer sollten die separaten Fähigkeiten zur Programmerstellung bzw. Programmplanung verwenden. |


## QA-Prüfung

Nach Abschluss des Builds bietet Coworker:

> „Soll ich vor dem Start eine QS-Prüfung durchführen, um alles zu validieren?“

Bestätigen Sie, dass `qa_program_preview` ausgeführt wird, gefolgt von `qa_program`. Der Prozess gibt einen Bericht mit bestanden, fehlgeschlagen und allen Warnungen sowie empfohlenen nächsten Schritten zurück.
