---
title: Datenarchitektur
description: Erfahren Sie, wie Marketo Optimizer und Marketo Engage Daten gemeinsam nutzen, einschließlich Synchronisierungsrichtung und Latenz der Entität, Aktivitätsdatenfluss und Sandbox-basierter Datenisolierung.
role: User, Admin
autotag-review: '2026-10-01T18:40:38.362Z'
TQID: 'https://experienceleague.adobe.com/oelEtys81g6TzM8bi-qy1nuWw6scOBry7tbZkMkZ6u0'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
  - id: 3cf5f37e-e87e-5179-812b-53ce05d7eebb
    internal-label: Setup
  - id: 46e599c6-e20f-5f67-9824-93415016f66b
    internal-label: Audiences
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
  - id: d4203578-d294-5145-b397-f26f4488a904
    internal-label: Channels
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
source-git-commit: 518a807aeed2471772b4f0a4d6d8d525cd3e22fd
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 1%
---

# Datenarchitektur

[!DNL Adobe Marketo Optimizer] lässt sich mit [!DNL Adobe Marketo Engage] integrieren, um einen umfassenden Überblick über B2B-Leads zu erhalten. Eine bidirektionale, vertrauenswürdige Synchronisierung sorgt dafür, dass beide Produkte aufeinander abgestimmt sind, sodass sie eine einheitliche Sicht auf Personen, Unternehmen, benutzerdefinierte Objekte und Aktivitäten haben. [!DNL Marketo Engage] bleibt die maßgebliche Quelle für Personendaten. Jede [!DNL Marketo Optimizer] ist mit einer [!DNL Marketo Engage] gepaart.

## Datengrundlage {#data-foundation}

[!DNL Marketo Optimizer] und [!DNL Marketo Engage] verwenden eine gemeinsame Datengrundlage, auf der sie synchronisiert bleiben, während sie Daten für nachgelagerte Analysen bereitstellen.

![Architekturdiagramm für Marketo Optimizer und Marketo Engage, das zeigt, wie die Services, Laufzeiten und Datenspeicher der beiden Produkte in Microsoft Azure und AWS verbunden sind](./assets/marketo-optimizer-architecture.svg)

Auf allgemeiner Ebene:

* **[!DNL Marketo Engage]** ist die definitive Quelle für Lead- und benutzerdefinierte Objektdaten, die die Datenintegrität zum Zeitpunkt der Erfassung sicherstellt.
* Eine **Datenbrokerschicht** koordiniert den Datenverkehr zwischen den beiden Produkten. Sie aggregiert freigegebene und replizierte Daten in eine einsatzbereite Datenbank. Der gesamte Austausch läuft in einem einzigen Aurora MySQL-Cluster.
* **[!DNL Marketo Optimizer]** ist die maßgebliche Quelle für die ausgeführten Journey-Aktivitäten.

## Synchronisierung von Entitäten {#entity-sync}

Jeder Entitätstyp wird in der Richtung und mit der Geschwindigkeit synchronisiert, die die Datenintegrität am besten schützt.

| Entität [!DNL Marketo Engage] | Synchronisationsrichtung | Latenz |
| --- | --- | --- |
| Lead | bidirektional | Unter 1 Sekunde |
| Unternehmen | bidirektional | Unter 1 Sekunde |
| Benutzerdefiniertes Objekt | unidirektional | Unter 5 Sekunden |
| Aktivität | unidirektional | Unter 5 Sekunden |
| Programmmitgliedschaft | Nicht synchronisiert | Nicht zutreffend |
| Assets | Nicht synchronisiert | Nicht zutreffend |

Die Synchronisierung erfolgt auf zwei Arten:

* **Leads, Unternehmen und Standardobjekte:** [!DNL Marketo Engage] steuert die Personentabelle und gibt sie über Lese- und Schreib-Datenbankansichten frei. Aktualisierungen in einem Produkt werden sofort in dem anderen angezeigt, und es werden keine doppelten Kopien erstellt.
* **Benutzerdefinierte Objekte:** Daten werden innerhalb von Sekunden aus [!DNL Marketo Engage] repliziert. Schemaaktualisierungen in [!DNL Marketo Engage] sind für aktive Journey sofort verfügbar.

[!DNL Marketo Engage] und [!DNL Marketo Optimizer] synchronisieren keine Programmmitgliedschaft oder Assets. Durch diesen Ausschluss werden Systemgeschwindigkeit und -integrität gewahrt.

>[!NOTE]
>
>Daten, die mit [!DNL Marketo Optimizer] und mit dem Data Warehouse synchronisiert werden, sind letztendlich konsistent. Der Zeitpunkt hängt von der zugrunde liegenden Änderungsdatenerfassung, dem Batch oder dem Stream-Mechanismus ab.

Dieses nahezu in Echtzeit ausgeführte Design liefert aktuelle Daten in Journey und Berichten. Sie können Leads mit hoher Priorität schnell nachverfolgen. Sie können auch B2B-Kontextdaten wie Produktnutzung und -absicht beim Journey von Entscheidungen verwenden, wenn diese sich ändern.

## Aktivitätsdatenfluss {#activity-flow}

Aktivitäten folgen einem separaten Pfad von anderen Entitäten. Jede Aktivität durchläuft fünf Phasen:

