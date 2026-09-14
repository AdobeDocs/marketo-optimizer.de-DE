---
title: Nächster bester Pfadknoten
description: Verwenden Sie den nächstbesten Pfadknoten in Marketo Optimizer für KI-gesteuertes Journey-Routing mit Eingabeaufforderungen in natürlicher Sprache, Pfadsimulation, Konfidenzwerten und Live-Pfadergebnissen für die Aufspaltung.
TQID: 'https://experienceleague.adobe.com/F-pxiABk7vHAktfmBUjZ8BYnxYIwQp--WutG6mvxiY0'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 5229c72e-d79b-574f-a03e-5c4bf48172c3
    internal-label: AI Decisioning
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: '1514'
ht-degree: 0%
---
# Nächster bester Pfadknoten

In Marketo Optimizer bringt der Knoten *Nächster bester Pfad* die KI-gesteuerte Split Path-Entscheidungsfindung direkt in die Journey-Arbeitsfläche. Anstatt Filterbedingungen auf einem [Split-Pfade](./split-merge-paths-nodes.md)-Knoten zu konfigurieren, beschreiben Sie Ihre Absicht in natürlicher Sprache und lassen Sie das System den relevantesten Pfad für jede Person bestimmen.

Beim B2B-Kauf mag ein Profil wie eine Art Käufer erscheinen, aber ihr Verhalten, ihre firmografischen Daten und ihr Interaktionskontext offenbaren eine differenziertere Geschichte. Der nächstbeste Pfadknoten bewertet diesen Kontext, um eine intelligente Routing-Entscheidung zu treffen, während Sie alle KI-Empfehlungen vor der Aktivierung des Journey überprüfen, ändern oder überschreiben können.

## Pfadentscheidung {#path-decisioning}

Von der Absicht zur Aktivierung sind drei Schritte erforderlich.

* **Schritt 1: Pfade definieren** - Fügen Sie einen Knoten des Typs Nächster bester Pfad zu Ihrem Journey hinzu, benennen Sie jeden Pfad und schreiben Sie eine Eingabeaufforderung in natürlicher Sprache, die beschreibt, wer den Pfad abschreiten soll. Sie können Pfade jederzeit hinzufügen oder entfernen.

* **Schritt 2: Simulieren** — Wählen Sie eine Beispielzielgruppe aus und führen Sie eine Simulation aus. Sie sehen Profilanzahl pro Pfad, Konfidenzwerte und die KI-Argumentation, damit Sie die Logik vor der Aktivierung überprüfen können.

  >[!NOTE]
  >
  >Die Simulation wird nur für Beispieldaten ausgeführt und beeinflusst nie die Live-Journey-Ausführung.

* **Schritt 3: Aktivieren** - Veröffentlichen Sie die Journey für Ihre echte Audience. Die KI bewertet jede Person zur Laufzeit, weist den Pfad mit der besten Anpassung in Echtzeit zu und ein standardmäßiges Fallback stellt sicher, dass niemand in eine Sackgasse gerät.

### KI-Entscheidungseingaben {#ai-decisioning-inputs}

Wenn eine Person den Knoten erreicht, ruft das System Profilkontext ab, wendet Einschränkungen an und wählt mithilfe eines LLM den am besten geeigneten Pfad aus. Die KI bewertet jede Person anhand einer Kombination der folgenden Eingaben:

* **Interaktionsverlauf** - E-Mail-Öffnungen, Link-Klicks, Web-Seitenbesuche und andere Verhaltenssignale von aktuellen und vorherigen Journey
* **Echtzeit-Signale** - Ereignisse mit hohen Absichten wie Formularausfüllungen und Preise für Seitenbesuche
* **Profilattribute** - Demografie, Stellenbezeichnung, Rolle und firmografische Daten
* **Kontoattribute** - Mit dem Konto der Person verknüpfte firmografische und technografische Daten

### KI-Kontextbildung {#ai-context-building}

