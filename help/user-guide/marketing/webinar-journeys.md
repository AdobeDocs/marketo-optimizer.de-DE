---
title: Webinar-Promotion und Follow-up-Journey
description: Erstellen Sie Werbe-, Bereitstellungs- und Nachbearbeitungs-Journey rund um ein Webinar in Marketo Optimizer und personalisieren Sie den Inhalt mit Webinar-Token.
keywords: 
role: User
feature: Person Journeys
TQID: 'https://experienceleague.adobe.com/9NJrT-Y66XXF1-mWDO80WpymCB6ujrkjkR87MhKuiB8'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2:
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 823
ht-degree: 0%

---


# Webinar-Promotion und Follow-up-Journey

Nachdem Sie einem Programm ein Webinar hinzugefügt haben, erstellen Sie in demselben Programm ein oder mehrere [Journey](./person-journeys.md), um Personen einzuladen, sie daran zu erinnern, die Sitzung zu halten und danach weitere Schritte durchzuführen.

>[!NOTE]
>
>Auf dieser Seite wird beschrieben, wie man diese Journey von Hand baut. Wenn Sie möchten, dass Ihr Kollege dieselben Journey aus einer Vorlage erstellt, finden Sie weitere Informationen unter [Erstellen von Webinaren mit Kollege](../agents/webinar-creation.md).

## Erstellen einer Promotion-Journey {#build-promotion-journey}

Eine typische Promotion-Journey lädt Personen ein, verfolgt ihre Registrierung und erinnert sie daran, wenn das Webinar näher rückt.

