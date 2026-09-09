---
title: Journey-Traffic-Steuerung
description: Erfahren Sie, wie die Journey-Traffic-Steuerung in Marketo Optimizer die KI-Bewertung über sieben gewichtete Dimensionen hinweg verwendet, um jede Person nur für die Einzel-Journey mit der besten Anpassung zu registrieren, wenn sich Zielgruppen überschneiden.
TQID: 'https://experienceleague.adobe.com/MRPRSUHGHV9CZdp4ZIqxsIsIaB6U86DDiau7RE2r0ak'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 3c1de303-7a7c-59a6-abca-8c534730e19cid: 46e599c6-e20f-5f67-9824-93415016f66bid: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 1543
ht-degree: 0%

---

# Journey-Traffic-Steuerung

Beim Journey-Traffic-Control (JTC) wird das beste Journey für eine Person priorisiert, wenn sich Zielgruppen überschneiden. Wenn eine Person für mehrere JTC-fähige Journey qualifiziert ist, werden sie von einem KI-Modell anhand jedes Bewerbers ausgewertet und zur am besten geeigneten Journey hinzugefügt, sodass sie von den anderen ausgeschlossen werden.

>[!NOTE]
>
>Die Journey-Traffic-Steuerung funktioniert für [!DNL Journey Optimizer B2B Edition] und [!DNL Marketo Optimizer] auf die gleiche Weise. Die Funktionen und die Logik sind identisch, es gibt nur geringfügige Unterschiede in der Benutzeroberfläche zwischen den Ebenen. Die Informationen auf dieser Seite spiegeln das [!DNL Marketo Optimizer] Erlebnis wider.

Nachdem der Patient die Journey abgeschlossen hat, wird er erneut auf die verbleibenden Journey untersucht, für die er qualifiziert bleibt. JTC fügt sie dann auf die nächstbeste Journey ein und so weiter. Dadurch wird verhindert, dass dieselbe Person mehreren sich überschneidenden Journeys gleichzeitig zugewiesen wird, und sichergestellt, dass jeder Kontakt zuerst das relevanteste Erlebnis erhält.

>[!NOTE]
>
>Derzeit kann eine Person nur jeweils in einer von JTC ausgewählten Journey platziert werden. Für eine zukünftige Version ist eine Option für die Administratorkonfiguration geplant, mit der eine Person gleichzeitig für mehr als eine Journey registriert werden kann.

## Scoring-Dimensionen {#scoring-dimensions}

Das Modell bewertet jede Journey-Kombination einer Person über sieben Bewertungsdimensionen hinweg. Jede Dimension wird unabhängig bewertet und dann entsprechend der von Ihnen konfigurierten Gewichtung kombiniert, um eine endgültige Übereinstimmungswahrscheinlichkeit für diese Person und diesen Journey zu ermitteln. Die Journey mit der größten Übereinstimmung wird ausgewählt.

