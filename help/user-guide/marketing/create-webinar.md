---
title: Erstellen und Entwerfen eines Webinars
description: Fügen Sie einem Programm ein Webinar-Asset hinzu, entwerfen Sie es in  [!DNL Adobe Connect], fügen Sie Co-Hosts und Moderatoren hinzu, führen Sie eine Testsitzung aus und bearbeiten Sie ein Live-Webinar in  [!DNL Marketo Optimizer].
keywords: 
role: User
feature: Channels
TQID: 'https://experienceleague.adobe.com/fFvlOnp8hDF1RNOyohPWkc1whSG3T3deNrJ3RnEDzlo'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2:
  - id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4
  - id: d4203578-d294-5145-b397-f26f4488a904
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 680
ht-degree: 0%

---


# Erstellen und Entwerfen eines Webinars

Fügen Sie einem Programm ein Webinar hinzu, entwerfen Sie die Registrierung und das Raumerlebnis und personalisieren Sie es mit Co-Hosts und Moderatoren aus [!DNL Marketo Optimizer]. Bevor Sie beginnen, lesen Sie [Übersicht zu interaktiven Webinaren](webinars-overview.md), um die Konzepte hinter den Webinar-Status, Token und Rollen zu erkunden und zu bestätigen, dass Sie die Rolle **Erstellen und Verwalten von Webinaren** haben.

## Hinzufügen eines Webinars zu einem Programm

