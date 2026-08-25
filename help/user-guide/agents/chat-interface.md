---
title: Chat-Oberfläche
description: Verwenden Sie das Bedienfeld „Coworker chat“ in Marketo Optimizer, um Programme, Journey und Listen in natürlicher Sprache oder mit dem Schrägstrich (/) zu erstellen.
source-git-commit: 75b481faf0d66210329f95c8afabdfa59e7bcb79
workflow-type: tm+mt
source-wordcount: '859'
ht-degree: 0%

---

# Chat-Oberfläche

Das Chat-Panel ist in [!DNL Adobe Marketo Optimizer] eingebettet. Hier können Sie mit den KI-Agenten interagieren, indem Sie sie in einfacher Sprache verwenden, um Programme und Journey zu erstellen, Personenlisten zu erstellen und zu vergleichen, Leads zu untersuchen, die Bewertung zu konfigurieren und vieles mehr.

Wählen Sie _linken Navigationsbereich das Symbol &quot;_&quot; aus, um das Bedienfeld zu öffnen. Die Panel-Kopfzeile verfügt über vier Steuerelemente:

| Kontrollvariante | Beschreibung |
|---------|-------------|
| **Neue Konversation** | Neuen Chat starten (löscht den aktuellen Thread). |
| **Konversationsverlauf** | Öffnen Sie vergangene Unterhaltungen, damit Sie eines erneut öffnen können. |
| **Bedienfelder wechseln** | Verschieben Sie das Chat-Bedienfeld auf die andere Seite des Arbeitsbereichs. |
| **Reduzieren** | Blenden Sie das Bedienfeld aus, um dem Arbeitsbereich mehr Platz zu geben. |

Unten im Bedienfeld befindet sich das Meldungsfeld, in dem Sie Folgendes tun können:

* Fügen Sie eine Nachricht hinzu und drücken Sie **Eingabetaste** um zu senden (**Umschalt+Eingabetaste** fügt einen Zeilenumbruch ein).
* Hängen Sie eine Datei mithilfe des _Anhängen_-Symbols an (unterstützte Formate: `.txt`, `.md`, `.csv`, `.json`, `.xlsx`, `.docx`, `.pdf`). Verwenden Sie CSV- und Tabellen-Uploads, um einen Lead-Import zu starten.

## Kollegen fragen

Es gibt zwei gleichermaßen gültige Arten Arbeit zu erledigen. Man muss nie das Schrägstrich-Menü benutzen.

**Natürliche Sprache** - Geben Sie Ihre Anfrage so ein, wie Sie sie einem Kollegen sagen würden:

* _„Erstellen Sie eine Begrüßungs-Journey für neue Testanmeldungen._
* _„Warum ist john@acme.com nicht auf diese Journey gekommen?“_
* _„Vergleichen Sie die Listen meiner Webinar-Teilnehmer im 3. Quartal mit den Listen der Unternehmenskonten.“_

Der Agent ordnet Ihre Formulierungen hinter den Kulissen den richtigen Kenntnissen zu und führt den entsprechenden Workflow aus.

**Menü mit Schrägstrich (/)** — Geben Sie `/` ein, um ein durchsuchbares Menü mit allem zu öffnen, was ein Kollege tun kann. Dies ist nützlich, wenn Sie Funktionen entdecken oder direkt zu einem bekannten Workflow springen möchten.

## Der Schrägstrich (/) im Menü

Verwenden Sie eine `/` am Anfang des Meldungsfelds oder nach einem Leerzeichen, um das Menü zu öffnen. Während Sie mit der Eingabe fortfahren, filtert die Liste nach Name, Beschreibung oder ID - zum Beispiel wird `/journey` auf Journey-bezogene Befehle eingegrenzt.

