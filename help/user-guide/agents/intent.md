---
title: Konfigurieren und Analysieren der Absicht
description: Erfahren Sie, wie Sie die Aktivitätsgewichte für das Modell der Absichtsbewertung konfigurieren und die Absichten auf Lead-Ebene mit Rangfolge-, Profil-, Trend- und Vergleichsberichten analysieren.
source-git-commit: 8b3ea5f52fc50ea6c995ace44dece90247deff8b
workflow-type: tm+mt
source-wordcount: '978'
ht-degree: 0%

---


# Konfigurieren und Analysieren der Absichten

In [!DNL Adobe Marketo Optimizer] bietet ein Mitarbeiter zwei Fähigkeiten in der Kategorie _Intent_ an. Jeder Kunde wiegt Marketing-Aktivitäten anders, sodass Sie mit diesen Fähigkeiten konfigurieren können, was für Ihr Unternehmen wichtig ist. Anschließend können Sie überprüfen, was die Intent-Pipeline erzeugt hat.

| Skill | Befehl | Funktion |
| --- | --- | --- |
| **Intent-Konfiguration** | `/intent-configuration` (Alias `/intent-config`) | Konfigurieren Sie die Aktivitätsgewichte für das Modell der Absichtsbewertung für Personen |
| **Analyseabsicht** | `/analyze-intent` | Abfragen und Validieren von Absichtsebenen-Ranking, Trend-, Produkt- und Keyword-Taxonomie und Vergleichsberichten |

Wenn Sie eine Qualifikation auswählen, wird ihre Beschreibung als Starteraufforderung in die Chat-Eingabe eingefügt, die Sie vor dem Senden bearbeiten können.

## Konfigurieren des Gewichtungsmodells {#configure-model}

Gehen Sie wie folgt vor, um die Aktivitätsgewichte für das Modell „Intent Score“ zu konfigurieren. Weitere Informationen zur Konfiguration und Bewertungsgewichtung finden Sie unter [_Absichtskonfiguration_](../audiences/intent-configuration.md).

1. Rufen Sie die Qualifikation auf (`/intent-configuration`) und drücken Sie **Eingabetaste**.

   Coworker öffnet das **[!UICONTROL Intent Configuration]**-Bedienfeld als Workspace-Registerkarte. Im Bedienfeld wird jede Absichtsaktivität der Pipeline aufgelistet. Für jede Aktivität werden ein **[!UICONTROL KI-]**) und ein bearbeitbarer **[!UICONTROL Gewichtung]** -Wert angezeigt. Außerdem werden die Modelle aufgelistet, die bereits für Ihren Mandanten vorhanden sind. Es kann immer nur ein Modell _[!UICONTROL Aktiv]_ sein: das, das derzeit die Bewertung steuert.

1. Um Änderungen vorzunehmen, öffnen Sie ein vorhandenes _[!UICONTROL Entwurf]_-Modell oder wählen Sie **[!UICONTROL Duplizieren]** im _[!UICONTROL Aktiv]_-Modell aus, um mit seiner aktuellen Gewichtung zu beginnen.

1. Anpassen der Gewichtungen Zeile für Zeile.

   Markieren Sie beispielsweise eine Aktivität mit niedrigem Wert wie **[!UICONTROL Zur Opportunity hinzufügen]** als **[!UICONTROL Trivial]** und erhöhen Sie **[!UICONTROL E-Mail-]** oder **[!UICONTROL Link klicken]** auf **[!UICONTROL Wichtig]**, wenn diese Aktivitäten für Ihr Unternehmen wichtiger sind.

1. Wählen Sie **[!UICONTROL Speichern]** aus.

   Beim Speichern werden Sie aufgefordert, das Modell jetzt zu aktivieren. Durch Bestätigen wird das aktuelle _[!UICONTROL Aktiv]_-Modell ersetzt, das automatisch herabgestuft wird.

## Absichtsbewertung

Bei der Absichtspunktzahl für einen Lead werden drei Dinge berücksichtigt:

* **Die hier konfigurierte** für jeden Aktivitätstyp.
* **Inhaltsrelevanz**: Schlüsselwörter, die aus den mit den einzelnen Aktivitäten verknüpften Assets extrahiert wurden.
* **Häufigkeit**: Wie oft der Lead mit diesem Inhalt interagiert hat.

Weitere Informationen zu diesen Metriken, einschließlich der von KI vorgeschlagenen Gewichtung, Inhaltsrelevanz und Einschränkungen, finden Sie unter [Absichtskonfiguration](../audiences/intent-configuration.md).

## Absichtsberichte

Um die vier Berichtstypen einzuführen, die er generieren kann, rufen Sie `/analyze-intent` auf, um einen Kollegen aufzufordern. Der Mitarbeiter wartet dann auf eine Folgeanfrage, in der ein Lead, ein Produkt oder ein Vergleich benannt wird. Jeder Bericht wird als eigene Registerkarte im Arbeitsbereich-Bedienfeld geöffnet und Coworker fügt auch eine Übersichtskarte in den Chat mit einer Schaltfläche _[!UICONTROL Bericht öffnen]_ ein.

### Absichts-Ranking-Bericht

**Empfohlene Eingabeaufforderung:** _„Meine mit hoher Absicht erstellten Leads für &lt;product> anzeigen“_

