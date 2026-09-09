---
title: Ziele
description: Erfahren Sie mehr über die erforderlichen Berechtigungen, unterstützte Ziele und wie Sie ein Ziel in Marketo Optimizer verbinden können, um statische Personenlisten für Werbe- und Social-Media-Plattformen zu aktivieren.
TQID: 'https://experienceleague.adobe.com/u5sWVDR0JaiX-YvlQ23l7mqoI9G95xS-uiKcqANwsnc'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 3cf5f37e-e87e-5179-812b-53ce05d7eebb
topic_v2: id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 643
ht-degree: 8%

---

# Ziele

Ziele sind vorgefertigte Integrationen, mit denen Sie [statische Personenlisten](./people-lists.md#static-lists) von [!DNL Marketo Optimizer] an externe Werbe- oder Social-Media-Plattformen senden können, z. B. eine LinkedIn-Kampagnenzielgruppe, eine Google Customer Match-Zielgruppe oder eine benutzerdefinierte Facebook-Zielgruppe. Durch die Aktivierung einer statischen Liste für ein Ziel wird die Mitgliedschaft synchron gehalten: Wenn Personen zur Liste hinzugefügt oder daraus entfernt werden, werden sie entsprechend zur Zielgruppe und entsprechend auch zu jeder Kampagne, die von der Zielgruppe bedient wird, hinzugefügt oder daraus entfernt.

Es gibt zwei Möglichkeiten, Personen für ein verbundenes Ziel zu aktivieren:

* **Aus einer statischen Liste** - Aktivieren Sie eine vorhandene statische Liste direkt auf der Registerkarte **_[!UICONTROL Personenlisten]_**. Siehe [Für ein Ziel aktivieren](./people-lists.md#static-list-activate).
* **Von einer Personen-Journey** - Fügen Sie eine Aktion **_[!UICONTROL Für Ziel aktivieren]_** zu einem Journey-Pfad hinzu, damit jeder, der diesen Knoten erreicht, zu einer Liste hinzugefügt und an das Ziel gesendet wird. Siehe [_Aktionsknoten hinzufügen_](../marketing/action-nodes.md#add-an-action-node).

>[!BEGINSHADEBOX]

## Erforderliche Berechtigungen {#required-permissions}

Für eine vollständige Zielfunktion müssen die folgenden [!DNL Adobe Experience Platform] aktiviert sein.

| Kategorie | Berechtigung | Erforderlich |
|--- |--- |--- |
| Sandboxes | Sandbox-_(standardmäßig aktiviert)_ | Ja |
| Dashboards | Standard-Dashboards anzeigen | Ja |
| Dashboards | Standard-Dashboards verwalten | Ja |
| Ziele | Anzeigen von Zielen | Ja |
| Ziele | Verwalten von Zielen | Ja |
| Ziele | Aktivieren von Zielen | Ja |
| Ziele | Segment ohne Zuordnung aktivieren | Ja |
| Ziele | Verwalten und Aktivieren des Datensatzziels | Ja |
| Ziele | Ziel-Authoring | Ja |
| Data Governance | Anzeigen von Datennutzungsrichtlinien | Ja |
| Data Governance | Verwalten von Datennutzungsrichtlinien | Ja |
| Datenaufnahme | Anzeigen von Quellen | Ja |
| Datenaufnahme | Verwalten von Quellen | Ja |
| Profilverwaltung | Profileinstellungen anzeigen | Ja |
| Profilverwaltung | Profileinstellungen verwalten | Ja |

>[!ENDSHADEBOX]

## Unterstützte Ziele {#supported-destinations}

Bevor Sie eine statische Liste aktivieren können, muss im Zielkatalog ein Ziel vorhanden sein. Erweitern Sie in der linken Navigation **[!UICONTROL Verbindungen]** und wählen Sie **[!UICONTROL Ziele]** aus. [!DNL Marketo Optimizer] unterstützt derzeit die folgenden Ziele:

* **[!UICONTROL Google Customer Match]** (Advertising)
* **[!UICONTROL Benutzerdefinierte Facebook-Zielgruppe]** (Social)
* **[!UICONTROL LinkedIn Matched Audience]** (Social)

![Zugriff auf die verfügbaren Connector-Typen](./assets/destinations-catalog.png){width="800" zoomable="yes"}

>[!NOTE]
>
>Dieser Katalog ist nicht der vollständige [!DNL Adobe Experience Platform]. Wenn Sie direkt über [!DNL Experience Platform] auf Ziele zugreifen, sehen Sie einen größeren Katalog, aber nur diese Ziele sind derzeit für die Aktivierung in [!DNL Marketo Optimizer] verfügbar. Weitere Ziele sind für zukünftige Versionen geplant.

## Ziel einrichten {#set-up-destination}

Jede unterstützte Zielkarte zeigt **[!UICONTROL Neues Ziel konfigurieren]**. Die Konfiguration eines Ziels ist eine Voraussetzung für die Aktivierung.

1. Klicken Sie auf der Connector-Karte auf **[!UICONTROL Neues Ziel konfigurieren]**.

1. Wählen Sie **[!UICONTROL Vorhandenes Konto]** oder **[!UICONTROL Neues]** aus und geben Sie die Kontodetails ein, z. B. den Kontonamen und die Beschreibung.

   ![Ein neues Zielkonto verbinden](./assets/destinations-configure-new.png){width="500"}

1. Klicken Sie **[!UICONTROL Mit Ziel verbinden]**.

   Mit einem OAuth-Fluss können Sie sich beim entsprechenden Konto anmelden: LinkedIn, Google oder Facebook.

   >[!IMPORTANT]
   >
   >Geben Sie an dieser **nicht** &quot;_[!UICONTROL &quot;]_. Es wird nur die Verbindung benötigt.

1. Schließen Sie die erforderliche Feldzuordnung zwischen Personenattributen und den für das Ziel erforderlichen Feldern ab.

1. Überprüfen Sie die Einstellungen für Data Governance und Marketing-Aktionen und klicken Sie dann auf **[!UICONTROL Speichern]**.

Die vollständigen Einrichtungsschritte finden Sie unter [Erstellen einer neuen Zielverbindung](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/connect-destination){target="_blank"} in der [!DNL Experience Platform].

Nach der Konfiguration kann das Ziel überall dort aktiviert werden, wo Sie ein Ziel in [!DNL Marketo Optimizer] auswählen können.

## Aktivierung und Synchronisierung {#activation-sync}

Die Aktivierung wird durch die Zugehörigkeit zu einer statischen Liste gesteuert, wobei eine bidirektionale Synchronisierung zwischen der Liste und der Zielgruppe erfolgt:

* Wenn Sie eine Person zur statischen Liste hinzufügen, wird sie innerhalb von 24 Stunden zum Ziel aktiviert, indem Sie sie zur Ziel-Audience und anschließend zu jeder Kampagne hinzufügen, die von der Audience gefüttert wird.
* Wenn Sie eine Person aus der statischen Liste entfernen, wird sie vom Ziel deaktiviert - sie wird aus der Zielgruppe und aus jeder verbundenen Kampagne entfernt.
* Dieselbe Liste kann für mehrere Ziele gleichzeitig aktiviert werden. Die Mitgliedschaft synchronisiert alle Ziele.

>[!TIP]
>
>Um eine LinkedIn-Kampagne für ein Segment auszuführen, aktivieren Sie die statische Liste dieser Personen für Ihr Ziel „LinkedIn Matched Audience“. Alle Personen in der Liste werden der entsprechenden Zielgruppe in LinkedIn hinzugefügt, wo eine Kampagne sie ansprechen kann. Die Zielgruppe bleibt bei Änderungen der Liste automatisch auf dem neuesten Stand.
