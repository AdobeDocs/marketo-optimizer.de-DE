---
title: Absichtskonfiguration
description: Erfahren Sie, wie Sie Aktivitätsgewichte konfigurieren, die das Modell der beabsichtigten Bewertung von Personen steuern, von KI-vorgeschlagenen Standardwerten bis hin zur Aktivierung eines benutzerdefinierten Gewichtungsmodells.
source-git-commit: 8b3ea5f52fc50ea6c995ace44dece90247deff8b
workflow-type: tm+mt
source-wordcount: '1322'
ht-degree: 2%

---


# Absichtskonfiguration

Ein einziger standardisierter Satz von Aktivitätsgewichten funktioniert nicht kundenübergreifend. Welche Signale für eine tatsächliche Kaufabsicht gelten, ist von Unternehmen zu Unternehmen unterschiedlich. Konfigurieren und aktivieren Sie ein Absichtsmodell, um festzulegen, was für Sie wichtig ist, z. B. ob ein ausgefülltes Formular mehr als ein E-Mail-Klick signalisiert, anstatt einen globalen Standard zu übernehmen.

Die **[!UICONTROL Absichtskonfiguration]**-Tools steuern, wie viel jede Lead-Intent-Aktivität zum Absichtswert einer Person zählt. Dies ist die einzige konfigurierbare Eingabe bei der Absichtsbewertung. Andere Faktoren wie Inhaltsrelevanz, Verfall und Schwellenwerte werden vom System verwaltet. Sie ist über die [Intent-Konfigurationsfertigkeit](../agents/intent.md#configure-model) verfügbar.

Öffnen Sie das Bedienfeld mit einer von zwei Methoden aus der [&#x200B; (Chat-Oberfläche](../agents/chat-interface.md):

* Geben Sie den `/intent-configuration` Befehl ein.
* Klicken Sie auf **[!UICONTROL +]**, wählen Sie **[!UICONTROL Agentenkompetenz verwenden]**, wählen Sie die Registerkarte **[!UICONTROL Absicht]** aus und klicken Sie dann auf **[!UICONTROL Intent-Konfiguration]**.

![Das Bedienfeld für die Absichtskonfiguration wurde über die Chat-Oberfläche geöffnet](./assets/intent-configuration-panel.png){width="700" zoomable="yes"}

## Modell-Listenansicht

Die Landung im Bedienfeld zeigt **[!UICONTROL Gewichtung der Absichtsbewertung]** mit der Gesamtmodellanzahl unter dem Titel, einem Suchfeld zum Filtern nach Namen und einer sortierbaren Tabelle:

| Spalte | Hinweise |
| --- | --- |
| [!UICONTROL Name] | Sortierbar, Standardsortierung |
| [!UICONTROL Status] | _[!UICONTROL Aktiv]_ (grüner Punkt), _[!UICONTROL Entwurf]_ (orangefarbener Punkt), _[!UICONTROL Archiviert]_ (grauer Punkt) |
| [!UICONTROL Erstellungsdatum] | Abgekürzt, vollständiges Datum beim Bewegen des Mauszeigers |
| [!UICONTROL Zuletzt aktualisiert] | Abgekürzt, vollständiges Datum beim Bewegen des Mauszeigers |
| [!UICONTROL Zuletzt aktualisiert von] | Abgeschnittener Benutzername, vollständiger Name beim Bewegen des Mauszeigers |

Es kann immer nur ein Modell _[!UICONTROL aktiv]_ sein und dies ist die Modellbewertung. Jedes andere Modell befindet sich im Status _[!UICONTROL Entwurf]_ (wird bearbeitet, noch nicht live) oder _[!UICONTROL Archiviert]_ (ein früheres _[!UICONTROL Aktives]_ Modell, das automatisch herabgestuft wird, wenn ein neues Modell aktiviert wird).

Klicken Sie auf eine Zeile, um die Modelldetailansicht zu öffnen.

## Modelldetailansicht

Die Detailansicht zeigt den Modellnamen, das Status-Badge, den zuletzt gespeicherten Zeitstempel und einen Breadcrumb mit der **[!UICONTROL Intent-Score-]** und dem Modellnamen an, auf den Sie klicken können, um zur Liste zurückzukehren.

In der Detailansicht werden die Aktivitäten mit Käuferabsicht sowie die Wichtigkeitsstufe aufgelistet, die jeder von ihnen zum Intent-Score der Person beiträgt. Der Aktivitätskatalog ist fest und nur die Ebenen können sich ändern. Diese Ebenen sind unabhängig: sie müssen sich in keiner Summe summieren. Es kann immer nur eine Version des Gewichtungsmodells aktiv sein. Um Änderungen vorzunehmen, duplizieren Sie die aktuelle Version und bearbeiten Sie die Kopie.

![Die Detailansicht für ein Modell mit aktiver Absicht](./assets/intent-configuration-model-detail.png){width="550" zoomable="yes"}

Ein Suchfeld filtert Aktivitätszeilen nach Namen. Die Tabelle selbst:

| [!UICONTROL Intent-Aktivität] | [!UICONTROL AI schlug vor] | [!UICONTROL Gewichtung] | [!UICONTROL Zurücksetzen] |
| --- | --- | --- | --- |
| Beispiel: Zu Opportunity hinzufügen, Formular ausfüllen, E-Mail klicken, Link klicken, E-Mail öffnen, E-Mail abmelden, Web-Seite besuchen, Fragen im Webinar stellen, Asset-Downloads im Webinar, Interessanter Moment, Beantwortet der Umfrage im Webinar, Opportunity aktualisieren | Schreibgeschützt | Dropdown-Liste, bearbeitbar für Entwurfsmodelle | **↺**-Symbol: Setzt diese Zeile auf den von KI vorgeschlagenen Wert zurück |

**Gewichtungsstufen** (gleiche Skala für die Spalten „Vorgeschlagene KI“ und „Gewichtung„):

| Stufe | Wert |
| ---| --- |
| [!UICONTROL Kein Gewicht] | 0 |
| [!UICONTROL Trivial] | 30 |
| [!UICONTROL Gering] | 40 |
| [!UICONTROL normal] | 60 |
| [!UICONTROL Wichtig] | 90 |
| [!UICONTROL WICHTIG] | 100 |

![Ändern des Werts für die Aktivität „Zu Opportunity hinzufügen“ in einem Entwurfsabsichtsmodell](./assets/intent-configuration-model-edit.png){width="550" zoomable="yes"}

Wenn Sie eine Aktivität auf **[!UICONTROL Kein Gewicht]** (0) setzen, wird sie nicht vollständig bewertet. Das System schließt derzeit **[!UICONTROL E-Mail abmelden]** standardmäßig mit dieser Methode aus.

Klicken Sie **[!UICONTROL der Tabelle auf „Alle auf Vorschlag zurücksetzen]**, um für jede Zeile den von KI vorgeschlagenen Wert wiederherzustellen.

### Erstellen und Aktivieren eines Modells

Gehen Sie wie folgt vor, um ein neues Gewichtungsmodell zu erstellen und zu aktivieren.

1. Mit einem vorhandenen Modell _[!UICONTROL Entwurf]_ beginnen.

   Sie können auch auf **[!UICONTROL Duplizieren]** klicken, damit das aktuelle _[!UICONTROL Aktiv]_-Modell seine Gewichtungen in einen neuen Entwurf klonen kann.

1. Passen Sie die Gewichtungen Zeile für Zeile an, um zu berücksichtigen, was für Ihr Unternehmen wichtig ist.

   Beispielsweise kann eine Aktivität mit niedrigem Signal auf **[!UICONTROL Trivial]** herabgestuft oder ein Aktivität mit hohem Signal auf **[!UICONTROL Wichtig]** oder **[!UICONTROL Wichtig]** aktualisiert werden.

1. Klicken Sie auf **[!UICONTROL Speichern]**.

   Beim Speichern werden Sie aufgefordert, das Modell sofort zu aktivieren.

1. Aktivierung bestätigen.

Die Bestätigung macht es zum neuen _[!UICONTROL Aktiv]_-Modell und stuft das zuvor aktive automatisch zu _[!UICONTROL Archiviert]_ herab. Es kann immer nur ein Modell aktiv sein.

### Von KI vorgeschlagene Spalte

Die Spalte KI-Vorschlag ist ein Ausgangspunkt, keine trainierte Empfehlung.

* Ein LLM-Abschlussaufruf verarbeitet alle Aktivitäten eines Mandanten gleichzeitig, nicht ein Aufruf pro Aktivität.

* Für jede Aktivität liest das Modell nur den Namen und die Beschreibung und wählt dann eine Gewichtungsstufe auf der Grundlage allgemeiner Kenntnisse des B2B-Käuferverhaltens aus. Betrachten Sie beispielsweise, was **[!UICONTROL Formular ausfüllen]** oder **[!UICONTROL E-Mail]** normalerweise einem B2B-Käufer signalisiert. Es hat keinen Zugriff auf Kundendaten, CRM-Datensätze oder historische Interaktionsmuster des Mandanten und ist heute nicht mandanten- oder abonnementspezifisch.

* Die Ausgabe füllt `SUGGESTED_WEIGHT_VALUE` zur Modellerstellungszeit in `IBG_INTENT_ACTIVITY_WEIGHT` und bleibt anschließend statisch. Er wird beim Bearbeiten der Spalte „Gewichtung“ nicht aktualisiert.

* Jede Aktivitätszeile enthält immer einen ausgefüllten empfohlenen Wert. Keine werden leer gelassen.

Überprüfen und passen Sie jede Zeile entsprechend Ihrem eigenen Geschäftskontext an. Die vorgeschlagenen Werte sind eine vernünftige Standardeinstellung und kein angepasstes Modell.

## Modellaktionen

Sie können ein Modell basierend auf seinem Status verwalten.

| Aktion | Verfügbar für | Was passiert? |
| --- | --- | --- |
| **[!UICONTROL Duplizieren]** | aktiv, Entwurf | Öffnet ein Modal mit dem **[!UICONTROL „Duplizieren]**, mit einem vorausgefüllten Namensfeld und **[!UICONTROL Abbrechen]** und **[!UICONTROL Duplizieren]**. Durch Bestätigen wird ein neues _[!UICONTROL Entwurf]_-Modell mit denselben Gewichtungen erstellt, das direkt in der Detailansicht geöffnet wird. |
| **[!UICONTROL Aktivieren]** | Nur Entwurf (wird auch direkt nach dem Speichern als Eingabeaufforderung angezeigt) | Hebt den Entwurf auf _[!UICONTROL Aktiv]_ und stuft das zuvor aktive Modell automatisch zu _[!UICONTROL Archiviert]_ herab. |
| **[!UICONTROL Löschen]** | Nur Entwurf | Vor dem endgültigen Löschen wird ein Bestätigungsdialogfeld angezeigt. Diese Aktion kann nicht rückgängig gemacht werden. Aktive Modelle können nicht gelöscht werden. |

Da nur Entwurfsmodelle bearbeitet werden können, besteht der normale Workflow darin, auf **[!UICONTROL Duplizieren]** für das aktuelle _[!UICONTROL Aktiv]_-Modell zu klicken, die Gewichtungen auf der Entwurfskopie anzupassen und dann auf **[!UICONTROL Speichern]**. Sie können ihn sofort oder später über die Schaltfläche **[!UICONTROL Aktivieren]** aktivieren.

## Gewichtungsberechnungen in Intent Scores

Die Spalte **[!UICONTROL Gewichtung]** zeigt die Zahl an, die bei der täglichen Bewertung verwendet wird, gelesen aus der Zeile für das aktuell _[!UICONTROL aktive]_ Modell. Drei Dinge bestimmen die Absichtsbewertung eines Leads:

1. **Die hier konfigurierte Gewichtung** (`WEIGHT_VALUE`) für jede Aktivität. Sie beginnt mit dem KI-Vorschlag, kann jedoch pro Mandant überschrieben werden. Es wird nur die mit dem _[!UICONTROL Active]_-Modell verknüpfte Zeile verwendet, sodass eine Gewichtungsänderung keine Code-Freigabe erfordert.

1. **Inhaltsrelevanz**: hier nicht konfigurierbar. Das System extrahiert Keywords aus aktivitätsbezogenen Inhalten oder Assets und bewertet, wie gut dieser Inhalt mit einem Keyword, einem Produkt oder einer Kategorie übereinstimmt, von 0 bis 1.

1. **Häufigkeit**: Wie oft ein Lead mit diesem Inhalt interagiert hat, berücksichtigt bei der Durchschnittsbildung über die Interaktionen einer Person hinweg.

Formal, pro Interaktion: `activity weight × content relevance`, gemittelt in einen **Tageswert** mit einem **7-tägigen exponentiellen Abfall** angewendet, sodass die jüngste Aktivität dominiert, dann normalisierte sich die Min-max auf 0 bis 1 in der aktuellen Population und gruppierte sich:

| Endergebnis | Absichtsstufe |
| --- | --- |
| > 0.6 | Hoch |
| > 0.2 | Medium |
| Andernfalls | Niedrig |

### Inhaltsrelevanz

Bei Web-basierten Aktivitäten überprüft das System die Asset-URL und das zugehörige Unternehmen und leitet dann relevante Keywords aus der Taxonomie dieses Unternehmens ab. Beispielsweise zeigt eine mit [!DNL Intuit] verknüpfte URL Schlüsselwörter wie _Steuer_ oder _Lohn_. Die tatsächliche Interaktion eines Leads mit diesem Inhalt, z. B. das Anzeigen einer [!DNL TurboTax] oder einer [!DNL QuickBooks], wird mit diesen Keywords verglichen, um zu bestimmen, welchem bestimmten Produkt das Interesse zugeordnet ist. Bei Nicht-Web-Aktivitäten wie _[!UICONTROL Interessanter Moment]_ (einschließlich Offline-Ereignissen) bewertet das Modell die Beschreibung oder den Inhalt des Moments, z. B. ein Offline-Webinar-Thema, anstelle des Aktivitätstyps. Die Relevanz wird durch den Inhalt und nicht durch die Ereigniskategorie bestimmt.

## Bekannte Einschränkungen

Die folgenden Einschränkungen gelten für die aktuelle Intent-Konfiguration.

* **Derzeit keine benutzerdefinierten oder von Mandanten definierten Aktivitäten.** Der Aktivitätskatalog ist fest und [!DNL Marketo Engage] ist die einzige Quelle der Wahrheit. Um eine Bewertung zu erhalten, muss eine Aktivität [!DNL Marketo Engage] angemeldet sein. Eine zukünftige Spalte für von Mandanten definierte Aktivitäten wird in den Gültigkeitsbereich aufgenommen.
* **Keine Aufnahme von Drittanbietern,**. B. aus [!DNL Demandbase], [!DNL ZoomInfo] oder [!DNL 6sense]. Dieses Update ist für spätere Versionen geplant. Bis dahin besteht die Problemumgehung darin, die Zielgruppe im Tool eines Drittanbieters zu erstellen und sie direkt in [!DNL Marketo Engage] oder [!DNL Marketo Optimizer] zu pushen, wobei die Absichtsbewertung für dieses Signal umgangen wird.
* **Kein nativer Export** aus dem Bedienfeld „Gewichtung“ oder aus Absichtsberichten. Siehe [Weiterverfolgung von Berichten](../agents/intent.md#report-follow-up) für Aufforderungen, die Berichtsergebnisse in eine Personenliste umzuwandeln.