Unter der Grundlage der Routing-Entscheidung erstellt die KI für jedes Profil eine abgeleitete Ebene. Sie kombiniert demografische und firmografische Daten, Kontodetails und Verhaltenssignale (wie persönliche Details, Problemabsicht und Produktabsicht) zu einer kontextuellen Zusammenfassung für diese Person. Unter Verwendung dieses angereicherten Kontexts kann die KI jede Person zum optimalen Pfad führen und sowohl einen Konfidenzwert als auch die Logik hinter jeder Entscheidung in natürlicher Sprache bereitstellen.

Jede Entscheidung wird mit einem Konfidenzwert und einer Argumentation in natürlicher Sprache für Transparenz und Beobachtbarkeit protokolliert.

Wenn kein Pfad eine starke Übereinstimmung aufweist oder die Eingabeaufforderung auf Daten verweist, die für ein Profil nicht verfügbar sind, wird die Person zum standardmäßigen Fallback-Pfad weitergeleitet.

## Hinzufügen eines Knotens mit dem nächsten besten Pfad {#add-node}

1. Öffnen Sie die Personen-Journey und navigieren Sie zur Journey-Arbeitsfläche.

1. Klicken Sie auf das Pluszeichen ( **+** ) auf einem Pfad und wählen Sie **Nächster bester Pfad**.

   Der Knoten wird der Arbeitsfläche hinzugefügt und das Bedienfeld für die Konfiguration einer KI-Teilung wird auf der rechten Seite geöffnet. Sie beginnt mit einem Pfad und dem Standardpfad *Andere Personen* zum Routing von Personen, die sich für keinen der definierten Pfade qualifizieren.

## Konfigurieren von Pfaden {#configure-paths}

Definieren Sie für jeden Pfad einen Namen und eine Eingabeaufforderung in natürlicher Sprache, die beschreibt, wer dort weitergeleitet werden soll. Die Benutzeroberfläche für Filterbedingungen wird durch die Eingabeaufforderung vollständig ersetzt. Es gibt keine Attributbedingungen, die konfiguriert werden müssen.

1. Klicken Sie **Pfad hinzufügen** für jeden zusätzlichen Pfad, den Sie einbeziehen möchten.

   Um einen Pfad zu entfernen, klicken Sie auf das *Löschen*-Symbol auf der Pfadkarte.

1. Für jede Pfadkarte im rechten Bedienfeld:

   * Geben Sie einen **Titel** ein, der die Zielgruppe oder Absicht für dieses Segment widerspiegelt.

   * Geben Sie eine **Eingabeaufforderung** in natürlicher Sprache ein, die beschreibt, wer zu diesem Pfad gehört. Konzentration auf Absicht und Ergebnis, nicht auf bestimmte Attributwerte.

     **Beispiel fordert zu einer Aufteilung auf drei Pfade auf:**

     * *Pfad 1 - Personalverantwortliche:* Identifizieren Sie Personen in Personalführungsrollen, die am ehesten mit dem Talent-Management und Mitarbeitererlebnisinhalten interagieren.
     * *Pfad 2 - Technische Gutachter:* Identifizieren Sie technische Stakeholder, die mit größter Wahrscheinlichkeit mit Produktarchitektur, Integrationen und Implementierungs-Content interagieren.
     * *Pfad 3 - Entscheidungsträger in Unternehmen:* Ermitteln Sie die Stakeholder, die am ehesten mit ROI, Geschäftsergebnissen und Fallstudieninhalten zu tun haben.

1. Ordnen Sie die Pfade bei Bedarf neu an, um die Prioritätsreihenfolge für den Abgleich festzulegen.

   Die Pfadfilterung wird in der Reihenfolge von oben nach unten bewertet. Jede Person fährt auf dem ersten Pfad fort, der übereinstimmt. Klicken Sie auf die Pfeile nach oben und unten oben rechts auf jeder Pfadkarte, um sie in der Liste nach oben oder unten zu verschieben.