| Dimension | Was ausgewertet wird |
|---|---|
| Absichtsausrichtung | Verhaltensbezogene Absichtssignale: Keyword-Suche, Besuche auf Produktseiten, Download von Inhalten, E-Mail-Öffnungen/Clickthrough und Preisfindungs-Seitenaktivität. |
| Zielgruppenanpassung | Wie gut die Person mit der [Zielgruppe](./person-audience-node.md) für die Journey übereinstimmt. |
| Persona Fit | Ausrichtung zwischen der Rolle/[ der Person ](../audiences/personas.md) der Journey. |
| Firmographischer Anfall | Attribute auf Unternehmensebene (wie Branche, Größe und Umsatz). |
| Demografische Übereinstimmung | Demografische Attribute auf Personenebene. |
| Psychographische Ausrichtung | Ausrichtung auf Einstellung/Präferenz. |
| Eingriffssitz | Neuigkeit und Tiefe der [ (Interaktion](../audiences/engagement-scores.md). |

Dimensionen, für die eine Person keine Daten hat, werden automatisch übersprungen, sodass die Bewertung nie für fehlende Attribute bestraft wird.

>[!IMPORTANT]
>
>Mindestens zwei Journey müssen JTC aktiviert haben, damit die Funktion etwas Sinnvolles tun kann. Die Aktivierung auf einer einzigen Journey ist ineffektiv, da es keine konkurrierenden Journey gibt, die es zu schlichten gilt. Erst wenn zwei oder mehr Journey JTC-fähig sind, beginnt das Modell mit der Konfliktlösung.

## Voraussetzungen {#prerequisites}

Bevor die Traffic-Steuerung von Journey Ergebnisse liefern kann, sollten Sie Folgendes beachten:

* **Für das Reporting ist eine veröffentlichte, JTC-fähige Journey erforderlich.** Auf _[!UICONTROL Registerkarte]_ Reporting“ werden erst dann Daten angezeigt, wenn mindestens eine Journey mit aktivierter Journey-Traffic-Steuerung veröffentlicht wurde.
* **Für die Simulation ist mindestens eine veröffentlichte Journey in der Instanz erforderlich.** Bei der Simulation werden [Profile](../audiences/people-lists.md) ausgewertet, die sich bereits in Live-Journey befinden. Daher muss mindestens eine veröffentlichte Journey in der Instanz vorhanden sein, aus der Profile gezogen werden können. Bei der Simulation selbst muss JTC nicht aktiviert sein (siehe [_Bewertung simulieren_](#simulate-scoring)).

## Erste Schritte {#get-started}

Wählen Sie im linken Navigationsbereich die Option **[!UICONTROL Traffic]** Steuerung für Journey. Die angezeigte Seite weist zwei Registerkarten auf:

* **[!UICONTROL Reporting]** - Ergebnisse der Traffic-Steuerungsdurchgänge werden angezeigt (erst ausgefüllt, nachdem JTC auf Live-Journey ausgeführt wurde).
* **[!UICONTROL Konfiguration]** - Passen Sie die Bewertungsdimensionen an, simulieren Sie Ergebnisse und wählen Sie aus, welche Journey teilnehmen sollen.

>[!IMPORTANT]
>
>Für einen Neukunden, der noch nie die Traffic-Steuerung von Journey verwendet hat, ist die _[!UICONTROL Reporting]_ leer. Das Reporting spiegelt nur Journey wider, auf die die Traffic-Steuerung angewendet wurde und die ausgeführt werden. Beginnen Sie mit der _[!UICONTROL Konfiguration]_.

## Registerkarte „Konfiguration“ {#configuration-tab}

Die _[!UICONTROL Konfiguration]_ hat zwei Abschnitte: **[!UICONTROL Anpassen der Dimensionsbewertung]** und **[!UICONTROL Journey auswählen]**.

### Anpassen der Dimensionsbewertung {#adjust-dimension-scoring}

In diesem Abschnitt legen Sie fest, wie viel jeder der sieben Dimensionen zum endgültigen Übereinstimmungsergebnis beiträgt. Jede Dimension kann auf &quot;**[!UICONTROL &quot;,]****[!UICONTROL Niedrig]**, **[!UICONTROL Medium]** oder **[!UICONTROL Hoch]** Wichtigkeit eingestellt werden. Der auf jeder Karte angezeigte Prozentsatz entspricht dem normalisierten Beitrag dieser Dimension, nachdem alle Ihre Auswahlen kombiniert wurden - die sieben Gewichtungen ergeben immer 100 %. Durch das Anheben einer Dimension werden die anderen automatisch neu normalisiert, sodass die Gesamtsumme bei 100 % bleibt.

Klicken Sie **[!UICONTROL Auf Gleich zurücksetzen]**, um für alle Dimensionen eine gleichmäßige Gewichtung wiederherzustellen.

![Journey-Traffic-Steuerung - Passen Sie die Dimensions-Scoring-Karten auf der Registerkarte „Konfiguration“ an](./assets/journey-traffic-control-configuration.png){width="800" zoomable="yes"}

### Scoring simulieren {#simulate-scoring}

Bevor Sie Gewichtungen an die Produktion übergeben, können Sie simulieren, wie sich die Traffic-Steuerung bei diesen Änderungen verhält. Bei der Simulation muss die Journey-Traffic-Steuerung nicht aktiviert sein. Es werden Profile ausgewertet, die sich bereits in Ihren Live-Journey befinden, und die Traffic-Steuerungslogik wird auf sie angewendet, sodass Sie beurteilen können, ob die Ergebnisse für die von Ihnen ausgewählten Gewichtungen richtig aussehen.

1. Wählen Sie aus, wie viele Profile simuliert werden sollen.

1. Klicken Sie auf **[!UICONTROL Bewertung simulieren]**.

Die Ergebniskopfzeile fasst den Durchlauf zusammen:

* **Ausgewertete Profile** - Wie viele Profile wurden ausgewertet, und über wie viele Journey hinweg.
* **Durchschnittliche Konflikte/**: Die durchschnittliche Anzahl konkurrierender Journey pro Profil.
* **Durchschnittlicher Übereinstimmungswert** - Die durchschnittliche Konfidenz der ausgewählten Journey.

![Journey-Traffic-Steuerung - Registerkarte „Konfiguration“ - Scoring-Ergebnisse simulieren](./assets/journey-traffic-control-configuration-simulate-scoring.png){width="700" zoomable="yes"}

Unterhalb der Zusammenfassung wird jedes ausgewertete Profil als Karte angezeigt, die die ausgewählte Journey, die wichtigsten Gründe, Absichtssignale und den Übereinstimmungsgrad anzeigt. Wählen Sie ein Profil aus, um eine Detailansicht zu öffnen mit:

* **Übereinstimmungswert** - Die Gesamtübereinstimmung mit einer farbcodierten Aufschlüsselung nach Dimension.
* **Entscheidung** - Die Journey, für die sich diese Person qualifiziert hat, welche ausgewählt wurde und warum.
* **Dimension-Werte nach Gewicht** - Die Werte pro Dimension, auf die sich die Entscheidung stützte und erweiterbar sind, um die zugrunde liegenden Signale anzuzeigen.

![Journey-Traffic-Steuerung - Scoring-Ergebnisse simulieren - Profildetails](./assets/journey-traffic-control-configuration-simulate-scoring-profile-details.png){width="450" zoomable="yes"}

Wenn Sie mit dem Ergebnis zufrieden sind, können Sie:

* Passen Sie die Bemaßungsgewichte an und klicken Sie auf **[!UICONTROL Erneut ausführen]**, um die Simulation erneut auszuführen.

* Klicken Sie **[!UICONTROL Auf Produktion anwenden]**, um die Gewichtungen zu übernehmen.

  Neue Entscheidungen zur Traffic-Steuerung verwenden die neuen Einstellungen sofort. Frühere Entscheidungen sind davon nicht betroffen. Die von Ihnen getesteten Gewichtungen werden auf der Registerkarte _[!UICONTROL Konfiguration]_ angezeigt und werden für alle Journey-Traffic-Steuerelemente verwendet, die in Ihrer Live-Umgebung ausgewertet werden.

Sie können die Seite auch verlassen, ohne die Gewichtungen anzuwenden.

<!--

This section does not appear in the staging environment

### Select journeys {#select-journeys}

The _[!UICONTROL Select journeys]_ section is where you choose which journeys participate in traffic control.

>[!IMPORTANT]
>
>Only draft journeys are available for selection. Traffic control cannot be enabled for a journey that is already live. When JTC is enabled for a journey and then that journey is published, it cannot be disabled.

-->

## Aktivieren der Traffic-Steuerung für Journey {#enable-traffic-control-journey}

Wenn bei zwei oder mehr Journey die Journey-Traffic-Steuerung aktiviert ist und veröffentlicht wird:

* Jede Person, die sich für eines oder mehrere dieser Journey qualifiziert, wird anhand ihres Profils und der Journey-Metadaten bewertet.
* Wenn eine Person sich für mehrere JTC-fähige Journey gleichzeitig qualifiziert (z. B. fünf), bestimmt das Modell, welche die beste Journey zu diesem Zeitpunkt ist, und registriert die Person nur für diese eine Journey. Sie werden von den anderen herausgehalten.
* Die Person durchläuft diese Journey, bis sie abgeschlossen ist.
* Nach Abschluss werden sie mit den verbleibenden Journey verglichen, für die sie noch qualifiziert sind, und zur nächstbesten hinzugefügt, wobei wiederholt wird, bis keine qualifizierten Journey mehr übrig sind.

### JTC für Entwurfs-Journey aktivieren {#enable-traffic-control-draft-journey}

Die Journey-Traffic-Steuerung kann direkt auf einer Journey aktiviert werden, wenn sie sich im Status _Entwurf_ befindet. <!-- This is the same setting surfaced from the admin/configuration flow — enabling it in either place keeps the two in sync. -->

1. Erweitern Sie in der linken Navigation **[!UICONTROL Marketing-Verwaltung]**.

1. Wählen Sie rechts in der **[!UICONTROL Marketing]**-Ressourcenliste **[!UICONTROL Personen-Journey]** aus.

1. Klicken Sie auf den Namen der Personen-Journey als Entwurf, um sie zu öffnen.

1. Klicken Sie auf **[!UICONTROL … Mehr]** oben rechts und wählen Sie **[!UICONTROL Traffic-Steuerungs-Einstellungen für Journey]**.

   ![Journey-Traffic-Steuerung - Für Personen-Journey als Entwurf aktivieren](./assets/journey-traffic-control-enable-journey.png){width="700" zoomable="yes"}

1. Aktivieren Sie im Dialogfeld die Option **[!UICONTROL Journey-Traffic-Steuerung aktivieren]**.

   Im Einstellungsdialogfeld wird das Verhalten erläutert: Wenn aktiviert, wird die Journey zu einem Kandidaten, und das Modell bewertet und empfiehlt die am besten geeignete Journey für eine Person, die sich für mehrere aktive Journey qualifiziert.

   ![Journey-Traffic-Steuerung - Umschalter aktivieren](./assets/journey-traffic-control-enable-dialog.png){width="380"}

1. Klicken Sie auf **[!UICONTROL Speichern]**.

>[!IMPORTANT]
>
>Der Umschalter kann jederzeit geändert werden, während die Journey im Status _Entwurf_ verbleibt. <!-- If it was already enabled from the admin section (or previously enabled by someone else), the toggle appears on. --> Nach der Veröffentlichung der Journey mit aktiviertem JTC bewertet die Traffic-Steuerung den Eintritt in diese Journey, und Sie können die Einstellung nicht mehr deaktivieren.

### Optimieren der Journey-Beschreibung {#optimize-journey-description}

Der Traffic Control Agent kann die Metadaten einer Journey - die Knoten in der Journey, den Namen der Zielgruppe und ähnliche Struktursignale - effektiv verwenden, um seine Entscheidung zu beeinflussen. Es profitiert jedoch stark von einer aussagekräftigen, beschreibenden Journey-Beschreibung, die den Zweck und die Ziele der Journey klar angibt.

Eine aussagekräftige Beschreibung gibt dem Modell den Kontext, den es benötigt, um eine fundiertere Entscheidung darüber zu treffen, ob eine Person zu dieser Journey gehört oder nicht. Dies ist am wichtigsten, wenn eine Journey sehr einfach ist. Ein Journey mit wenigen Knoten bietet beispielsweise einen begrenzten Kontext, sodass eine klare Beschreibung seines Ziels und seiner Zielgruppe dem Modell bei der richtigen Auswahl hilft.

>[!TIP]
>
>Behandeln Sie die Journey-Beschreibung als Eingabe für das Entscheidungsmodell und nicht nur die interne Dokumentation. Beschreiben Sie den Zweck der Journey (was sie erreichen möchte), ihre Ziele und die Zielgruppe, für die sie vorgesehen ist. Je genauer die Beschreibung ist, desto genauer kann die Traffic-Steuerung die Entscheidung treffen, wenn sich eine Person für mehrere sich überschneidende Journey qualifiziert - insbesondere für leichte Journey mit wenigen Knoten.

## Registerkarte „Reporting“ {#reporting-tab}

Nachdem die Traffic-Steuerung für zwei oder mehr Journey mit abgeschlossenen Ausführungen aktiviert wurde, zeigt die Registerkarte _[!UICONTROL Reporting]_ die Ergebnisse an. Es gibt zwei Ansichten: **[!UICONTROL By run]** und **[!UICONTROL By Journey]**.

### Nach Durchgang {#by-run}

Die Ansicht _[!UICONTROL Nach]_&quot; listet alle Traffic-Steuerungsdurchgänge auf. Für jeden Durchgang können Sie die Uhrzeit, den Trigger (geplant oder manuell), die ausgewerteten aktiven Journey, die ausgewerteten Personen, die Traffic-Steuerungsentscheidungen, die Verarbeitungszeit und den Status sehen. Wählen Sie einen Durchgang aus, um ein Bedienfeld mit diesen Schlüsselmetriken für den Durchgang und der Liste der in diesem Durchgang bewerteten Journey zu öffnen.

![Journey-Traffic-Steuerung - Registerkarte „Berichterstellung“ - Nach Ausführungsansicht](./assets/journey-traffic-control-reporting-tab-by-run.png){width="700" zoomable="yes"}

### Durch Journey {#by-journey}

Verwenden Sie die Ansicht _Nach Journey_, um zu überprüfen, wie sich die Traffic-Steuerung auf eine bestimmte Journey ausgewirkt hat. Die Tabelle zeigt pro Journey die Anzahl der ausgewerteten, für diese Journey registrierten, in andere Journey verschobenen und bereits aktiven Personen an.

![Journey-Traffic-Steuerung - Registerkarte „Berichterstellung“ - Nach Journey-Ansicht](./assets/journey-traffic-control-reporting-tab-by-journey.png){width="700" zoomable="yes"}

<!--
Selecting a journey opens a detail panel:

* **Summary** — Total people evaluated, broken down into _Enrolled in this journey_, _Moved to other journeys_, and _Already active_.
* **Competing journeys** — Every journey that had people competing with this one, and how many were enrolled in each.
* **People evaluated** — The individual people, each with an outcome (_Enrolled_, _Moved_, or _Already active_), competing journeys, and match score.

>[!TIP]
>
>The sum of enrolled people across all competing journeys always equals the _Moved to other journeys_ count in the summary. _Already active_ means the person was already in the journey when the evaluation occurred.

Selecting an individual person shows the same detail view as in simulation: the match score, the decision (competing journeys and which journey was selected and why), and the full dimension breakdown behind the selection.
-->
