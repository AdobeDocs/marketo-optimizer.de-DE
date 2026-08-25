---
title: E-Mail-Kanalkonfiguration
description: Erstellen und verwalten Sie E-Mail-Kanalkonfigurationen, die Absenderidentität, Subdomain, IP-Pool, E-Mail-Typ und URL-Tracking für Marketo Optimizer verbinden.
feature: Administration
role: Admin
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 0%

---

# E-Mail-Kanalkonfiguration

Eine Kanalkonfiguration ist das zentrale Objekt, das Ihre Absenderidentität, Subdomain, Ihren IP-Pool und Ihre Tracking-Einstellungen miteinander verknüpft. E-Mail-Aktionen in Journey verweisen auf eine Kanalkonfiguration, um zu erfahren, wie die Nachricht gesendet werden soll. Bevor Sie eine Konfiguration erstellen, schließen Sie [Einrichtung von Subdomain-Zuweisung und IP-Pool](../start/email-deliverability.md) ab.

* **channel:** email.
* **E-Mail-Typ** Marketing oder Transaktion. Diese Einstellung bestimmt, ob Unterdrückungsregeln angewendet werden (Marketing wendet sie an; Transaktionsnachrichten umgehen standardmäßig die Unterdrückung von Spam-Beschwerden für rechtmäßige Transaktionsnachrichten).
* **Kopfzeilenparameter:** von Name, von E-Mail, Antwort-an-Name, Antwort-an-E-Mail, Fehler-E-Mail.
* **Subdomain:** Die delegierte Subdomain, die zum Senden verwendet wird. Die Absender-E-Mail muss diese Subdomain verwenden.
* **IP-Pool:** Der IP-Pool, der zum Versand der Nachricht verwendet wird.
* **URL-Tracking** Aktivieren oder Deaktivieren des Klick- und Öffnungs-Trackings; Konfigurieren der Tracking-Domain.
* **Tags:** Tags für Organisation und Suche.

## Erstellen einer E-Mail-Kanal-Konfiguration {#create-email-channel-configuration}