1. [Erstellen Sie die Personen-Journey](./person-journeys.md#create-a-person-journey).

1. [Wählen Sie eine Zielgruppe für die Journey aus](./person-audience-node.md).

1. Fügen Sie einen **[!UICONTROL E-Mail senden]**-Knoten mit einer Einladungs-E-Mail hinzu.

   Verwenden Sie Webinar-Token wie _Titel_ und _Startdatum/-uhrzeit_ im Inhalt und verknüpfen Sie sie mit der Registrierungsseite für das Webinar.

1. Fügen Sie einen Knoten **[!UICONTROL Aktion durchführen]** hinzu, wählen Sie die Aktion **[!UICONTROL Status des Webinar-Mitglieds ändern]** aus, wählen Sie das Webinar aus und legen Sie den Status auf _Eingeladen_ fest.

   Platzieren Sie sie unmittelbar nach dem Knoten **[!UICONTROL Einladung senden]**.

   >[!NOTE]
   >
   >Normalerweise legen Sie &quot;_&quot;_ &quot;_&quot;_ einer Promotion-Journey fest. [!DNL Adobe Connect] legt normalerweise _Attended_, _No-Show_ und _Attended on Demand_ automatisch fest. Dieselbe Aktion kann diese späteren Statuswerte bei Bedarf von einer Journey überschreiben, jedoch nur vorwärts, entsprechend der linearen Progression, die unter „Webinar [_Status“ beschrieben_](webinars-overview.md#webinar-status).

1. Hosten Sie das Registrierungsformular auf einer [Landingpage](../content/landing-pages.md).

1. Fügen Sie einen Knoten **[!UICONTROL Aktion durchführen]** hinzu, wählen Sie die Aktion **[!UICONTROL Status des Webinar-Mitglieds ändern]** aus, wählen Sie das Webinar aus und setzen Sie den Status auf _Registriert_ (ausgelöst durch die Formularübermittlung).

   Beim Verschieben einer Person nach _Registriert_ werden zwei Dinge automatisch ausgeführt:

   * [!DNL Adobe Connect] generiert die individuelle Join-URL dieser Person.
   * Wenn Sie eine konfiguriert haben, sendet sie die Bestätigungs-E-Mail mit dem Token _Join-URL_ .

1. Erstellen Sie eine Erinnerungskadenz mit **[!UICONTROL Warten]**-Knoten, die relativ zum Webinar-Token _Startdatum/Uhrzeit_ sind.

   Legen Sie sie beispielsweise auf eine Woche davor, einen Tag davor und eine Stunde davor fest.

1. Fügen Sie einen **[!UICONTROL Warten]**-Knoten zum Webinar-Token _End DateTime_ hinzu, sodass der Journey angehalten wird, bis die Live-Sitzung beendet ist.

   Fahren Sie [Erstellen einer Post-Webinar-Journey](#build-post-webinar-journey) von hier fort.

   >[!NOTE]
   >
   >Änderungen des Webinar-Status sind derzeit nicht als Trigger **[!UICONTROL Auf ein Ereignis]**) verfügbar. Verwenden Sie stattdessen einen zeitgesteuerten **[!UICONTROL Warten]**-Knoten gefolgt von einem **[!UICONTROL Split-Pfade]**-Knoten im Webinar-Status, wie unten gezeigt, anstatt auf die Statusänderung selbst zu warten.

## E-Mails personalisieren

Webinar-Token werden im E-Mail-Inhalt gerendert: Betreff, Textkörper, Preheader und Absender. Die vollständige Liste finden [&#x200B; unter &#x200B;](webinars-overview.md#webinar-tokens)Webinar-Token“.

>[!NOTE]
>
>Webinar-Token sind derzeit weder auf der Registrierungs-Landingpage noch in Formularen verfügbar. Personalisieren Sie diese stattdessen mit Standard-Programm-Token und reservieren Sie eine Webinar-spezifische Personalisierung (wie die Join-URL und die Aufnahme-URL) für E-Mails.

>[!IMPORTANT]
>
>Das Token **_Beitritt zur URL_** kann nur für Personen aufgelöst werden, deren Webinar-Status _Registriert_ oder höher ist. Das **_Aufzeichnungs-URL_**-Token wird erst aufgelöst, nachdem die Aufzeichnung veröffentlicht wurde. Beide werden vorab auf einen leeren Wert und nicht auf einen Fehler aufgelöst. Überprüfen Sie daher vor der Veröffentlichung, ob Ihre E-Mails in beiden Fällen akzeptabel gerendert werden.

## Durchführen des Webinars {#deliver-webinar}

Zum geplanten Zeitpunkt wird das Webinar in [!DNL Adobe Connect] ausgeführt:

* Moderatoren und Co-Moderatoren nehmen über ihren individuellen Link am Webinar **Team** teil.
* Teilnehmer treten mit ihrem persönlichen Token **Teilnehmende URL** bei.
* [!DNL Adobe Connect] erfasst Aktivitäten während der Sitzung (Fragen, Umfrageantworten, Link-Klicks, Asset-Downloads und Handzeichen) und sendet sie zurück an [!DNL Marketo Optimizer] als [Webinar-Aktivitäten](webinars-overview.md#webinar-activities), die für jede Hör-Journey verfügbar sind.

Wenn das Webinar auf **Simuliert Live** eingestellt ist, werden aufgezeichnete Inhalte automatisch zum geplanten Zeitpunkt wiedergegeben, während die Moderatoren über Chat, Umfragen und Fragen und Antworten live interagieren.

## Erstellen einer Journey nach dem Webinar {#build-post-webinar-journey}

Nach Abschluss der Live-Sitzung setzt [!DNL Adobe Connect] den Webinar-Status jeder Person auf &quot;_&quot;_ „Nicht _&quot;_. Wenn der Journey **[!UICONTROL Warten]**-Knoten freigegeben wird, verzweigen Sie unter Verwendung dieses Status mit einem **[!UICONTROL Split-Pfade]**-Knoten.

1. Fügen Sie einen Knoten **[!UICONTROL Pfade aufteilen]** mit einer Bedingung im Webinar-Status hinzu, z. B _„Hat an Webinar teilgenommen_.

1. Senden Sie auf _Pfad_ Teilgenommen“ eine Dankesnachricht.

   Senden Sie beispielsweise eine Wiederholung und Ressourcen-Follow-up. Verwenden Sie dann einen **[!UICONTROL Warte]**-Knoten und eine call-to-action-E-Mail für den nächsten Schritt.

1. Auf dem _No-Show_-Pfad senden Sie eine E _Mail, in der wir Sie_ haben.

   Laden Sie sie im E-Mail-Inhalt ein, sich die Aufzeichnung anzusehen. Verwenden Sie dann einen **[!UICONTROL Warte]**-Knoten und eine Folgenachricht, in der die wichtigsten Erkenntnisse zusammengefasst sind.

1. Personalisieren Sie beide Pfade mithilfe anderer Webinar-Aktivitäten weiter.

   Verzweigen oder personalisieren Sie beispielsweise anhand von _Antwortet auf eine Abfrage_ mit einer bestimmten Antwort.

1. Verwenden Sie das **_Aufnahme-URL_**-Token in jedem Pfad, nachdem es aufgelöst werden kann, damit Benutzer es bei Bedarf ansehen können.

   **_On-Demand-Interaktion_** (Dauer der Uhr, Klicks auf den Wiedergabe-Link und Downloads) wird während derselben Webinar-Aktivitäten aufgenommen, die mit einem Modus von _On-Demand“_ sind. Im Gegensatz zu diesen Aktivitäten verschiebt die On-Demand-Anzeige auch eine _No-Show_-Person in den _Attended on Demand_-Webinar-Status. Daher kann ein &quot;_-Show_-Pfad die Personen erreichen, die die Aufnahme später ansehen. Teilen Sie den Webinar-Status weiter auf oder überprüfen Sie ihn nach einer Verzögerung erneut, wenn Sie eine andere Behandlung für Personen wünschen, die On-Demand ansehen.