1. Überprüfen Sie den Standardpfad (der letzte in der Pfadliste) und ändern Sie bei Bedarf die Bezeichnung.

   Der Standardpfad wird verwendet, wenn die KI keine Person einem definierten Pfad zuweisen kann oder wenn die relevanten Daten nicht verfügbar sind. Wenn eine Eingabeaufforderung auf Daten verweist, die für ein bestimmtes Profil nicht im Datensatz vorhanden sind, leitet das System dieses Profil an den Standardpfad weiter und markiert die Datenlücke.

>[!BEGINSHADEBOX]

**Human-in-the-loop-Steuerung**

KI-Empfehlungen sind unverbindlich. Vor der Aktivierung der Journey haben Sie folgende Möglichkeiten:

* Bearbeiten Sie eine Pfadaufforderung, um die Routing-Logik zu verfeinern.
* Pfade hinzufügen, entfernen oder neu anordnen.
* Überschreiben von KI-Vorschlägen bei Bedarf mit benutzerdefinierten Bedingungen.

KI-gesteuerte Pfadzuweisungen werden erst wirksam, wenn Sie die Journey veröffentlichen.

>[!ENDSHADEBOX]

## Beispiele nach Anwendungsfall auffordern {#prompt-examples}

Die folgenden Beispiele zeigen, wie effektive Pfadaufforderungen in gängigen B2B-Marketing-Anwendungsfällen geschrieben werden. Verwenden Sie sie als Ausgangspunkte und passen Sie die Sprache an Ihren Journey-Kontext und Ihre Zielgruppendaten an.

* „Identifizieren Sie Personen, die in den letzten 30 Tagen Interaktionen auf HR-Sites (shrm.org, hbr.org/topic/human-resource-management) hatten und sich für Journey Optimizer interessierten, die wahrscheinlich an einem Webinar über KI im HR-Betrieb teilnehmen werden. Sie hätten auch ein gewisses Interesse an KI-Produkten zeigen müssen.“

* Identifizieren Sie Personen, die in den letzten 30 Tagen Interaktionen auf Finanz-Sites (wsj.com/finance,investopedia.com) hatten und an Marketo interessiert waren, die wahrscheinlich an einem Webinar über KI in der Finanzplanung teilnehmen werden. Sie hätten auch ein gewisses Interesse an KI-Produkten zeigen müssen.“

* „Identifizieren Sie Personen, die in den letzten 30 Tagen an GenStudio interessiert waren und die wahrscheinlich an einem Webinar über KI im Risikomanagement teilnehmen werden. Diese Personen haben Kontakte zu Risiko-/Forschungssites (mckinsey.com/capabilities/risk-and-resilience, forrester.com/research). Sie hätten auch ein gewisses Interesse an KI-Produkten zeigen müssen.“

## Simulieren der Entscheidungsfindung vor der Veröffentlichung {#simulate}

Verwenden Sie eine Simulation, um zu testen, wie die KI Ihre Eingabeaufforderungen vor der Live-Schaltung der Journey gegenüber einer echten Zielgruppe auswertet. Die Simulation ist nur verfügbar, wenn sich die Journey im Status *Entwurf* befindet, und hat keine Auswirkungen auf veröffentlichte Journey.

### Simulation ausführen {#run-simulation}

1. Wählen Sie den nächstbesten Pfadknoten aus und klicken Sie oben *rechten Bedienfeld auf* Simulieren“.

