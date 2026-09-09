---
title: Optimierung des E-Mail-Versandzeitpunkts
description: Konfigurieren der Sendezeitoptimierung in den Personen-Journey von Marketo Optimizer. Festlegen von Versandfenstern, Hinzufügen von Warteknoten und Anzeigen von STO-Berichten in Coworker.
TQID: 'https://experienceleague.adobe.com/7g2aCAhlDO17TNy-VZSsWZ2JKGFgE5MZT20zp7eC1WQ'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 3c1de303-7a7c-59a6-abca-8c534730e19cid: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 759
ht-degree: 0%

---

# Optimierung des E-Mail-Versandzeitpunkts

Verwenden Sie die Funktion „Optimierung des Versandzeitpunkts (STO)“, um den Versandzeitpunkt von E-Mails für [Personen-Journey](./person-journeys.md) zu personalisieren, indem Sie vorhersagen, wann jedes Profil am ehesten interagieren wird. Anstelle einer festen Versandzeit verwendet STO historische E-Mail-Interaktionssignale, um den Versand für jeden Empfänger zum optimalen Zeitpunkt zu planen und so die Interaktion insgesamt zu verbessern.

STO analysiert die historischen Interaktionen jedes Profils mithilfe eines großen Sprachmodells. Er sagt potenzielle Versandzeitpunkte voraus und stuft sie ein, und plant dann den Versand zum Zeitpunkt, der im Optimierungsfenster am höchsten rangiert.

Leistungseinblicke, wie z. B. Nutzung, Interaktionssteigerung und STO-Vergleiche mit Nicht-STO-Vergleichen, sind über Abfragen in natürlicher Sprache in Coworker verfügbar.

>[!BEGINSHADEBOX]

Es sind viele **_zukünftige Verbesserungen_** für STO geplant:

* Globale STOP-Konfiguration im Bereich _[!UICONTROL Admin]_
* STO-Aktivierung auf Journey-Ebene
* Konfigurierbare Test-/Kontrollaufteilungen

>[!ENDSHADEBOX]

## Konfiguration {#configuration}

Sie können die Sendezeitoptimierung konfigurieren, wenn Sie [ Journey eine _[!UICONTROL Aktion durchführen]_-Knoten ](./action-nodes.md) Person hinzufügen und die Aktion **[!UICONTROL E-Mail senden]** auswählen.

1. Wählen Sie den Aktionsknoten _E-Mail senden_ Journey aus.

1. Aktivieren Sie in den Knoteneigenschaften auf der rechten Seite die Option **[!UICONTROL Sendezeitoptimierung]** .

   ![Knoten „E-Mail-Journey senden“ - Optionen zur Optimierung des Versandzeitpunkts](./assets/email-node-send-time-optimization.png){width="450" zoomable="no"}

1. Um das Fenster und die Testverteilung festzulegen, legen Sie die STO-Optionen fest:

   * **[!UICONTROL Senden innerhalb der nächsten]** - Dieser Wert bestimmt das Optimierungsfenster (in Tagen), das den Zeitraum angibt, in dem E-Mails zugestellt werden können. Ein Webinar, das beispielsweise in fünf Tagen stattfindet, kann vier oder fünf Tage dauern. STO wählt für jedes Profil in diesem Fenster die beste prognostizierte Versandzeit aus.

   * **STO / Feste Verteilung** - STO erstellt automatisch eine _Test- und Kontrollaufteilung_ um die geeigneten Profile zwischen optimierten und festen Versandzeiten zu unterteilen. Die Aufspaltung ermöglicht einen direkten Leistungsvergleich. (Es sind zukünftige Verbesserungen geplant, um benutzerdefinierte Aufspaltungsprozentsätze zuzulassen.)

   >[!NOTE]
   >
   >Profile mit einem starken Interaktionsverlauf werden gleichmäßig in Kontroll- und Testgruppen aufgeteilt, um die STO-Wirkung zu messen. Um statistisch verlässliche Ergebnisse zu gewährleisten, ist die Aufteilung zwischen STO und Nicht-STO zwischen 30 % und 70 % beschränkt. Dadurch wird verhindert, dass kleinere Kohorten die Ergebnisse verfälschen, und es werden aussagekräftige Vergleiche sichergestellt.