Die Leads werden nach der Stärke des Intent-Signals für ein Produkt oder ein Keyword sortiert. Die Spalten umfassen Lead, E-Mail, Konto, Branche, Produkte, Bewertung, Absichtsebene und die Top-Aktivitätsquelle. Die _[!UICONTROL 7-Tage-Delta]_-Spalte zeigt, wie sich der Intent-Score in der letzten Woche verschoben hat. Die Spalte _[!UICONTROL Letzte Aktualisierung]_ zeigt an, wann der Lead zuletzt interagiert hat, d. h. wann sich der Score zuletzt geändert hat. Filter für die Produkt- und Absichtsebene sind Live-Dropdown-Listen, sodass Sie nicht auf das beschränkt sind, was Sie in der Eingabeaufforderung eingegeben haben. Spalten sind sortierbar.

Andere Eingabeaufforderungen, die denselben Bericht öffnen:

* „Ordnen Sie die 10 besten Leads nach Absichtspunktzahl für Photoshop ein“
* „Auflisten von Leads mit hohem Intent für Photoshop&quot;
* „Zeigen Sie mir Leads, deren Intent-Score für Photoshop in dieser Woche am meisten gesprungen ist.“
* „Welcher Marktführer im Einzelhandel verfolgt für Creative Cloud einen mittleren bis hohen Anspruch“
* „Finden Sie in einem Webinar Leads mit Absichtspunktzahlen, die von Asset-Downloads beigetragen werden.“
* „Auflisten von Leads mit hoher Absicht, deren wichtigste Aktivitätsquelle E-Mail-Klick ist“
* „Leads mit Absicht anzeigen, die nur von Web-Besuchen beigetragen werden, mit Ausnahme von Downloads oder Webinaren“

### Absichtsprofilbericht

**Vorgeschlagene Eingabeaufforderung:** _„Absichtsprofil von &lt;Lead> anzeigen“_

Ein kurzer Schnappschuss eines Leads: Welche Produkte und Keywords interessieren sich für sie und wie bewerten sie die einzelnen? Verwenden Sie diesen Bericht, sobald ein Rangfolgebericht einen Lead aufgedeckt hat, den es zu untersuchen lohnt. Es hilft Ihnen, Journey, Rollen und Einkaufsgruppen um die tatsächliche Produktabsicht des Leads herum zu formen.

Weitere Eingabeaufforderungen:

* „Welche Produkte interessieren sich am meisten für &lt;lead>?“
* „Woran interessiert sich &lt;lead> derzeit?“
* „Geben Sie mir eine Zusammenfassung aller Produkte und Schlüsselwörter, für die Lead X eine Absicht gezeigt hat.“

### Absichtstrendbericht

**Empfohlene Eingabeaufforderung:** _„Anzeigen des Verlaufs der &lt;Absichtsbewertung für &lt;Produkt> für &lt;Lead> in den letzten 30 Tagen“_

Stellt die Absichtsbewertung eines Leads für ein Produkt im Zeitverlauf dar. Damit lassen sich Wendepunkte identifizieren. Ein Wert, der beispielsweise wochenlang konstant bleibt und dann steil fällt, signalisiert eine Änderung des Interesses und nicht irrelevante Daten. Sie können den Zeitrahmen auf 7, 30 oder 100 Tage anpassen.

Weitere Eingabeaufforderungen:

* „Was ist der Intent Surge für Acrobat diese Woche für Lead X?“
* „Trend der Absichten für einen Lead in diesem Monat anzeigen“
* „Ist die Absicht von Lead X für Acrobat in diesem Monat gestiegen oder gesunken?“

### Bericht zum Absichtsvergleich

**Empfohlene Eingabeaufforderung:** _„Absichtstrends für Photoshop mit denen von Illustrator in allen Leads in den letzten 30 Tagen vergleichen“_

Vergleicht die Absicht im Zeitverlauf für zwei Leads oder zwei Produkte als paralleles Diagramm plus einer Zusammenfassungstabelle (aktueller Punktwert, Punktzahl vor N Tagen, Delta). Der Zeitrahmen ist auf die gleiche Weise anpassbar wie der Trendbericht. Die Absicht kann sich täglich, Minute für Minute oder stündlich ändern, sodass ein kurzes flaches Fenster nicht unbedingt bedeutet, dass nichts passiert.

Weitere Eingabeaufforderungen:

* „Vergleich der Absichten von Acrobat und Photoshop im letzten Quartal“
* „Vergleich von Lead X mit der Absicht von Lead Y für Creative Cloud&quot;
* „Welche Zielgruppe hat einen höheren Durchschnittswert: Photoshop oder Illustrator?“
* „Personas für Acrobat vergleichen: Wer hat die höhere Gewinnquote?“
* „Absichten für Photoshop in den Segmenten „Einzelhandel und Finanzen“ nebeneinander anzeigen“

## Weiterverfolgung von Berichten {#report-follow-up}

Absichtsberichte sind schreibgeschützt und haben keine eigenständige Exportoption. Um auf das zu reagieren, was ein Bericht anzeigt, verwenden Sie stattdessen andere Fähigkeiten.

* Eingabeaufforderung mit _„Auflisten der Leads mit der obersten Absicht für Creative Cloud&quot;_ Der Mitarbeiter verwendet die `/analyze-intent` Kenntnisse, um die angegebene Liste zu erstellen.

* Eingabeaufforderung mit _„Erstellen einer Personenliste mit dieser Liste“_ Ein Mitarbeiter übergibt den Lead-Satz an die [Zielgruppenerstellungs-Qualifikation](./audience-creation.md) die die Personenliste direkt erstellt. Es ist kein manueller Export- oder Importschritt erforderlich.