1. Wählen Sie im Dialogfeld die Zielgruppe aus, die für die Simulation verwendet werden soll:

   * **[!UICONTROL Ursprüngliche Personenlisten]** - Verwenden Sie die Zielgruppe aus dem Zielgruppenknoten. Geben Sie eine Stichprobengröße an, wenn die vollständige Zielgruppe den Simulationsschwellenwert überschreitet.
   * **[!UICONTROL Dynamische und statische Listen]** - Verwenden Sie eine statische oder dynamische Marketo Engage-Liste.
   * **[!UICONTROL Testdatensätze]** - Verwenden von von KI vorgeschlagenen Testprofilen.

   >[!NOTE]
   >
   >* Wenn die ausgewählte Zielgruppe den Schwellenwert für die Simulation überschreitet, führt das System die Simulation an einem 100-Profil-Beispiel aus. Ein Indikator in der Benutzeroberfläche zeigt an, dass die Ergebnisse Beispielbasiert sind.
   >* Wenn die ausgewählte Zielgruppe noch nicht materialisiert wurde, wird die Simulation blockiert. Eine Inline-Warnung weist Sie an, die Zielgruppe zuerst zu materialisieren.

1. Klicken Sie **[!UICONTROL Simulieren]**.

### Überprüfen der Simulationsergebnisse {#review-results}

Nach der Ausführung der Simulation zeigt das rechte Bedienfeld die Verteilung der Profile auf die einzelnen Pfade und die KI-Überlegungen hinter diesen Zuweisungen an:

| Ergebnis | Beschreibung |
|---|---|
| **Profile** | Die Anzahl der an den Pfad weitergeleiteten Profile. |
| **Aufspaltung** | Der Prozentsatz der an den Pfad weitergeleiteten Profile. |
| **Konfidenz** | Die KI-Vertrauensstufe für die Pfadzuweisung. Konfidenz spiegelt die Aktualität der Daten, die Signalstärke und -konsistenz sowie den historischen Erfolg ähnlicher Routing-Muster wider. |
| **Eingabeaufforderung** | Die Aufforderung, die für den Pfad ausgewertet wurde. |
| **KI-Argumentation** | Eine Erklärung in natürlicher Sprache, warum Profile diesem Pfad gemeinsam zugewiesen wurden. |

>[!NOTE]
>
>Wenn Daten verfügbar sind oder der Umfang eine Entscheidung einschränkt, enthalten die Ergebnisse Informationen über die Einschränkung. Wenn beispielsweise ein erforderliches Attribut im Datensatz nicht vorhanden ist, enthalten die Ergebnisse einen expliziten Indikator, der erklärt, wie sich die fehlenden Daten auf die Ergebnisse ausgewirkt haben.

Verwenden Sie die Ergebnisse, um Eingabeaufforderungen zu verfeinern und zu bestätigen, dass das Routing Ihr beabsichtigtes Ergebnis widerspiegelt. Sie können Pfadaufforderungen ändern und die Simulation so oft wie nötig vor der Veröffentlichung erneut ausführen.

## Veröffentlichen und Überwachen der Journey {#publish-monitor}

Nach Validierung der Simulationsergebnisse:

1. Verbinden Sie die Zielgruppe mit dem Journey-Einstiegsknoten.

2. [Veröffentlichen der Journey](./person-journeys.md#publish).

Nach der Live-Schaltung des Journey wird der nächstbeste Pfadknoten zur Ausführungszeit ausgeführt. Wenn jede Person den Knoten erreicht, bewertet die KI sie in Echtzeit anhand der neuesten Signale und leitet sie zum relevantesten Pfad.

Bei einer veröffentlichten Journey öffnen Sie die Journey-Arbeitsfläche und wählen Sie den nächstbesten Pfadknoten aus, um den Abschnitt **_[!UICONTROL Live-Ergebnisse]_** im rechten Bedienfeld anzuzeigen. Live-Ergebnisse zeigen:

* Die prozentuale Verteilung der Profile über jeden Pfad
* Der Konfidenzwert für jede Pfadzuweisung
* Argumentation auf Pfad- und Profilebene mit erweiterbaren Details für einzelne Profile

Live-Ergebnisse sind auch in der Journey-Konsole und über die Journey-Beobachtungsfunktion im KI-Hub verfügbar.