1. **Primäre Erfassung:** [!DNL Marketo Engage] schreibt die Aktivität in die freigegebene Datenbank und indiziert sie in Apache SOLR, um innerhalb von [!DNL Marketo Engage] schnell suchen zu können.
1. **Produktübergreifende Wahrnehmung:** [!DNL Marketo Engage] veröffentlicht die Aktivität in der Aktivitäts-Pipeline, sodass [!DNL Marketo Optimizer] sie sofort erhält.
1. **Analytische Transformation:** Die Journey-Laufzeitumgebung verarbeitet die Aktivität und schreibt sie in Snowflake, wodurch Betriebsdaten in analysefähige Daten umgewandelt werden. Alle bisherigen Phasen laufen in Amazon Web Services (AWS).
1. **Nachgelagertes Ziel:** [!DNL Marketo Optimizer] repliziert die Aktivität in [!DNL Adobe Experience Platform] Datensätze.
1. **Berichte:** Der Datensatz-Feed wurde [!DNL Adobe Customer Journey Analytics] Berichte eingebettet. [!DNL Customer Journey Analytics] können auf Microsoft Azure oder AWS gehostet werden. Sie können die Datensätze auch mit [!DNL Query Service] abfragen. Siehe [Experience Platform-](./reports/aep-datasets.md).

Journey- und Ereignis-Zielgruppen können sowohl [!DNL Marketo Optimizer] Aktivitäten als auch eine Untergruppe [!DNL Marketo Engage] Aktivitäten verwenden. Sie verwenden beide Sets auf die gleiche Weise. [!DNL Marketo Optimizer] Aktivitäten werden nicht an [!DNL Marketo Engage] zurückgesendet.

Verwenden Sie Aktivitäten wie Formularausfüllungen, Web-Besuche und E-Mail-Interaktion, um Personen-Journey in Triggern, Filtern und Verzweigungen zu erstellen:

* [Ereignis-Trigger für die Überwachung eines Ereignisknotens](./marketing/listen-for-event-nodes.md#event-triggers)
* [Ereignisfilter für die Überwachung eines Ereignisknotens](./marketing/listen-for-event-nodes.md#event-filters)
* [Abgestimmte Personenfilter für aufgeteilte Pfade und Knoten](./marketing/split-merge-paths-nodes.md#matched-person-filters)
* [Ereignisbasierte Zielgruppen](./audiences/event-based-audiences.md)

## Datenisolierung und Sandboxes {#data-isolation}

[!DNL Marketo Engage], [!DNL Marketo Optimizer] und [!DNL Experience Platform] geben Kundendaten im Rahmen dieser Architektur frei. Adobe isoliert Ihre Daten mithilfe von [!DNL Experience Platform]-Sandboxes logisch von anderen Mandanten. Daten werden über sichere, verschlüsselte Kanäle übertragen. Adobe speichert sie in Adobe Managed Services mit branchenüblicher Verschlüsselung und Zugriffssteuerung.

Jede [!DNL Marketo Optimizer] verfügt über eine dedizierte Produktkarte in der [!DNL Adobe Admin Console] und eine dedizierte Sandbox. Adobe stellt beide automatisch bereit, sodass Sie keine Sandbox erstellen. Der Sandbox-Name verwendet das Muster `mktoaep<prefix>` , wobei das Präfix Ihr [!DNL Marketo Engage] ist. Wenn Sie [!DNL Marketo Optimizer] mit mehr als einer [!DNL Marketo Engage] verwenden, verfügt jede Instanz über eine eigene Produktkarte und Sandbox.

[!DNL Marketo Optimizer] ist nur in dieser Sandbox verfügbar, auch wenn Ihre Organisation über andere Sandboxes verfügt.

Bei der Bereitstellung wird kein Sandbox-Zugriff zugewiesen. Rollen haben in der Regel Zugriff auf die standardmäßige `prod`-Sandbox, [!DNL Marketo Optimizer] sie jedoch nicht verwendet. Weisen Sie jeder [!DNL Experience Platform]-Rolle explizit die dedizierte Sandbox zu, da sonst Benutzende nicht in [!DNL Marketo Optimizer] arbeiten können. Verwenden Sie Benutzergruppen, um Benutzer hinzuzufügen und zu entfernen, ohne die Rolleneinrichtung zu wiederholen. Das vollständige Verfahren finden Sie unter [Benutzerzugriff und Berechtigungen](./start/user-management.md).

[!DNL Marketo Optimizer] verwendet auch [!DNL Experience Platform] im Hintergrund. Dazu gehören die Schemaregistrierung, Ziele für den Paid-Media-Export, die Zugriffskontrolle und [!DNL Customer Journey Analytics]. Sie richten keine Schemata oder Namespaces ein. [!DNL Marketo Optimizer] erfordert keine [!DNL Real-Time Customer Data Platform], kein Echtzeit-Kundenprofil und keine Segmentierung.

>[!WARNING]
>
>Löschen Sie nicht die dedizierte [!DNL Marketo Optimizer]-Sandbox. Das Löschen ist dauerhaft und kann nicht rückgängig gemacht werden. [!DNL Marketo Optimizer] zur Wiederherstellung neu bereitstellen.
