---
title: Interoperabilität mit Marketo Engage
description: Erfahren Sie, was Marketo Optimizer für Marketo Engage freigibt, einschließlich Daten, Aktivitäten und Zielgruppen, und wie Sie E-Mails von einem der Produkte in Ihren Journey senden.
role: User, Admin
autotag-review: '2026-10-01T18:40:01.444Z'
TQID: 'https://experienceleague.adobe.com/7TB6JG9yiUT-l0VevNW4tvwieCyFjOypZwI0SlUzmmY'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
  - id: 46e599c6-e20f-5f67-9824-93415016f66b
    internal-label: Audiences
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
  - id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4
    internal-label: Programs
  - id: d4203578-d294-5145-b397-f26f4488a904
    internal-label: Channels
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 518a807aeed2471772b4f0a4d6d8d525cd3e22fd
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 0%
---

# Interoperabilität mit Marketo Engage

[!DNL Adobe Marketo Optimizer] und [!DNL Adobe Marketo Engage] geben Daten, einige Aktivitäten und Zielgruppen frei. Sie halten Assets getrennt. Erfahren Sie, was die einzelnen Produktfreigaben nutzen, um zu entscheiden, wo Sie Ihr Marketing aufbauen und versenden können.

## Geteilt zwischen den Produkten {#shared}

* [!DNL Marketo Engage] Leads und Aktivitäten fließen automatisch in [!DNL Marketo Optimizer].
* Journey können auf [!DNL Marketo Engage] Aktivitäten lauschen.
* Zu den ereignisbasierten Zielgruppen können Personen gehören, die [!DNL Marketo Engage] Aktivitäten durchführen.
* Journey-Aktionen können mit [!DNL Marketo Engage] interagieren. Sie können Personen zu einer [!DNL Marketo Engage] hinzufügen oder daraus entfernen und eine [!DNL Marketo Engage] Kampagne anfordern.
* [!UICONTROL Scoring Studio] bewertet Personen anhand von [!DNL Marketo Engage]- und [!DNL Marketo Optimizer]. Sie können die Punktzahlen in [!DNL Marketo Engage] verwenden.
* Beide Produkte verwenden gemeinsame IP-Adressen und Subdomains.
* Einheitliches dialogorientiertes Reporting deckt beide Produkte ab.

## Getrennt aufbewahrt {#separate}

* **Assets:** E-Mails, Vorlagen, Programme und Bilder sind in separaten Repositorys verfügbar.
* **Aktivitäten:** [!DNL Marketo Optimizer] Aktivitäten werden nicht an [!DNL Marketo Engage] freigegeben.
* **Felder und Beschränkungen:** Personafelder, die [!DNL Marketo Optimizer] ableitet, sind in [!DNL Marketo Engage] nicht verfügbar. Kommunikationsbeschränkungen werden in jedem Produkt separat festgelegt.

Weitere Informationen zur Synchronisierung finden Sie unter [Entitätssynchronisierung](./data-architecture.md#entity-sync).

## E-Mail von Marketo Engage senden {#send-from-marketo}

Verwenden Sie diesen Ansatz, um Journey, Warteschritte und KI-Entscheidungen in [!DNL Marketo Optimizer] auszuführen, während [!DNL Marketo Engage] jede E-Mail sendet.

1. Erstellen Sie [!DNL Marketo Optimizer] eine Journey, die Warteschritte und KI-Entscheidungen enthält.
1. Fügen Sie für jeden Versandschritt die Aktion **[!UICONTROL Marketo Engage-Kampagne anfragen]** hinzu und wählen Sie eine passende [!DNL Marketo Engage] aus.
1. Optional: Fügen Sie ein standardmäßiges, übergeordnetes Programm hinzu, [!DNL Marketo Engage] die Erfolgsberichte auf der gesamten Journey zu aggregieren.

Weitere Informationen zu Aktionen finden Sie unter [Aktionsknoten ausführen](./marketing/action-nodes.md).

[!DNL Marketo Engage] sendet die E-Mail über die vorhandenen Kanaleinstellungen. Da [!DNL Marketo Engage] die E-Mail sendet, konfigurieren Sie keine Kanäle oder E-Mails in [!DNL Marketo Optimizer]. Zusätzlich gilt Folgendes:

* Sendet, öffnet und klickt auf [!DNL Marketo Engage].
* Die Abmeldeverwaltung und E-Mail-Governance gelten in [!DNL Marketo Engage].
* Die E-Mail-Aktivität liefert Daten für Ihre bestehenden [!DNL Marketo Engage].
* Aktivitätsgesteuerte Salesforce-Synchronisierungskampagnen werden erwartungsgemäß ausgeführt.
* Jeder sendet Karten an eine [!DNL Marketo Engage] Kampagne, sodass Sie die Programmmitgliedschaft pro E-Mail-Kampagne verfolgen und in vertrauten Programmen berichten können.

## E-Mail von Marketo Optimizer senden {#send-from-optimizer}

Verwenden Sie diesen Ansatz, um die Journey zu erstellen und E-Mails vollständig in [!DNL Marketo Optimizer] zu senden. [!DNL Marketo Engage] bleibt das Aufzeichnungssystem für die Übergabe an Ihr CRM-System (Customer Relationship Management).

1. Einrichten des E-Mail-Kanals. Erstellen Sie E-Mail-Vorlagen und konfigurieren Sie die IP-Adresse und Subdomain, Abmelde-Links und Landingpages. Siehe [E-Mail-](./start/email-deliverability.md).
1. Kommunikationsbeschränkungen in [!DNL Marketo Optimizer] festlegen. Freigegebene Kommunikationsbeschränkungen sind nicht verfügbar.
1. Erstellen Sie die Journey mit Zielgruppen, KI-Entscheidungsfindung und dem nächstbesten Pfad.
1. E-Mail von [!DNL Marketo Optimizer] senden. [!DNL Marketo Optimizer] zeichnet die Aktivitäten auf.
1. Bewerten Sie Personen in [!UICONTROL Scoring Studio], um ein Modell für [!DNL Marketo Engage] und [!DNL Marketo Optimizer] Aktivität zu erstellen. Siehe [Scoring Studio](./labs/scoring-studio.md).

Abmeldungen werden automatisch über freigegebene Felder mit [!DNL Marketo Engage] synchronisiert. [!DNL Marketo Optimizer] E-Mail-Aktivität wird nicht an [!DNL Marketo Engage] zurückgesendet, aber [!UICONTROL Scoring Studio] verwendet sie weiterhin.

### Übergabe von Leads an den Verkauf {#hand-off}

[!DNL Marketo Optimizer] hat keine direkte CRM-Integration. Führen Sie mit einer der folgenden Methoden durch [!DNL Marketo Engage]:

* **Bewertungsbasiert:** Das Feld Bewertung wird in [!DNL Marketo Engage] angezeigt, und eine intelligente Kampagne synchronisiert den Lead mit Ihrem CRM.
* **Aktivitätsbasiert:** Eine [!DNL Marketo Optimizer] Journey überwacht die Aktivität und fügt den Lead zu einer [!DNL Marketo Engage] Smart-Kampagne hinzu.
* **Programmmitgliedschaft:** Die Journey befindet sich in einem [!DNL Marketo Optimizer] Programm, sodass Sie den Status von Anfang bis Ende verfolgen können.