1. Suchen Sie zuerst das Programm in der _[!UICONTROL Programme]_-Baumstruktur oder [Programm erstellen](./programs.md#create-program).

1. Klicken Sie auf _Mehr Menü_ ( **…** ) neben dem Programmnamen und wählen Sie **[!UICONTROL Webinar erstellen]**.

1. Geben Sie im Dialogfeld die wichtigsten Webinar-Details ein:

   * **Titel** und **Beschreibung**.
   * **Zeitplan** - Startdatum und -zeit, Zeitzone und Dauer.
   * **Maximale Zielgruppe** - Die Webinar-Lizenzkapazität, die für diese Sitzung verwendet werden soll.

   ![Das Dialogfeld Webinar planen mit Feldern für das übergeordnete Programm, Name, Dauer, Zeitzone, Startzeit und maximale Zielgruppe sowie den Schaltflächen Abbrechen und Erstellen.](assets/webinar-create-schedule-dialog.png){width="500" zoomable="yes"}

   >[!NOTE]
   >
   >Die Optionen für Versand, Audio und Video, Einzelsitzung oder wiederkehrend, sind derzeit nicht konfigurierbar. Jedes Webinar besteht aus einer einzigen, videoaktivierten Sitzung.

1. Fügen Sie **Co-Hosts** und **Presenter** hinzu.

   >[!NOTE]
   >
   >In der aktuellen Version fügen Sie alle Personen als externen Kontakt nach Name und E-Mail hinzu, unabhängig davon, ob sie über ein rollenberechtigtes Adobe SSO-Konto verfügen oder nicht.<!-- See [Permissions](./webinars-overview.md#permissions) for what each role governs. --> Die vollständigen Schritte finden Sie unter [_Hinzufügen von Co-Hosts und Moderatoren_](#add-co-hosts-and-presenters).

1. (Optional) Passen Sie die Raumvorlage, das Branding und das Layout an.

   Diese Optionen werden in [!DNL Adobe Connect] verwaltet und können später von der Entwurfsoberfläche aus weiter verfeinert werden. Siehe [Webinar entwerfen](#design-the-webinar).

1. Klicken Sie auf **[!UICONTROL Speichern]**.

   Durch Speichern wird das Webinar im Programm registriert und seine Token, Attribute und Aktivitäten werden für jede Journey und jedes Asset in diesem Programm verfügbar gemacht.

>[!NOTE]
>
>Die Erstellung von Webinaren entspricht _interaktiven Webinaren_ in [!DNL Marketo Engage]. Daher sind die Felder vertraut, wenn Sie dies über diese Anwendung durchgeführt haben.

## Webinar entwerfen {#design-the-webinar}

Um die [!DNL Adobe Connect] Design-Oberfläche zu öffnen, die direkt in [!DNL Marketo Optimizer] eingebettet ist, wo Sie den Raum, die Registrierungsseite und die Layouts konfigurieren, verwenden Sie _[!UICONTROL Webinar entwerfen]_.

1. Klicken Sie auf der Webinar-Seite auf **Webinar erstellen**.

1. Wählen Sie einen **Versandmodus**:

   &#x200B;- **Live** - Moderatoren hosten die Sitzung in Echtzeit.
   &#x200B;- **Simulierte Live** - Aufgezeichnete Inhalte werden zum geplanten Zeitpunkt neben Live-Chat, Umfragen und Fragen und Antworten wiedergegeben.

1. Wählen Sie einen **Webinar-Raum**.

   Erstellen Sie einen neuen Raum oder verwenden Sie einen vorhandenen.

1. Wählen Sie **Vorlage**, **Sprache** und **Design** aus und sehen Sie sich das Layout an.

1. Fügen Sie Pods hinzu und ordnen Sie sie nach Bedarf an.

   Zu den verfügbaren Pods gehören Freigabe, Notizen, Video, Chat, Teilnehmerliste, Dateien, Weblinks, Umfragen, Fragen und Antworten sowie Umfragen.

1. Betreten Sie den Raum, um das Erlebnis zu überprüfen, und verlassen Sie ihn, wenn Sie fertig sind.

1. Speichern Sie Ihre Änderungen.

   Eine Bestätigung wird angezeigt, um anzugeben, dass das Webinar erfolgreich gestaltet wurde.

>[!TIP]
>
>Gestalten Sie das Webinar, bevor Sie Co-Moderatoren und Moderatoren hinzufügen, sodass deren Zugriff und Steuerung auf den fertigen Raum angewendet werden.

Die Raumanpassung wie Logo, Farben und virtuelle Hintergründe wird direkt in [!DNL Adobe Connect] vorgenommen.

## Co-Hosts und Moderatoren hinzufügen {#add-co-hosts-and-presenters}

1. Rufen Sie auf der Webinar-Seite den Abschnitt **Webinar-Team** auf.

1. Klicken Sie **Co-Host hinzufügen** oder **Moderator hinzufügen**.

1. Geben Sie im Dialogfeld den Vornamen **[!UICONTROL Person,]**&#x200B;**[!UICONTROL Nachname]** und **[!UICONTROL E-Mail]** ein und klicken Sie dann auf **[!UICONTROL Hinzufügen]**.

   >[!NOTE]
   >
   >In der aktuellen Version werden alle auf die gleiche Weise hinzugefügt, nach Name und E-Mail, unabhängig davon, ob sie über ein Adobe SSO-Konto verfügen oder nicht. Unter [Berechtigungen](webinars-overview.md#permissions) finden Sie Informationen dazu, was die Rollen **Webinar-Co-Host** und **Webinar-** steuern, sobald jemand hinzugefügt wird.

   Nachdem die Person hinzugefügt wurde, wird eine Bestätigung angezeigt, die im Abschnitt „Webinar **Team“ unter &quot;**&quot; oder **Referenten** aufgeführt wird.

## Testen des Webinars {#test-the-webinar}

Führen Sie vor der Weiterleitung des Webinars eine Testsitzung durch, um zu bestätigen, dass Raum, Pods und Präsentator wie erwartet auf alle Funktionen zugreifen.

>[!NOTE]
>
>Der Testmodus wirkt sich nicht auf den Teilnehmerstatus einer Person aus. Sie können einen Test so oft ausführen, wie Sie benötigen, ohne jemanden zu registrieren oder einzuladen.

## Live-Webinar bearbeiten {#edit-a-live-webinar}

Nach der Registrierung können Sie ein Webinar bearbeiten. Gehen Sie dabei jedoch mit Vorsicht vor:

&#x200B;- Durch Bearbeiten des Zeitplans können Trigger Benachrichtigungen an bereits registrierte Personen aktualisieren. Die Möglichkeit, geplante Webinare zu bearbeiten, ist konfigurierbar.
&#x200B;- Felder, auf die von Token in Live-E-Mails verwiesen wird, müssen explizit zum Entfernen bestätigt werden, da dadurch bereits für den Versand geplante Inhalte beschädigt werden.
