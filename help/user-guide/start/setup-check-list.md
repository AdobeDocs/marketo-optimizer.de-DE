---
title: Checkliste einrichten
description: Führen Sie die anfänglichen Einrichtungsaufgaben für Ihre Marketo Optimizer-Instanz aus, einschließlich der Konfiguration des Benutzerzugriffs und der Infrastruktur zur E-Mail-Zustellbarkeit.
TQID: 'https://experienceleague.adobe.com/XEPKIa88-L7mdPz1opKegY1pdEF4Qyls0nLVJBQSaJk'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 3cf5f37e-e87e-5179-812b-53ce05d7eebbid: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 249
ht-degree: 10%

---

# Checkliste einrichten

Führen Sie diese Aufgaben aus, um die Funktionalität in Ihrer bereitgestellten [!DNL Marketo Optimizer]-Instanz zu aktivieren.

## Benutzerzugriff aktivieren {#enable-user-access}

Wenn die Bereitstellung abgeschlossen und Sandboxes gebunden sind, konfigurieren Sie [!DNL Journey Optimizer B2B Edition] Zugriff für Ihr Team und Ihre Benutzer.

<table>
<thead>
<tr>
<th colspan="2">Aufgabe</th>
<th>Details und Anweisungen</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><strong>Produktzugriff und Berechtigungen für </strong> bereitstellen</td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox für Aufgabe"/></td>
<td>Erstellen eines Journey Optimizer B2B edition-Produktprofils in der Admin Console (nur einmaliges/erstmaliges Setup)</td>
<td><a href="./user-management.md#create-profile">Profil erstellen</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox für Aufgabe"/></td>
<td>Hinzufügen einer Benutzergruppe in der Admin Console</td>
<td><a href="./user-management.md#add-user-group">Benutzergruppe hinzufügen</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox für Aufgabe"/></td>
<td>Zuweisen des Produktprofils zur Benutzergruppe in der Admin Console</td>
<td><a href="./user-management.md#assign-profile">Produktprofil zuweisen</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox für Aufgabe"/></td>
<td>Hinzufügen von Benutzern zur Benutzergruppe in der Admin Console</td>
<td><a href="./user-management.md#add-users">Hinzufügen von Benutzenden</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox für Aufgabe"/></td>
<td>Bearbeiten von integrierten Rollen oder Erstellen einer benutzerdefinierten Rolle mit Produktberechtigungen</td>
<td><a href="./user-management.md#edit-role-permissions">Rollen bearbeiten</a> <br/> <a href="./user-management.md#create-a-custom-role">Benutzerdefinierte Rolle erstellen</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox für Aufgabe"/></td>
<td>Hinzufügen von Benutzenden oder Gruppen zu Rollen in Adobe Experience Platform</td>
<td><a href="./user-management.md#add-users-to-a-role">Benutzer hinzufügen</a> <br/><a href="./user-management.md#add-user-groups-to-a-role">Gruppen hinzufügen</a></td>
</tr>
</tbody>
</table>

## Zustellbarkeit von E-Mails {#email-deliverability}

Bevor Marketer E-Mails von Journey-Benutzern senden können, müssen Sie die Versandinfrastruktur für Ihr Unternehmen konfigurieren, einschließlich Subdomain-Zuweisung, E-Mail-Authentifizierung und Kanaleinstellungen.

<table>
<thead>
<tr>
<th colspan="2">Aufgabe</th>
<th>Details und Anweisungen</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><strong>Konfigurieren der E-Mail-Zustellbarkeit und Kanaleinstellungen</strong></td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox für Aufgabe"/></td>
<td>Delegieren einer Subdomain an Adobe (vollständig delegiert oder CNAME)</td>
<td><a href="./email-deliverability.md#delegate-fully-delegated">Vollständig delegiert</a> <br/> <a href="./email-deliverability.md#delegate-cname">CNAME</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox für Aufgabe"/></td>
<td>Konfigurieren von DMARC für die Subdomain</td>
<td><a href="./email-deliverability.md#configure-dmarc">Konfigurieren von DMARC</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox für Aufgabe"/></td>
<td>IP-Pool überprüfen und zuweisen</td>
<td><a href="./email-deliverability.md#review-ip-pool">IP-Pool überprüfen</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox für Aufgabe"/></td>
<td>Erstellen einer E-Mail-Kanal-Konfiguration</td>
<td><a href="../admin/email-channel-configuration.md#create-email-channel-configuration">Konfigurieren des E-Mail-Kanals</a></td>
</tr>
</tbody>