1. Direkt nach dem Knoten _[!UICONTROL E-Mail senden]_ [fügen Sie einen _Warten_-Knoten hinzu](./wait-nodes.md).

   Auf eine STO-aktivierte E-Mail-Aktion muss sofort ein Warteknoten folgen. Durch Hinzufügen dieses Knotens wird sichergestellt, dass Profile im Journey bleiben, bis das vollständige Optimierungsfenster gelöscht ist und alle STO-Sendungen abgeschlossen sind. Wenn Sie diesen Knoten auslassen, kennzeichnet das System die Konfiguration als ungültig.

1. Nachdem Sie den Rest der Personen-Journey abgeschlossen haben, fahren Sie mit [Veröffentlichen](./person-journeys.md#publish) fort.

## Berichterstellung {#reporting}

STO-Leistungsdaten sind über den [Mitarbeiter](../agents/chat-interface.md) verfügbar, der die `send-time-report` Kenntnisse verwendet. Sie können einen Bericht auf Journey-Ebene anzeigen, der alle E-Mail-Knoten zusammenfasst, oder für eine bestimmte E-Mail-Aktion einen Drilldown zu einem Bericht auf Knotenebene durchführen.

Der Bericht zeigt die einzelnen E-Mail-Knoten auf der Journey an und gibt an, ob STO dafür aktiviert ist. Außerdem wird ein tabellarischer Vergleich zwischen STO-aktivierten und Nicht-STO-E-Mails angezeigt, sodass Sie die Interaktionssteigerung auswerten können.

### STO-Bericht generieren {#generate-sto-report}

Es gibt drei Möglichkeiten, einen STO-Bericht mit dem -Mitarbeiter zu generieren:

**Verwenden Sie den Schrägstrich**

1. Geben Sie im Bedienfeld „Mitarbeiter“ `/` ein, um die Liste der verfügbaren Fähigkeiten anzuzeigen.
1. Wählen Sie **[!UICONTROL Sendezeitbericht]** aus der Liste aus und klicken Sie auf den Nach-oben-Pfeil, um die Abfrage zu senden.

   ![Abfrage bezüglich der Kenntnisse des Kollegen-Sendezeitberichts](./assets/email-sto-reporting-coworker.png){width="700" zoomable="yes"}

   Wenn eine Journey im Editor geöffnet ist, verwendet Coworker sie automatisch als Kontext. Andernfalls fordert Sie Coworker auf, die Journey anzugeben.

   Der Kollege lädt den Bericht und zeigt eine Zusammenfassungskarte an.

1. Klicken Sie **[!UICONTROL Bericht öffnen]**, um den vollständigen Bericht mit Details auf Knotenebene anzuzeigen.

**Auf einen E-Mail-Knoten klicken**

1. Klicken Sie auf der Journey-Arbeitsfläche auf den Knoten **[!UICONTROL E-Mail senden]**.

1. Fragen Sie im Bedienfeld „Mitarbeiter“ nach dem STO-Bericht.

   Da der Knoten ausgewählt ist, verwendet Coworker ihn als Kontext und gibt einen Bericht zurück, der nur für diesen Knoten gilt.

   Der Bericht wird geladen und eine Zusammenfassungskarte wird angezeigt.

1. Klicken Sie **[!UICONTROL Bericht öffnen]**, um den vollständigen Bericht anzuzeigen.

**Abfrage in natürlicher Sprache**

1. Geben Sie im Bedienfeld „Mitarbeiter“ eine Anfrage ein, z. B _„Geben Sie mir den STO-Bericht für [Journey-Name]_.

   Mitarbeiter interpretiert die Anfrage, lädt die `send-time-report`, generiert den Bericht und zeigt eine Übersichtskarte an.

1. Klicken Sie **[!UICONTROL Bericht öffnen]**, um den vollständigen Bericht anzuzeigen.

### Anzeigen der E-Mail-Berichtsdaten {#sto-report-data}

Sie können das Bedienfeld „Mitarbeiter“ verkleinern, um die Größe des angezeigten Berichts zu erhöhen, oder scrollen, um die volle Breite zu sehen.

![Bericht zur Sendezeitoptimierung - E-Mail-Leistungszusammenfassung](./assets/email-sto-reporting-summary-report.png){width="700" zoomable="yes"}

Klicken Sie in _[!UICONTROL Spalte]_ Details **[!UICONTROL auf STO-Ergebnisse anzeigen]** um ein Popup-Fenster zu öffnen. Das Fenster bietet E-Mail _Datenvisualisierungen für_ Leistungsvergleich _(Sendezeitverteilung_ und _Datenintegrität_.

![Bericht zur Sendezeitoptimierung - E-Mail-Leistungsdaten](./assets/email-sto-reporting-data.png){width="500" zoomable="yes"}