>[!PREREQUISITES]
>
>* Mindestens eine [Subdomain](../start/email-deliverability.md#subdomain-delegation) muss delegiert und aktiv sein.
>* Mindestens ein [IP-Pool](../start/email-deliverability.md#ip-pools) muss Ihrer Organisation zugewiesen sein.
>* Sie benötigen die Administratorrolle.
>* Überprüfen Sie [aktuelle Einschränkungen](../start/email-deliverability.md#limitations) - Dedizierte IP-Pools sind bei Beta nicht verfügbar.

1. Erweitern Sie in der linken [!DNL Adobe Marketo Optimizer]-Navigation **[!UICONTROL Administration]** und wählen Sie **[!UICONTROL Kanäle]** aus.
1. Erweitern Sie im Bedienfeld **[!UICONTROL E-Mail-Einstellungen]** und wählen Sie **[!UICONTROL Kanalkonfigurationen]** aus.
1. Klicken Sie **[!UICONTROL Kanalkonfiguration erstellen]**.
1. Geben Sie einen Namen (z. B. _Contoso B2B Marketing — Nordamerika_) und eine optionale Beschreibung ein.
1. Wählen Sie den Kanal **[!UICONTROL E-Mail]** aus.
1. (Optional) Wählen Sie Tags aus, um die Konfiguration zu kategorisieren.
1. Wählen Sie im Abschnitt **[!UICONTROL E]** Mail-Typ“ die Option „Marketing“ oder „Transaktion“.
1. Wählen Sie im **[!UICONTROL Subdomain]** eine zuvor delegierte Subdomain aus.
1. Wählen Sie **[!UICONTROL Abschnitt „IP]** Pool“ einen aktiven IP-Pool aus.

   Bei Beta ist nur der freigegebene IP-Pool verfügbar. Sie können den Mauszeiger über die IPs bewegen, um PTR-Einträge anzuzeigen.

1. Konfigurieren Sie die **[!UICONTROL Kopfzeilenparameter]**:
   * Absendername (z. B. „Contoso Marketing„)
   * Aus E-Mail - Muss die ausgewählte Subdomain verwenden (z. B. `marketing@mail.contoso.com`).
   * Name der Antwortadresse und E-Mail-Adresse der Antwortadresse — standardmäßig _Von_, wenn leer.
   * Fehler-E-Mail - Adresse, die Nicht-Versand-Benachrichtigungen erhält.
1. Aktivieren Sie **[!UICONTROL URL-Tracking]** und wählen Sie die Tracking-Domain aus.
1. Klicken Sie auf **[!UICONTROL Senden]**.

>[!NOTE]
>
>Nach dem Senden führt das System die Validierung durch: Subdomain-Status, MX-Eintrag, SPF/DKIM/DMARC-Ausrichtung, IP-Pool-Bereitschaft, FBL-Registrierung. Die Konfiguration durchläuft die → „Entwurf → Verarbeitung aktiv“.

>[!NOTE]
>
>Wenn die Validierung fehlschlägt, wechselt die Konfiguration in den Status **[!UICONTROL Fehlgeschlagen]**. Öffnen Sie die Konfiguration, um die Fehlerursache anzuzeigen. Häufige Ursachen sind Fehler bei der Validierung von MX-Datensätzen, IPs im Pool, die nicht mit der Konfiguration übereinstimmen, oder eine Fehlausrichtung von DMARC. Auflösen und erneut übermitteln.

## Bearbeiten oder Löschen einer Kanalkonfiguration {#edit-channel-configuration}

Sie können Kanalkonfigurationen nach der Erstellung bearbeiten, jedoch mit einer wichtigen Einschränkung: **Kanal kann nicht geändert werden.** Eine Konfiguration ist an ihren Kanal gebunden.

Wenn Sie eine Konfiguration bearbeiten, die verwendet wird:

* **Für veröffentlichte Journey**: Die Änderung wird bei der nächsten Wiederholung oder bei der nächsten Ausführung angewendet. Die Ausführungen während des Fluges werden mit den vorherigen Einstellungen fortgesetzt.
* **Bei Transaktions- oder Echtzeitnachrichten:** Änderungen werden innerhalb von etwa fünf Minuten weitergegeben.

>[!WARNING]
>
>Das Löschen einer Kanalkonfiguration ist dauerhaft. Eine Konfiguration, auf die eine aktive Journey verweist, kann nicht gelöscht werden. Entfernen Sie zuerst alle E-Mail-Aktionen oder weisen Sie sie neu zu.

Um eine Konfiguration zu löschen, entfernen oder aktualisieren Sie zunächst jede E-Mail-Aktion, die auf sie verweist, in [E-Mails an Journey hinzufügen](../marketing/email-channel.md#define-email-properties). [!DNL Marketo Optimizer] löscht keine Konfiguration, die derzeit von einer aktiven Journey verwendet wird.

## Konfigurationen mit mehreren Kanälen {#multiple-channel-configurations}

Die meisten B2B-Unternehmen verwenden mehrere Kanalkonfigurationen, um Marken, Regionen oder Versandtypen zu trennen. Häufige Muster:

* Eine separate Marketing-Konfiguration pro Geschäftseinheit (z. B. *BU-A Marketing*, *BU-B Marketing*).
* Eine dedizierte Transaktionskonfiguration mit E-Mail-Typ = Transaktionsnachricht für Produkt- oder Vertragsbenachrichtigungen.
* Regionsspezifische Konfigurationen mithilfe regionsspezifischer Subdomains (z. B. `mail.eu.contoso.com`, `mail.us.contoso.com`) zur Abstimmung mit regionalen ISPs und zur Einhaltung der Vorschriften.

>[!TIP]
>
>Benennen Sie Ihre Konfigurationen mit einer klaren, strukturierten Konvention - z. B.: *[Marke] - [Region] - [Typ]*. Dies wird wichtig, sobald Sie ein Dutzend oder mehr Konfigurationen haben.
