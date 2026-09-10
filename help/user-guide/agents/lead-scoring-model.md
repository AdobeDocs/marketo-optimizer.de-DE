---
title: Erstellen benutzerdefinierter Bewertungsmodelle
description: Erstellen, Anzeigen und Veröffentlichen benutzerdefinierter Lead-Bewertungsmodelle in Marketo Optimizer mithilfe der Scoring-Studio-Kenntnisse in der Benutzeroberfläche des Coworker Chat.
TQID: 'https://experienceleague.adobe.com/OAY0CzFPTyUi7NCPbRnxGkG6nnndPygbwGlbv9u2oeA'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 1650dadf-b034-5ac9-a309-77ad1e2f5035
source-git-commit: 96a923c923a6290b9d90e4ffc8e161d78f029c47
workflow-type: tm+mt
source-wordcount: 468
ht-degree: 2%

---

# Erstellen benutzerdefinierter Scoring-Modelle

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_scoring_studio"
>title="Scoring Studio"
>abstract="Verwenden Sie die Scoring Studio-Kenntnisse zum Erstellen, Konfigurieren und Veröffentlichen benutzerdefinierter Lead-Scoring-Modelle über die Chat-Oberfläche des Kollegen."

Die [_Scoring Studio_-](./skills.md#scoring-signals) in [!DNL Adobe Marketo Optimizer] bietet eine KI-native Lead-Scoring-Lösung, mit der Sie Lead-Scoring-Modelle erstellen, konfigurieren und veröffentlichen können. Das Studio kombiniert einen agentengesteuerten Workflow mit einer visuellen Benutzeroberfläche. Sie können Bewertungsmodelle durch Eingabeaufforderungen in natürlicher Sprache in der [Coworker Chat-Oberfläche](./chat-interface.md) oder durch direkte Interaktion mit den Benutzeroberflächen-Steuerelementen erstellen.

* **Kenntnisse** - `scoring-studio`
* **Aufruf** - Verwenden Sie einen Schrägstrich, um Scoring Studio zu öffnen. Beispiel: _„Open Scoring Studio.“_
* **Lese-/Schreibvorgänge an** - [!DNL Marketo Optimizer] Scoring-Service; liest [!DNL Marketo Engage] Lead-Felder und Aktivitätstypen

Bei einem Launch ruft der Mitarbeiter automatisch relevanten Kontext ab - einschließlich Aktivitätstypen, Lead-Feldern, Personenlisten und vorhandenen Bewertungslisten -, um seine Vorschläge in Ihren Daten zu begründen.

![Scoring Studio in der Benutzeroberfläche des Coworker chat gestartet](./assets/scoring-studio.png){width="700" zoomable="yes"}

## Scoring-Modell erstellen {#create-model}

Wenn Sie Scoring Studio öffnen, schlägt Coworker ein relevantes Beispiel-Scoring-Modell vor, das mit einer statischen Liste und einer Reihe von bewerteten Aktivitäten vorausgefüllt ist. Sie können diesen vorgeschlagenen Ausgangspunkt annehmen oder Ihre eigene Aufforderung angeben, um ein benutzerdefiniertes Modell zu definieren.

### Vorschau des Modells {#preview-model}

Nachdem Sie eine Eingabeaufforderung eingegeben haben, generiert Coworker eine Modellvorschau, bevor Sie Änderungen vornehmen. Die Vorschauoberflächen:

* Verwendete Scoring-Dimensionen
* Bewertete Attribute und Aktivitäten
* Statische Listen oder Smart-Listen, die als Segmente angewendet werden
* Eine Zusammenfassung des Modellziels, des Zielsegments und der primären Signale

Sie können die Vorschau überprüfen und wählen, ob Sie das Modell basierend darauf erstellen möchten, oder den Chat vor der Fertigstellung weiter verfeinern.

### Modellstruktur {#model-structure}

Das erstellte Modell ist in _Dimensionen_ und _Signale_ organisiert. Sie können jedes Signal über das Bedienfeld „Eigenschaft“ in der Benutzeroberfläche konfigurieren:

* **Signaltyp** — Aktivitäts- oder attributbasiert
* **Aktivität oder Attribut** - Das spezifische Element, das bewertet werden soll
* **Signalparameter** — Einstellbare Einstellungen für das Signal

Sie können Modelle vollständig über Coworker mit natürlicher Sprache erstellen und konfigurieren oder direkt mit den Benutzeroberflächen-Steuerelementen interagieren.

## Scoring-Modell veröffentlichen {#publish-model}

Weisen Sie nach Fertigstellung Ihres Modells einen Mitarbeiter an, es zu veröffentlichen. Der Veröffentlichungsprozess verarbeitet automatisch Folgendes:

| Schritt | Was passiert? |
| --- | --- |
| **Regelkompilierung** | Alle Bewertungsregeln werden kompiliert und validiert |
| **Erstellen von Score-Aufgaben** | Eine geplante Bewertungsaufgabe wird erstellt und für die tägliche Ausführung konfiguriert |

Nach der Veröffentlichung haben Sie auch die Möglichkeit, einen manuellen Trigger auszuführen, um Scores sofort zu verarbeiten.

## Scoring-Ergebnisse anzeigen {#view-results}

Nach Abschluss eines Scoring-Durchgangs werden die Bewertungen über den Lead-Importprozess zurück in [!DNL Marketo Engage] geschrieben. Nach Abschluss des Imports können die aktualisierten Scores direkt in [!DNL Marketo Engage] überprüft werden.

Nach jedem Durchlauf können Sie eine Ergebniszusammenfassung anzeigen, die Folgendes anzeigt:

* Wie viele Personen wurden bewertet?
* Die individuelle Punktzahl ändert sich pro Person

Ein Administratorprotokoll ist für die Überprüfung zusätzlicher Ausführungsdetails verfügbar.