Verwenden Sie **/**, um durch Einträge zu navigieren **(** oder **Tabulator** auszuwählen und **Esc**, um sie zu schließen. Sie können auch direkt auf einen Eintrag klicken.

Menüeinträge sind in beschriftete Abschnitte unterteilt:

| Abschnitt | Enthält |
|---------|----------|
| **untersuchen** | Diagnostische, schreibgeschützte Suchen (z. B. Lead-Ermittlung, Absichtsabfragen). |
| **Validieren** | QA- und Audit-Workflows |
| **Build** | Erstellungs-Workflows (Programme, Journey, Listen, Bewertung). |
| **Importieren** | CSV-Leadimport. |
| **Sonstige** | Alles, was nicht in die oben genannten Kategorien fällt. |

Im Menü werden auch **Connectoren** (z. B. _Marketo durchsuchen_ und ein Auswahldialogfeld geöffnet) und **Navigationskürzel** aufgeführt, die zu einem Arbeitsbereichsbildschirm springen.

### Menüelement auswählen

Wenn Sie eine Qualifikation oder einen Agenten aus dem Menü auswählen, wird eine Starteraufforderung in das Meldungsfeld eingefügt, die Sie bearbeiten können - sie wird **automatisch**. Wenn Sie beispielsweise _Kampagnen planen_ in &quot;_&quot; auswählen, wird ein neues Marketo-Programm für [Kampagnenname“ ]. Ich lade die Zusammenfassung hoch.“_ Füllen Sie die Platzhalter in Klammern aus und drücken Sie **Eingabetaste** um zu senden.

Connectoren öffnen ein modales Fenster, anstatt Text einzufügen. Über Navigationsbefehle gelangen Sie direkt zu diesem Bildschirm im Arbeitsbereich.

>[!NOTE]
>
>Einige Befehle werden ausgegraut angezeigt und als _In Kürze verfügbar_ gekennzeichnet. Diese werden durch Feature Flags eingegrenzt und sind noch nicht für Ihr Konto aktiv. Die Auswahl eines Flags bewirkt nichts. Welche Funktionen verfügbar sind, hängt davon ab, welche für Sie aktiviert sind.

## Skills

Eine Qualifikation ist ein gepackter Workflow, den der Agent ausführen kann - die Bausteine hinter dem `/` und den Anforderungen in natürlicher Sprache. Jede Qualifikation umfasst schrittweise Anweisungen und die spezifischen Tools, die für einen Auftrag erforderlich sind (z. B. „Veröffentlichen eines Journey&quot;, „Vergleichen von zwei Personenlisten“, „Erstellen eines Bewertungsmodells„).

Eine vollständige Liste _[derzeit unterstützten](./skills.md)_ finden Sie unter „Mitarbeiterqualifikationen“.

Wichtige Informationen zu Kenntnissen über Fähigkeiten:

* **Kenntnisse beziehen sich auf das Produkt.** In [!DNL Marketo Optimizer] sehen Sie verschiedene produktspezifische Fertigkeiten (Journey, Personenlisten, Bewertung, Kanäle, Sendezeitoptimierung usw.). Einige Fähigkeiten sind nur [!DNL Marketo Engage] und ein paar arbeiten in beiden Produkten (Leadimport, Produktwissen). Sie sehen nur Fähigkeiten, die für Ihren aktuellen Standort relevant sind.
* **Sie müssen sich die Namen von Kenntnissen nicht merken.** Beschreiben Sie Ihr Ziel, und der Agent wählt die passende Qualifikation aus. Das `/` ist eine schnellere, auffindbare Verknüpfung zu denselben Workflows.
* **Manche Fähigkeiten lesen nur; andere ändern Dinge.** Investigative Fähigkeiten und Berichtsfähigkeiten (z. B. Lead-Ermittlung, Absichtsabfrage, Sendezeitbericht) lesen nur Daten. Erstellen und konfigurieren Sie Fertigkeiten (z. B. Journey-Erstellung, Bewertung), um Daten zu erstellen oder zu ändern.

## Folgenachrichten

Nach Antworten von Kollegen werden oft mehrere anklickbare Folgeaufforderungen angezeigt, die genau auf das zugeschnitten sind, was Sie gerade getan haben. So kann beispielsweise nach dem Erstellen einer Journey Folgendes geboten werden: _„Veröffentlichen Sie diese Journey&quot;_ oder _„Warten hinzufügen“_. Klicken Sie auf eins, um ohne Eingabe fortzufahren. Hierbei handelt es sich lediglich um Vorschläge. Stattdessen können Sie auch Ihre eigene nächste Nachricht eingeben.

## Tipps

* **Verwenden Sie Kennungen.** Geben Sie bei der Untersuchung oder Bearbeitung die E-Mail-Adresse, den Personennamen, den Journey-Namen oder den Listennamen an, damit der Agent das richtige Asset bearbeiten kann.
* **Verwenden Sie `/` zum Erkunden.** Wenn Sie sich nicht sicher sind, was ein Kollege tun kann, öffnen Sie das Menü `/` und überspringen Sie die Kategorien.
* **Bearbeiten Sie die Starteraufforderung.** Durch Auswahl einer Qualifikation erhalten Sie eine Vorlage - ersetzen Sie die `[bracketed]` Platzhalter vor dem Versand.
* **Zuerst für Importe hochladen.** Für einen Lead-Import fügen Sie zuerst die CSV-Datei hinzu und beschreiben Sie dann, was Sie damit tun möchten.
* **Beginnen Sie eine neue Konversation** wenn Sie zu einer nicht verwandten Aufgabe wechseln, sodass sich ein früherer Kontext nicht auf die neue Anfrage auswirkt.
