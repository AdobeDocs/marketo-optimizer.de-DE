---
title: Hochrangige Architektur
description: Erfahren Sie mehr über die Datenarchitektur, die Marketo Optimizer und Marketo Engage verbindet, einschließlich bidirektionaler Synchronisierung, Entitätslatenz und Mandantendatenisolierung.
role: User, Admin
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 2%

---


# Allgemeine Architektur

[!DNL Adobe Marketo Optimizer] lässt sich mit [!DNL Adobe Marketo Engage] integrieren, um eine 360-Grad-Ansicht von B2B-Leads zu erhalten. Eine bidirektionale, vertrauenswürdige Synchronisierung sorgt dafür, dass Marketo Engage und Marketo Optimizer aufeinander abgestimmt bleiben, sodass beide Plattformen eine einheitliche, gemeinsame Ansicht von Personen, Unternehmen, benutzerdefinierten Objekten und Aktivitäten erhalten. Der leistungsstarke nahezu in Echtzeit ausgeführte Datenfluss sorgt dafür, dass die Datensätze aktuell und ausführbar bleiben, sodass Kampagnen und Journey sofort auf Leads reagieren können.

## Datengrundlage

[!DNL Marketo Optimizer] und [!DNL Marketo Engage] verwenden eine gemeinsame Datengrundlage, auf der beide Plattformen synchronisiert bleiben, während Daten für nachgelagerte Analysen bereitgestellt werden.

![Architekturdiagramm von Marketo Optimizer und Marketo Engage, das zeigt, wie die Services, Laufzeiten und Datenspeicher der beiden Produkte in Microsoft Azure und AWS miteinander verbunden sind](./assets/marketo-optimizer-architecture.svg)

Auf allgemeiner Ebene:

* **Marketo Engage Core** ist die definitive Quelle für Lead- und benutzerdefinierte Objektdaten und stellt die Datenintegrität zum Zeitpunkt der Erfassung sicher.
* Eine **Datenbrokerschicht** koordiniert den Datenverkehr zwischen Marketo Engage und Marketo Optimizer und aggregiert freigegebene und replizierte Daten in eine einsatzbereite Umgebung. Dieser gesamte Austausch läuft in einer einzigen gemeinsamen AWS Aurora-Instanz und bildet die Closed-Loop-Grundlage für eine groß angelegte B2B-Orchestrierung.
* **Aktivitäten** folgen einem definierten Pfad: Sie werden zuerst in die Marketo Engage-Datenbank geschrieben und in Apache SOLR für eine schnelle produktinterne Suche indiziert. Anschließend werden sie in der Aktivitäts-Pipeline veröffentlicht, damit Marketo Optimizer sofort erkannt wird. Die Journey-Laufzeit verarbeitet diese Aktivität und schreibt sie in Snowflake, wodurch Betriebsdaten in einen analysefähigen Status umgewandelt werden. Von dort aus werden Aktivitäten in AEP-Datensätze und CJA repliziert, um das Reporting zu unterstützen.
* Verschiedene Entitätstypen werden mit unterschiedlichen Geschwindigkeiten und Richtungen synchronisiert, um Frische und Systemintegrität in Einklang zu bringen:

| Marketo Engage-Entität | Synchronisationsrichtung | Latenz |
| --- | --- | --- |
| Lead | Bidirektional | &lt; 1 Sek |
| Unternehmen | Bidirektional | &lt; 1 Sek |
| Benutzerdefiniertes Objekt | unidirektional | &lt; 5 s |
| Aktivität | unidirektional | &lt; 5 s |
| Programmmitgliedschaft | Nicht synchronisiert | – |
| Assets | Nicht synchronisiert | – |

Leads und Unternehmen werden sofort in beide Richtungen aktualisiert, ohne dass doppelte Datenkopien erstellt werden. Benutzerdefinierte Objekte werden innerhalb von Sekunden repliziert, sodass Schemaaktualisierungen in Marketo Engage auf einer aktiven Journey sofort verarbeitet werden können. Programmmitgliedschaft und Assets werden absichtlich von der Synchronisierung ausgeschlossen, um die Systemgeschwindigkeit und -integrität zu wahren.

Dieses Design mit nahezu null Latenz bedeutet, dass Analytics-Dashboards und nachgelagerte Systeme nahezu in Echtzeit gespeist werden, was eine Live-Kampagnenoptimierung und eine schnelle Nachverfolgung von Leads mit hoher Priorität ermöglicht.

### Isolierung und Mandantenfähigkeit von Daten

* Kundendaten werden von Marketo Engage, Marketo Optimizer und Experience Platform im Rahmen der Produktsynchronisierung und -analysearchitektur gemeinsam genutzt.
* Die Daten sind für jeden Mandanten logisch isoliert und durch Adobe-Sicherheitskontrollen geschützt.
* Die Daten werden über sichere, verschlüsselte Kanäle übertragen und in Adobe Managed Services gespeichert, wobei Verschlüsselung und Zugriffskontrolle nach Industriestandard verwendet werden.
* Je nach Datentyp können Informationen zwischen Marketo Engage und Marketo Optimizer synchronisiert oder auf Experience Platform repliziert werden, um Reporting- und Analysefunktionen zu unterstützen, während die Sicherheit und die Mandantenisolation erhalten bleiben.
