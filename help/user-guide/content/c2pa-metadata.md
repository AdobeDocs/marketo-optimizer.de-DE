---
title: C2PA-Metadaten
description: Erfahren Sie, wie Adobe Marketo Optimizer C2PA-Metadaten automatisch auf Bilder anwendet, die mit generativer KI generiert wurden, und was dies für Ihre Inhalte bedeutet.
feature: Assets, Content
role: User
TQID: 'https://experienceleague.adobe.com/DI9vJhE4EsGI4g4X5wz5-kqTjHOZqs6cvqo6Fke-4HU'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: d4203578-d294-5145-b397-f26f4488a904
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 586
ht-degree: 0%

---

# C2PA-Metadaten

Marketing-Organisationen sind mehr denn je besorgt über Inhaltstransparenz, KI-Offenlegung und die Verhinderung von Manipulationen an Assets. Die Content Authenticity Initiative (CAI) von Adobe erstellt Tools, die dem technischen Standard [Coalition for Content Provenance and Authenticity](https://c2pa.org/specifications/specifications/1.1/specs/C2PA_Specification.html#_trust_model) (C2PA) entsprechen. _C2PA-_: sind verschlüsselte, manipulationssichere Informationen, die Betrachtern helfen können, die Herkunft von Inhalten zu verstehen und die Integrität von Marken-Assets sicherzustellen. Zu diesen Informationen gehören:

* Aussteller oder Unterzeichner — Informationen über die Entität oder das Unternehmen, die bzw. das die digitale Signatur zum Zertifizieren oder Signieren des Assets ausgestellt hat.
* Ausstellungsdatum - Das Datum, an dem die C2PA-Metadaten auf das Asset angewendet wurden.
* Kredit und Nutzung — Informationen über den Produzenten des Assets, einschließlich Name, Social-Media-Handles oder andere identitätsbezogene Informationen.
* Prozess - Aufzeichnungen aller Bearbeitungen oder Änderungen am Asset.
* Gerätedetails - Informationen zu der App oder dem Gerät, die bzw. das zum Erstellen oder Bearbeiten des Assets verwendet wird.
* Verwendetes KI-Tool — Wenn generative KI zum Erstellen des Assets verwendet wurde, kann der Name des verwendeten Modells einbezogen werden.
* Weitere relevante Informationen - Es sind auch zusätzliche Daten enthalten, um mehr Kontext über den Verlauf eines Assets anzubieten.

Umfassende Informationen zum Asset-Verlauf erhalten Sie mit dem Adobe Content Authenticity [Inspektions-Tool](https://contentauthenticity.adobe.com/inspect).

C2PA-Metadaten bleiben in der Bilddatei erhalten. Wenn ein Bild, das mit generativer KI generiert oder bearbeitet wurde, in [!DNL Adobe Marketo Optimizer] hochgeladen oder aus exportiert wird, bleiben seine C2PA-Metadaten erhalten.

Weitere Informationen zum automatischen Anhängen von C2PA-Metadaten an Adobe CX Enterprise-Anwendungen finden Sie unter [_Generative KI-Inhaltstransparenz_](https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/overview/content-transparency){target="_blank"} im Handbuch zu KI in CX Enterprise .

>[!NOTE]
>
>Bei einigen Methoden zum Importieren von Bildern in Ihre Inhalte, z. B. beim Extrahieren eines Bildes aus einer PDF oder aus einer eingebetteten (base64) Quelle, bleiben die ursprünglichen C2PA-Metadaten möglicherweise nicht erhalten. In diesen Fällen können C2PA-Metadaten nicht aus der Quelle gelesen werden, und es wird keine für das Ergebnis erstellt.

>[!BEGINSHADEBOX]

## Persistenz von C2PA-Metadaten über Kanäle {#channels}

Wenn Sie Bilder in Ihre E-Mail- oder WhatsApp-Nachrichten einfügen, werden die C2PA-Metadaten für die bereitgestellten Bilder ebenfalls beibehalten:

* **E-**: Wenn Sie die Aktion _E-Mail senden_ Journey verwenden, fügen Sie das Bild aus der _Assets_ Bibliothek zu Ihrem E-Mail-Inhalt hinzu. Wenn die E-Mail zugestellt wird, kann der Empfänger das Bild aus der Nachricht herunterladen und die C2PA-Metadaten sind intakt.
* **WhatsApp** - Fügen Sie das Bild zu Ihrer WhatsApp-Nachrichtenvorlage in Ihrem Meta-Geschäftskonto hinzu. Sie können sie direkt von Ihrem System hinzufügen oder eine Bilddatei aus der Bibliothek _Assets_ herunterladen. Verwenden Sie die Vorlage für eine Aktion _WhatsApp senden_ Journey. Wenn die WhatsApp-Nachricht zugestellt wird, kann der Empfänger das Bild aus der Nachricht herunterladen und die C2PA-Metadaten sind intakt.

>[!ENDSHADEBOX]

## Bildgenerierung {#generate}

>[!INFO]
>
>Im Bereich der generativen KI-Transparenz entstehen neue Gesetze, und Adobe arbeitet daran, die geltenden Anforderungen in allen Rechtssystemen zu erfüllen. C2PA-Metadaten sind das Herkunftstool, das Adobe verwendet, um die Anforderungen dieser Gesetze zu erfüllen.

Wenn Sie generative KI zum Erstellen eines Bildes für Ihren E-Mail-Inhalt in [!DNL Marketo Optimizer] verwenden, werden C2PA-Metadaten automatisch an das generierte Bild angehängt, sodass keine Aktion Ihrerseits erforderlich ist. Generative KI-Tools erstellen ein kombiniertes C2PA-Metadatenelement für Varianten von Bildern mit vorhandenen Metadaten, einschließlich der Originalquelle.

>[!NOTE]
>
>[!DNL Marketo Optimizer] unterstützt derzeit keine manuellen Bildbearbeitungsaktionen. C2PA-Metadaten-Workflows für diese Aktionen sind derzeit nicht anwendbar.
