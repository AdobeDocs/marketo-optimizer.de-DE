---
title: KI-Entscheidungsstatus
description: Erfahren Sie, wie KI-Entscheidungs-Konsistenzprüfungen die Lead-Abdeckung, die Personenklassifizierung und die Signalreichhaltigkeit in Marketo Optimizer überprüfen und auf fehlende Elemente hinweisen.
TQID: 'https://experienceleague.adobe.com/rZy9gOQusGt2mfZ3t0iBS2blVp1PXH-R-TIW5cGWu2Y'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2:
  - id: 5229c72e-d79b-574f-a03e-5c4bf48172c3
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 801
ht-degree: 0%

---


# KI-Entscheidungsstatus

Der KI-Entscheidungsstatus prüft die Daten, die die Personalisierung in [!DNL Adobe Marketo Optimizer] ermöglichen. Es berichtet über die Lead-Abdeckung, Personenklassifizierung und die Reichhaltigkeit von Geschichten in demografischen, firmografischen, technografischen und psychografischen Kategorien. Anschließend werden fehlende Daten gekennzeichnet, um zu ermitteln, wo begonnen werden soll.

Verwenden Sie den KI-Entscheidungsstatus, um zu sehen, welche Daten aus [!DNL Marketo Engage] eingehen und wo Lücken bestehen. Das Schließen dieser Lücken verbessert die Bewertung und Weiterleitung [&#x200B; einzelnen Personen durch &#x200B;](./ai-decisioning.md) KI-Entscheidungsfindung.

## KI-Entscheidungsstatus öffnen {#open}

Öffnen Sie den Bericht entweder über die Startseite oder den Kollegen-Chat.

* Wählen Sie auf _Startseite_ die Karte **[!UICONTROL Zustand der KI-Entscheidung]** in der Zeile Schnellzugriff aus. Die Karte führt die Zeile an und zeigt das Volumen der Story und den Fortschritt der Persona-Klassifizierung an, z. B. 929 Geschichten, 32 % Persona klassifiziert.
* Fragen Sie im Chat-Feld „Mitarbeiter“ direkt nach Ihren Personalisierungsdaten oder geben Sie `/` ein und wählen Sie **[!UICONTROL KI-Entscheidungsstatus]**.

![Schnellzugriffszeile auf der Startseite, in der die KI-Entscheidungsintegritätskarte zuerst angezeigt wird, gefolgt von Marketing, Assets und Berichten.](./assets/ai-decisioning-health-quick-access.png){width="600"}

Bei beiden Pfaden wird der Bericht im Arbeitsbereich des Mitarbeiters geöffnet.

## Begrüßungs- und Folgenachrichten im Chat {#chat-welcome}

Beim Öffnen des Zustands der KI-Entscheidung im Chat werden eine Begrüßungsmeldung, _[!UICONTROL *Willkommen beim Zustand der KI-Entscheidung]_, eine Zusammenfassung der Berichtsprüfungen und eine Karte zum Öffnen des vollständigen Berichts angezeigt.

Unter der Karte unter _[!UICONTROL Was möchten Sie als Nächstes tun?]_ schlägt die KI-Entscheidungsfindung „Konsistenz“ Folgeaufforderungen vor, die auf den spezifischen Lücken Ihrer eigenen Daten basieren. Wenn beispielsweise 67,7 % Ihrer Leads nicht über eine Personenklassifizierung verfügen, wird eine Eingabeaufforderung mit dem Hinweis _Warum werden 67,7 % der Leads nach Persona nicht klassifiziert?_ Wählen Sie eine vorgeschlagene Eingabeaufforderung aus oder stellen Sie Ihre eigene Frage, um eine direkte Antwort zu erhalten, ohne den Chat zu verlassen.

![Bedienfeld „Coworker chat“ mit der Begrüßungsnachricht für den KI-Entscheidungszustand, einer Karte, die den Bericht öffnet, und vier vorgeschlagenen Nachverfolgungsaufforderungen.](./assets/ai-decisioning-health-highlights.png){width="800" zoomable="yes"}

## Berichtsübersicht {#report-overview}

Der Arbeitsbereich-Bericht wird mit einem **[!UICONTROL Highlights]**-Callout geöffnet, in dem die stärksten und schwächsten Bereiche Ihrer Daten im Klartext aufgelistet werden, z. B. _Demografische Daten erreichen 100 % der Leads mit starker_ oder _67,7 % der Leads bleiben in einer Rolle nicht klassifiziert_. Ein Häkchen kennzeichnet ein einwandfreies Ergebnis, und ein Kreis mit einem Schrägstrich kennzeichnet eine Lücke.

Neben den Highlights zeigt ein Radardiagramm die gesamte **[!UICONTROL Abdeckung)]** sechs Dimensionen an: demographisch, firmographisch, technographisch, psychographisch, persona und Intent. Ein größerer schattierter Bereich bedeutet eine breitere Abdeckung.

