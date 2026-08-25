---
title: Aufspalten und Zusammenführen von Pfadknoten
description: Erfahren Sie, wie Sie mithilfe von Knotenpunkten für Aufspaltungs- und Zusammenführungspfade in Personen-Journeys Personen basierend auf definierten Bedingungen in verschiedene Pfade segmentieren und dann an einem gemeinsamen, nachgelagerten Punkt zusammenführen können.
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 0%

---

# Aufspalten und Zusammenführen von Pfadknoten

Verwenden Sie Split-Pfade und Zusammenführungsknoten in Personen-Journey, um Personen basierend auf von Ihnen definierten Bedingungen in verschiedene Pfade zu segmentieren, und bringen Sie diese Pfade dann wieder zusammen, damit die Journey fortgesetzt werden kann. Mit Pfaden für die Aufspaltung können Sie Aktionen und Ereignisse auf bestimmte Zielgruppensegmente anpassen, während Pfade für die Zusammenführung diese Segmente an einem gemeinsamen nachgelagerten Punkt zusammenführen.

## Pfade von Knoten teilen

Verwenden Sie geteilte Knoten, um Personen entsprechend den von Ihnen definierten Bedingungen zu segmentieren. Erstellen Sie Pfade für die Audience-Liste gemäß Bedingungen, definieren Sie jeden Pfad mit Aktions- und Ereignisknoten für das Segment, kombinieren Sie dann die Pfade und setzen Sie das Journey fort.

Ein Knoten für aufgeteilte Pfade definiert einen oder mehrere segmentierte Pfade, die auf Personenfiltern basieren.

<!-- A split based on a people filter is automatically closed with a merge paths node so that all people can move forward to the next step. Split by people paths can include only people actions. These paths cannot be split again and automatically join back. _not currently true_ -->

_**Wie funktioniert ein aufgeteilter Pfad nach Personenknoten**_

* Die Auswertung jedes Pfads erfolgt von oben nach unten. Wenn eine Person für den ersten und zweiten Pfad eine Übereinstimmung findet, fährt sie nur entlang des ersten Pfads fort.
* Der Knoten unterstützt die Definition eines Pfads _Andere Personen_, in dem Sie Aktionen oder Ereignisse für Personen hinzufügen können, die nicht mit einem der definierten Segmente/Pfade übereinstimmen.

### Übereinstimmende Filter

Verwenden Sie für jeden Pfad, den Sie für den Knoten definieren, die folgenden Filtertypen, um Personen entsprechend einer oder mehreren Bedingungen abzugleichen:

* Aktivitätsverlauf - Sie können einen Pfad entsprechend der Aktivität der Person definieren, die mit Folgendem zusammenhängt:

  * E-Mail-Nachrichten
  * Änderung des Datenwerts

* Personenattribute - Definieren Sie eine Bedingung anhand der Attribute einer Person, z. B. Land, Berufsbezeichnung, abgeleitete Rolle oder Listenmitgliedschaft.

### Hinzufügen eines Knotens mit aufgeteilten Pfaden

1. Navigieren Sie zur Journey-Arbeitsfläche.

1. Klicken Sie auf das Pluszeichen ( **+** ) auf einem Pfad und wählen Sie **[!UICONTROL Pfade aufteilen]**.

   ![Klicken Sie auf das Symbol zum Hinzufügen auf dem Journey-Pfad](./assets/person-journey-canvas-add-node.png){width="200"}

1. Um eine Bedingung zu definieren, die für _[!UICONTROL Pfad 1]_ gilt, klicken Sie auf **[!UICONTROL Bedingung anwenden]**.

1. Fügen Sie im Bedingungseditor einen oder mehrere Filter hinzu, um den Aufspaltungspfad zu definieren.

   * Ziehen Sie einen beliebigen Personenfilter aus dem linken Navigationsbereich und füllen Sie die Definition der Übereinstimmung aus.

   * Passen Sie Ihre Bedingungen durch Anwendung der **[!UICONTROL Filterlogik]** oben an. Sie wählen, ob alle Bedingungen oder nur eine der Bedingungen erfüllt sein sollen.

     <!-- ![Split path node - conditions person filter logic](./assets/node-split-conditions-people.png){width="700" zoomable="yes"} -->

   * Klicken Sie auf **[!UICONTROL Fertig]**.

1. Um weitere Pfade hinzuzufügen, klicken Sie auf **[!UICONTROL Pfad hinzufügen]** und wiederholen Sie die vorherigen Schritte, um die für den Pfad geltenden Bedingungen hinzuzufügen.

   Sie können auch jeden Pfad anhand dieser Bedingungen beschriften oder die Standardbeschriftungen verwenden.

1. Ordnen Sie die Pfade bei Bedarf entsprechend der Priorität neu an, die Sie für die Aufspaltung festlegen möchten.

   Die Pfadfilterung wird in der Reihenfolge von oben nach unten bewertet. Jede Person fährt auf dem ersten Pfad fort, der übereinstimmt.

   Klicken Sie auf die Pfeile nach oben und unten oben rechts auf jeder Pfadkarte, um sie in der Liste der Pfade nach oben oder unten zu verschieben.

   <!-- ![Split path node - reorder paths](./assets/node-split-reorder-paths-people.png){width="500" zoomable="yes"} -->

1. Aktivieren Sie die Option **[!UICONTROL Andere Personen]**, um einen Standardpfad für Personen hinzuzufügen, die den definierten Pfaden nicht entsprechen.

   Wenn diese Option nicht aktiviert ist, bewegen sich Personen, die mit keinem definierten Segment/Pfad übereinstimmen, an der Teilung vorbei und fahren mit dem nächsten Schritt auf der Journey fort.

Wenn Sie für jeden Pfad Bedingungen definiert haben, können Sie Aktions- oder Ereignisknoten hinzufügen, die Sie auf Personen in einem Pfad anwenden möchten.

## Zusammenführen von Pfadknoten

1. Navigieren Sie zur Journey-Arbeitsfläche und suchen Sie den aufgeteilten Pfadknoten mit zwei oder mehr Pfaden.

   Jeder Pfad sollte eine Kombination aus Aktionen und Ereignissen auf jedem Pfad enthalten.

1. Klicken Sie auf das Pluszeichen ( **+** ) am Ende eines dieser Pfade und wählen Sie **[!UICONTROL Zusammenführungspfade]** aus den angezeigten Optionen aus.

1. Wählen Sie in den Knoteneigenschaften rechts die Pfade aus, die Sie zusammenführen möchten.

   <!-- ![Journey node - merge paths](./assets/node-merge-select-paths.png){width="600" zoomable="yes"} -->

   An dieser Stelle werden die Pfade zusammengeführt, sodass Personen aus den ausgewählten Pfaden zu einem einzigen Pfad kombiniert werden, der durch den Journey weiter ausgeführt werden kann.

1. Bei Bedarf können Sie die Zusammenführung von Pfaden aufheben, indem Sie zurück zu den Knoteneigenschaften der Zusammenführungspfade navigieren und das Kontrollkästchen für alle Pfade deaktivieren, die Sie entfernen möchten.