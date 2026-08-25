---
title: Personalisieren von E-Mail-Inhalten nach Persona
description: Verwenden Sie die Personalization-Kenntnisse zu Inhalten in Marketo Optimizer, um eine E-Mail in personalbasierte, dateninformierte Varianten zu verwandeln. Personalisieren oder Analysieren von E-Mails
source-git-commit: 75b481faf0d66210329f95c8afabdfa59e7bcb79
workflow-type: tm+mt
source-wordcount: '1236'
ht-degree: 0%

---


# Personalisieren von E-Mail-Inhalten nach Persona

Die _Content Personalization_-Kompetenz wandelt eine E-Mail in personalbasierte, dateninformierte Varianten um, sodass Sie nicht für jede Audience eine separate E-Mail erstellen müssen. Anstatt eine Nachricht nach einem Ereignis zu senden, löst die Qualifikation Ihre Zielgruppe in [abgeleitete Persona](../audiences/personas.md) Kohorten auf, liefert Einblicke und generiert personalisierte Varianten. Jede Variante wird als bedingter Inhalt in einer einzigen E-Mail gespeichert, sodass jede Person automatisch die Version erhält, die ihrer Rolle entspricht, wenn eine Journey sie sendet.

* **Kenntnisse** - `content-personalization`
* **Aufruf** - Beschreiben Sie in der [Chat-](./chat-interface.md) eine Zielgruppe für eine neue E-Mail, wählen Sie **[!UICONTROL Diese E-Mail personalisieren]** oder **[!UICONTROL Diese E-Mail analysieren]** eine vorhandene E-Mail in einem [E-Mail-Knoten senden](../marketing/action-nodes.md)
* **Lese-/Schreibvorgänge nach** - [!DNL Marketo Optimizer]

## Schlüsselkonzepte {#key-concepts}

