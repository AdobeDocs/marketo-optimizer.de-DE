---
title: Hochrangige Architektur
description: Erfahren Sie mehr über die Datenarchitektur, die Marketo Optimizer und Marketo Engage verbindet, einschließlich bidirektionaler Synchronisierung, Entitätslatenz und Mandantendatenisolierung.
role: User, Admin
TQID: 'https://experienceleague.adobe.com/oelEtys81g6TzM8bi-qy1nuWw6scOBry7tbZkMkZ6u0'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 3c1de303-7a7c-59a6-abca-8c534730e19cid: 64b90904-e4f0-5c1b-a871-8c6a40b204a1id: d4203578-d294-5145-b397-f26f4488a904
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: d00e9f03-e50b-4162-b143-0c0817c937c2id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 451
ht-degree: 1%

---


# Allgemeine Architektur

[!DNL Adobe Marketo Optimizer] lässt sich mit [!DNL Adobe Marketo Engage] integrieren, um eine 360-Grad-Ansicht von B2B-Leads zu erhalten. Eine bidirektionale, vertrauenswürdige Synchronisierung sorgt dafür, dass [!DNL Marketo Engage] und [!DNL Marketo Optimizer] aufeinander abgestimmt bleiben, sodass beide Plattformen eine einzige, gemeinsame Ansicht von Personen, Unternehmen, benutzerdefinierten Objekten und Aktivitäten haben. Der leistungsstarke nahezu in Echtzeit ausgeführte Datenfluss sorgt dafür, dass die Datensätze aktuell und ausführbar bleiben, sodass Kampagnen und Journey sofort auf Leads reagieren können.

## Datengrundlage

[!DNL Marketo Optimizer] und [!DNL Marketo Engage] verwenden eine gemeinsame Datengrundlage, auf der sie synchronisiert bleiben, während sie Daten für nachgelagerte Analysen bereitstellen.

![Architekturdiagramm von Marketo Optimizer und Marketo Engage, das zeigt, wie die Services, Laufzeiten und Datenspeicher der beiden Produkte in Microsoft Azure und AWS miteinander verbunden sind](./assets/marketo-optimizer-architecture.svg)

Auf allgemeiner Ebene:

* **[!DNL Marketo Engage]Core** ist die definitive Quelle für Lead- und benutzerdefinierte Objektdaten und stellt die Datenintegrität zum Zeitpunkt der Erfassung sicher.
* Eine **Datenbrokerschicht** koordiniert den Datenverkehr zwischen [!DNL Marketo Engage] und [!DNL Marketo Optimizer] und aggregiert freigegebene und replizierte Daten in eine einsatzbereite Umgebung. Dieser gesamte Austausch läuft in einer einzigen gemeinsamen AWS Aurora-Instanz und bildet die Closed-Loop-Grundlage für eine groß angelegte B2B-Orchestrierung.
* **Aktivitäten** folgen einem definierten Pfad: Sie werden zuerst in die [!DNL Marketo Engage]-Datenbank geschrieben und in Apache SOLR für eine schnelle produktinterne Suche indiziert. Anschließend werden sie in der Aktivitäts-Pipeline veröffentlicht, damit [!DNL Marketo Optimizer] sofort auf sie aufmerksam wird. Die Journey-Laufzeit verarbeitet diese Aktivität und schreibt sie in Snowflake, wodurch Betriebsdaten in einen analysefähigen Status umgewandelt werden. Von dort aus werden Aktivitäten in [!DNL Adobe Experience Platform] Datensätze repliziert und für das Reporting [!DNL Adobe Customer Journey Analytics].
* Verschiedene Entitätstypen werden mit unterschiedlichen Geschwindigkeiten und Richtungen synchronisiert, um Frische und Systemintegrität in Einklang zu bringen:

| Entität [!DNL Marketo Engage] | Synchronisationsrichtung | Latenz |
| --- | --- | --- |
| Lead | Bidirektional | &lt; 1 Sek |
| Unternehmen | Bidirektional | &lt; 1 Sek |
| Benutzerdefiniertes Objekt | unidirektional | &lt; 5 s |
| Aktivität | unidirektional | &lt; 5 s |
| Programmmitgliedschaft | Nicht synchronisiert | – |
| Assets | Nicht synchronisiert | – |

Leads und Unternehmen werden sofort in beide Richtungen aktualisiert, ohne dass doppelte Datenkopien erstellt werden. Benutzerdefinierte Objekte werden innerhalb von Sekunden repliziert, sodass Schemaaktualisierungen in [!DNL Marketo Engage] auf einer aktiven Journey sofort wirksam werden können. Programmmitgliedschaft und Assets werden absichtlich von der Synchronisierung ausgeschlossen, um die Systemgeschwindigkeit und -integrität zu wahren.

Dieses Design mit nahezu null Latenz bedeutet, dass Analytics-Dashboards und nachgelagerte Systeme nahezu in Echtzeit gespeist werden, was eine Live-Kampagnenoptimierung und eine schnelle Nachverfolgung von Leads mit hoher Priorität ermöglicht.

### Isolierung und Mandantenfähigkeit von Daten

* Kundendaten werden von [!DNL Marketo Engage], [!DNL Marketo Optimizer] und [!DNL Experience Platform] im Rahmen der Produktsynchronisierungs- und Analysearchitektur gemeinsam genutzt.
* Die Daten sind für jeden Mandanten logisch isoliert und durch Adobe-Sicherheitskontrollen geschützt.
* Die Daten werden über sichere, verschlüsselte Kanäle übertragen und in Adobe Managed Services gespeichert, wobei Verschlüsselung und Zugriffskontrolle nach Industriestandard verwendet werden.
* Je nach Datentyp können Informationen zwischen [!DNL Marketo Engage] und [!DNL Marketo Optimizer] synchronisiert oder auf [!DNL Experience Platform] repliziert werden, um Reporting- und Analysefunktionen zu unterstützen, während die Sicherheit und die Mandantenisolation erhalten bleiben.