## Persona-Klassifizierung {#persona-classification}

Der Abschnitt **[!UICONTROL Persona-Klassifizierung]** zeigt, wie viele Ihrer Geschichten in eine Persona klassifiziert werden, z. B.: _300 von 929 Geschichten klassifiziert ・ 32,3 % klassifiziert ・ 67,7 % nicht klassifiziert_. Ein gestapelter Balken durchbricht die klassifizierten Geschichten nach Rollen, wobei eine Legende die Anzahl der Geschichten und den Prozentsatz für jede Geschichte anzeigt.

Wählen Sie ein Personensegment aus, um eine Detailkarte mit Beispielaufgabentiteln für diese Rolle zu öffnen. Beispielsweise könnte das Segment **[!UICONTROL Other]** Folgendes zeigen: _272 Geschichten / 29,3 %_, mit Beispielen wie Branchenspezialist, unabhängiger Berater, freiberuflicher Berater und Fachexperte.

## Abdeckung {#coverage}

Im Abschnitt **[!UICONTROL Abdeckung]** werden fünf Datenkategorien aufgelistet: demographisch, firmographisch, technographisch, psychographisch sowie Intent und Aktivität. Jede Kategorie zeigt den Prozentsatz der Storys mit mindestens einem verfügbaren Attribut in dieser Kategorie an.

Wählen Sie eine Kategorie aus, um sie zu erweitern, und wählen Sie dann eine von zwei Registerkarten aus:

* **[!UICONTROL Attribute]** - Attribute gruppiert nach Typ, z. B. „Persönliche Details“ oder „Standort unter „Demografisch“. Jedes Attribut zeigt, wie viele Storys einen Wert dafür haben, z. B.: `firstName (906 stories)`.
* **[!UICONTROL Flags]** - Lücken, die für diese Kategorie spezifisch sind, oder _Keine offenen Flags in dieser Kategorie_ wenn die Abdeckung intakt ist.

Verwenden Sie das Suchfeld über der Kategorieliste, um direkt zu einer Kategorie oder einem Attribut anhand des Namens zu springen.

![Der Abschnitt zur Abdeckung mit der erweiterten Kategorie „Demografisch“ zeigt Attributgruppen wie persönliche Details, Interaktionsbewertung und Standort.](./assets/ai-decisioning-health-coverage.png){width="800" zoomable="yes"}

## Markierungen {#flags}

Im Abschnitt **[!UICONTROL Flags]** am Ende des Berichts werden alle festgestellten Lücken in allen Kategorien nach Schweregrad sortiert aufgelistet:

* **[!UICONTROL Kritisch]** - Lücken, die eine Funktion vollständig blockieren, z. B. _Die technische Abdeckung beträgt 0 % für alle Leads_.
* **[!UICONTROL Watch]** - Lücken, die die Effektivität verringern, aber eine Funktion nicht blockieren, z. B. _Die psychografische Abdeckung erreicht nur 7,2 % der Leads_.

Filtern Sie die Liste nach Schweregrad, wählen Sie dann eine Markierung aus, um sie zu erweitern, und lesen Sie eine 1-Sätze-Erklärung ihrer geschäftlichen Auswirkungen, z. B.: _Nicht klassifizierte Leads können keine personenspezifischen Journey-Einträge vornehmen oder rollenspezifische Nachrichten erhalten, was die Kampagnenrelevanz und die Konversionsraten verringert._

![Der Abschnitt Flags wurde nach Schweregrad der Überwachung gefiltert und zeigt drei Flags mit jeweils einer erweiterten Markierung, um die Erklärung der Geschäftsauswirkungen anzuzeigen.](./assets/ai-decisioning-health-flags.png){width="800" zoomable="yes"}

## Kürzlich aufgerufen {#recently-accessed}

Wenn Sie den KI-Entscheidungszustand öffnen und dann die Seite verlassen, wird sie erneut unter **[!UICONTROL Kürzlich aufgerufen]** im leeren Arbeitsbereich angezeigt, sodass Sie zurück in den Bericht springen können, ohne zur Startseite zurückzukehren.

![Kürzlich aufgerufene Liste, in der der Zustand der KI-Entscheidungsfindung vor dem Scoring-Studio als aktuelles Element angezeigt wird.](./assets/ai-decisioning-health-recently-accessed.png){width="500"}

>[!BEGINSHADEBOX]

Zu den geplanten Verbesserungen für den Status von KI-Entscheidungen gehören:

* Ein dedizierter Eintrag im Coworker skills-Katalog.
* Geführte „Fragen nach“-Aktionen, die Sie durch das Korrigieren einer Markierung führen.
* Eine spezielle Registerkarte Nächste Schritte .

>[!ENDSHADEBOX]