| Begriff | Definition |
|---|---|
| **Persona-Kohorte** | Eine Gruppe von Personen, die eine [abgeleitete Rolle“ &#x200B;](../audiences/personas.md), z. B. _CXO/EVP_ oder _Einzelne Mitwirkende_. |
| **Segment** | Eine Gruppe von Personen, die durch beliebige Kriterien definiert werden, z. B. Persona, Branche oder Interaktionsstufe. Eine Persona-Kohorte ist ein Segment, das speziell durch eine abgeleitete Persona definiert wird, die mit anderen geteilt wird. |
| **Zielgruppe** | Die Zielgruppe, die Sie in natürlicher Sprache beschreiben. Die Qualifikation löst sie in übereinstimmende Persona-Kohorten auf. |
| **Insight** | Ein dateninformiertes Ergebnis über die Botschaften, die Positionierung oder den Ton, der für eine persönliche Kohorte am besten funktioniert, basierend auf Ihren eigenen Daten. |
| **Variante** | Eine personalisierte Version der E-Mail-Abschnitte, die Sie personalisieren möchten, die für eine persönliche Kohorte generiert wurde. |
| **Personalisierte KI-E-Mail** | Die einzelne gespeicherte E-Mail, die jede Variante als [bedingte Inhalte](../content/conditional-content.md) blockiert. |
| **E-Mail-Audit** | Eine Überprüfung einer vorhandenen E-Mail für jedes Ihrer Zielgruppensegmente, die zeigt, was bei jeder Rolle Resonanz findet und was verbessert werden muss, bevor Sie personalisieren. |

## Voraussetzungen {#prerequisites}

* Zugriff auf [!DNL Marketo Optimizer] mit aktiviertem Coworker.
* [Abgeleitete Personas](../audiences/personas.md) in Ihren Daten aufgelöst. Die Qualifikation beruht auf diesen Klassifizierungen, um Personalkohorten zu erstellen. Die Unterstützung benutzerdefinierter Personas ist für eine zukünftige Version geplant.
* Genug historische Daten für Einblicke. Wenn für eine Persona-Kohorte keine Einblicke verfügbar sind, sagt Ihnen die Fähigkeit, dass die Daten unzureichend sind, und greift auf allgemeine Best Practices für diese Persona zurück.
* Eine [E-Mail](../content/templates.md)Vorlage oder eine vorhandene E-Mail, auf die durch einen [_E-Mail senden_-Aktionsknoten verwiesen &#x200B;](../marketing/action-nodes.md).
* Eine [Personen-Journey](../marketing/person-journeys.md) mit dem Aktionsknoten _E-Mail senden_, der zum Versand der personalisierten E-Mail verwendet wird.

## Erstellen und Personalisieren einer E-Mail aus einer Vorlage {#create-personalize-from-template}

Dieser Fluss verfasst eine neue E-Mail und personalisiert sie im selben Gespräch.

1. **Inhalt bereitstellen.** Laden Sie eine Inhaltsübersicht hoch oder beschreiben Sie die gewünschten Inhalte in natürlicher Sprache.

1. **Wählen Sie eine [Vorlage](../content/templates.md)** aus Ihrer Vorlagenbibliothek aus.

1. **Überprüfen Sie den Entwurf.**

   Coworker ordnet Ihren Inhalt der Vorlage zu und erstellt einen E-Mail-Entwurf. Sie können grundlegende Textbearbeitungen inline vornehmen.

   >[!WARNING]
   >
   >Während des Authorings sind nur grundlegende Textbearbeitungen inline verfügbar. Für erweiterte Bearbeitungen speichern Sie die E-Mail und öffnen Sie sie im [visuellen Design-Bereich](../content/email-authoring.md).

1. **Beschreiben Sie die** in natürlicher Sprache.

1. **Überprüfen Sie die aufgelösten Persona-Kohorten**.

   Coworker prüft Ihre Daten und gibt die persönlichen Kohorten zurück, die Ihrer Beschreibung entsprechen. Jede Kohorte wird gezählt. Überarbeiten Sie die Beschreibung der Zielgruppe und versuchen Sie es bei Bedarf erneut.

1. **Bestätigen Sie die**.

   Anschließend ruft ein Mitarbeiter Einblicke für jede aufgelöste Persona-Kohorte ab.

1. **Wählen Sie die zu personalisierenden Abschnitte aus** z. B. die Betreffzeile oder einen Hauptteilabschnitt, und überprüfen Sie die generierten Varianten.

   Variante neu erzeugen, wenn sie nicht passt. Die Anzahl der Rollenkohorten ist nicht festgelegt. Das hängt von Ihrer Zielgruppe und Ihren Daten ab.

1. **Speichern Sie die E-Mail**.

   Alle Varianten werden in einer personalisierten KI-E-Mail gespeichert, nicht als separate E-Mails.

<!-- screenshot: Coworker chat panel showing the resolved persona cohorts with counts, and the "Personalized variants" review grid -->

## Analysieren einer vorhandenen E-Mail {#analyze-existing-email}

Auf einer Journey [_Send Email_-Knoten](../marketing/action-nodes.md) die auf eine vorhandene E-Mail verweist, wird im Bedienfeld **[!UICONTROL Aktion]** der E-Mail-Name mit zwei Optionen angezeigt: **[!UICONTROL Diese E-Mail personalisieren]** und **[!UICONTROL Diese E-Mail analysieren]**.

<!-- screenshot: Send Email node "Take an action" panel showing the email name and the Personalize this email / Analyze this Email options -->

Wählen Sie **[!UICONTROL Diese E-Mail analysieren]** aus, um ein E-Mail-Audit durchzuführen:

1. **Beschreiben Sie die Zielgruppe** für die Sie eine Personalisierung durchführen möchten, in Bezug auf ihre Persona.

   Zum Beispiel _Personen in Marketing_ oder _Personen in Führungsfunktionen_.

1. **Überprüfen Sie die E-Mail-Prüfung.**

   Ein Mitarbeiter löst Ihre Beschreibung in Personensegmente auf und zeigt eine **E-Mail-Audit**-Karte an, auf der jedes Segment aufgelistet ist. Anschließend vergleicht er die E-Mail mit jeder einzelnen Karte, um herauszustellen, was Resonanz findet und was verbessert werden muss.

1. Der Mitarbeiter fragt, was als Nächstes zu tun ist, einschließlich **[!UICONTROL siehe Abschnitt-für-Abschnitt]** und **[!UICONTROL diese E-Mail personalisieren]**.

1. Wählen Sie **[!UICONTROL siehe Abschnitt-für-Abschnitt]** aus, um eine Ansicht **_E-Mail-Analyse_** mit einem Personaselektor und spezifischen Empfehlungen für jeden Abschnitt zu öffnen.

   In jedem Abschnitt wird angezeigt, wie viele Änderungen empfohlen werden, und jede Rolle zeigt eine Anzahl von Empfehlungen an, z. B. `4 recommendations for SVP/VP`. Sie können die Empfehlungen auch direkt anwenden, indem Sie _Chat_ Personalisieren“ eingeben.

1. Wählen Sie aus der Prüfung **[!UICONTROL Diese E-Mail personalisieren]** aus, um die Einblicke anzuwenden und Varianten zu generieren.

   Siehe folgenden Abschnitt &quot;[_einer vorhandenen E-Mail_](#personalize-existing-email).

<!-- screenshot: Email analysis view with persona selector, per-section "N changes" badges, and "what needs work" recommendations -->

## Vorhandene E-Mail personalisieren {#personalize-existing-email}

Wählen Sie **[!UICONTROL Diese E]** Mail personalisieren auf einem Aktionsknoten _E-Mail senden_ oder fahren Sie mit einem [E-Mail-Audit](#analyze-existing-email) fort, um eine bereits erstellte E-Mail zu personalisieren.

1. **Überprüfen Sie die aufgelösten Persona-Kohorten.**

   Coworker prüft Ihre Daten und gibt die persönlichen Kohorten zurück, die Ihrer Beschreibung entsprechen. Jede Kohorte wird gezählt. Überarbeiten Sie die Beschreibung der Zielgruppe und versuchen Sie es bei Bedarf erneut.

   Wenn Sie bei diesem Schritt aus einem E-Mail-Audit angekommen sind, fährt Coworker direkt mit den Audit-Erkenntnissen fort.

1. **Wählen Sie die zu personalisierenden Abschnitte** der E-Mail-Vorschau aus, z. B. die Betreffzeile und bestimmte Inhaltsabschnitte, und bestätigen Sie den Vorgang.

1. **Überprüfen Sie die generierten Varianten.**

   Neben der Persona können auch branchenspezifische Varianten variieren, z. B. ein CXO im Gesundheitswesen im Vergleich zu einem CXO in Finanzdienstleistungen. Der Mitarbeiter präsentiert ein **[!UICONTROL Personalisierte Varianten]** Raster, eine Karte pro Persona-Kohorte mit jeweils einer Betreffzeile, Überschrift, Hauptteil und einer **[!UICONTROL Vorschau]**-Option.

   Wählen Sie das _Information_-Symbol auf einer Karte aus, um die insight hinter dieser Variante anzuzeigen (die Rolle, auf der sie basiert, und die Interaktions-insight, die sie geprägt hat) und eine Variante bei Bedarf neu zu generieren.

   Sie können das Raster nach Persona filtern.

1. **Speichern Sie das Set.**

   Klicken Sie auf **[!UICONTROL Speichern]** und bestätigen Sie. Der Mitarbeiter bestätigt, dass die E-Mail jetzt in der KI-Bibliothek verfügbar ist, und fragt dann, ob die Änderungen auch auf die ursprüngliche E-Mail angewendet werden sollen, wodurch sie an Ort und Stelle aktualisiert wird.

<!-- screenshot: "Personalized variants" grid showing persona cards with subject, headline, body, Preview, and the info-icon insight tooltip -->

## Ausgabe gespeichert und in einem Journey verwendet {#saved-output}

Unabhängig davon, von welchem Fluss aus Sie beginnen, erstellt die Personalisierung eine einzelne **personalisierte KI-E-Mail** die in der KI-Bibliothek gespeichert ist. Die E[Mail enthält &#x200B;](../content/conditional-content.md)bedingte Inhalte). Um Abschnitte zu bearbeiten, öffnen Sie sie im [visuellen Design-Bereich](../content/email-authoring.md) und verwenden Sie „Inhalt **[!UICONTROL &quot;, um eine Vorschau der Auflösung der einzelnen Blöcke mit]** anzuzeigen.

Um die E-Mail auf einer Journey zu verwenden, fügen Sie einen [E-Mail senden](../marketing/action-nodes.md)-Knoten hinzu und wählen Sie **[!UICONTROL KI - Personalisierte]** E-Mails“ anstelle von **[!UICONTROL E-Mail erstellen]** aus und wählen Sie dann die gespeicherte E-Mail aus. Wenden Sie Ihre Konfigurations- und Geschäftsregeln wie gewohnt auf den Knoten an.

<!-- screenshot: Send Email node configuration with "AI Personalized Emails" selected and the saved email applied -->

## Laufzeitverhalten {#run-time-behavior}

Sie wählen die einzelne personalisierte KI-E-Mail in der Journey aus, nicht eine Variante pro Zielgruppe. Wenn der Journey ausgeführt wird, wird die E-Mail automatisch auf die Variante aufgelöst, die der Persona jedes Empfängers entspricht. Es wird keine Variante pro Empfänger ausgewählt.

## Einschränkungen {#limitations}

| Einschränkung | Detail |
|---|---|
| **Benutzerdefinierte Personas** | Noch nicht unterstützt. Die Qualifikation klassifiziert nur Persona-Kohorten aus nativen ([) &#x200B;](../audiences/personas.md). |
| **Nicht genügend Daten für Einblicke** | Wenn Ihre Daten keine insight für eine Persona-Kohorte unterstützen, gibt die Kenntnis dies an und greift auf allgemeine Best Practices für diese Persona zurück. |
| **Inline-Bearbeitung beim Authoring** | Inline sind nur grundlegende Textbearbeitungen verfügbar, wenn Sie [E-Mail aus einer Vorlage erstellen und personalisieren](#create-personalize-from-template). Für erweiterte Bearbeitungen ist der [visuelle Design-Bereich](../content/email-authoring.md) erforderlich. |
| **Ausgangspunkt erforderlich** | Zum Personalisieren einer E-Mail ist entweder eine Vorlage oder eine vorhandene E-Mail erforderlich, auf die von einem Knoten E-Mail senden verwiesen wird. |
