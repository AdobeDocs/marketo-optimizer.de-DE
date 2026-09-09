---
title: Programme
description: Erfahren Sie, wie Sie mit Programmen Ihre Marketing-Maßnahmen organisieren und Marketingmaterial und Journey von einem Ort aus verwalten können.
TQID: 'https://experienceleague.adobe.com/RljL2N9P22AbWB6jSSaQ-iKlpTSz8d3cGNrIKatMH4o'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 46e599c6-e20f-5f67-9824-93415016f66bid: 64b90904-e4f0-5c1b-a871-8c6a40b204a1id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094id: ff2b9b37-92e0-45fc-b853-379d44c08c89
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 804
ht-degree: 1%

---

# Programme

Programme sind so konzipiert, dass sie Ihren Marketingmaterialien und Journey einen gemeinsamen Kontext geben, sodass Sie alle Aspekte einer Marketingkampagne von einem Ort aus verwalten können. Verwenden Sie Programmattribute zur Beschreibung Ihres Programms und den Filter _Mitglied des Programms_ um Zielgruppen basierend auf Programmmitgliedschaft, Mitgliedsstatus und Erfolg zu segmentieren. Auf der Registerkarte Token können Sie sowohl lokale _Meine Token_ als auch Token verwalten, die in Ihrer Ordnerstruktur übernommen werden.

## Zugreifen auf Programme {#access-programs}

Jedes Programm befindet sich in der _[!UICONTROL Marketing]_-Ordnerstruktur und kann Journey, Listen und andere Ressourcen enthalten, um Ihre Marketing-Maßnahmen zu organisieren.

1. Erweitern Sie in der linken Navigation **[!UICONTROL Marketing-Verwaltung]**.

1. Wählen Sie rechts in der **[!UICONTROL Marketing]**-Ressourcenliste **[!UICONTROL Programme]** aus.

1. Verwenden Sie die _Suche_ und _Filter_, um Elemente innerhalb der Struktur zu finden.

1. Wählen Sie ein Programm oder einen Ordner in der Struktur aus, um seine Details im mittleren Arbeitsbereich zu öffnen.

   ![Ausgewähltes Programm in der Programmstruktur](./assets/programs-tree-select.png){width="800" zoomable="yes"}

   Wählen Sie eine der Registerkarten aus, um auf Programm- oder Ordnerdetails oder -inhalte zuzugreifen.

## Erstellen eines Programms {#create-program}

>[!IMPORTANT]
>
>Jedes Programm basiert auf einem [Programmtyp](../admin/program-types.md) der wichtige Aspekte des Programms und seiner Mitglieder definiert. Stellen Sie sicher, dass Sie über einen definierten Programmtyp verfügen, um Ihr Programm zu unterstützen, bevor Sie es erstellen.

1. Klicken **[!UICONTROL oben]** der Programmstruktur auf „Programm erstellen“.

1. Wählen Sie im Dialogfeld die **[!UICONTROL Übergeordnetes Element]** in der Programmstruktur aus.

   Dabei kann es sich um den Stamm, einen Ordner oder ein vorhandenes Programm handeln.

1. Geben Sie einen eindeutigen **[!UICONTROL Namen]** ein (erforderlich).

   ![Dialogfeld „Programm erstellen“](./assets/program-create-dialog.png){width="400"}

1. Wählen Sie **[!UICONTROL Programmtyp]**, der die Programmattribute und den Mitgliedsstatus bestimmt.

1. (Optional) Geben Sie eine **[!UICONTROL Beschreibung]** für das Programm ein.

   >[!TIP]
   >
   >Das Einschließen einer Beschreibung ist eine Best Practice und macht Ihre Programme leichter zugänglich und auffindbar.

1. Klicken Sie auf **[!UICONTROL Erstellen]**.

## Attribute {#attributes}

Jedes Programm erbt eine Reihe von Attributen von seinem [Programmtyp](../admin/program-types.md). Verwenden Sie Attribute, um die wichtigen Aspekte Ihrer Marketing-Programme zu beschreiben, z. B. Ereignisdaten und Standortattribute.

>[!NOTE]
>
>In Beta: Programmattribute als Token und als Mitglied von Programmeinschränkungen

## Status {#statuses}

Jedes Programm übernimmt eine Reihe von Mitgliedsstatus von seinem Programmtyp. Diese Status können Programmmitgliedern zur Verwendung in der Zielgruppensegmentierung mit dem Filter Mitglied des Programms zugewiesen werden.

Jeder Status wird einem Schritt im Programmtyp zugewiesen (z. B. 1, 2 oder 3). Mitglieder eines Programms können nur von einem Status mit derselben Schrittnummer (z. B. von _Nicht angezeigt_ zu _Teilgenommen_) oder zu einem Status mit einer höheren Schrittnummer (z. B. von _Eingeladen_ zu _Registriert_) wechseln.

Im Programmtyp werden Status mit _[!UICONTROL Als Erfolg]_ markieren) als erfolgreich betrachtet.

### Programmstatus ändern {#change-program-status}

Um eine Person zu einem Programm hinzuzufügen oder ihren Status zu ändern, muss sie eine Aktion **_[!UICONTROL Programmstatus ändern]_** [ auf einer Journey ](./action-nodes.md). Dadurch werden sie zu Mitgliedern des Programms und weisen ihnen einen Status in diesem Programm zu.

### Programmstatus korrigieren {#correct-program-status}

Wenn Personen versehentlich einem Status zugewiesen wurden und nicht vorwärts oder seitlich in den richtigen Status verschoben werden können, können Sie dies korrigieren, indem Sie die Person zunächst auf _Nicht im Programm_ setzen und sie dann auf den richtigen Status setzen.

## Mitglieder {#members}

Die **Mitglieder** zeigt ein Inventar der Personen an, die am Programm teilnehmen.

<!-- How do they get there? I don't see this populated for any of the programs that I have reviewd -->

## Token {#tokens}

Verwenden Sie _Meine Token_, um Programmdetails, die an vielen Orten angezeigt werden, einfach zu verwalten, z. B. Ereignisdaten und -speicherorte, E-Mail-Fußzeilen, Geschäftsjahre und Quartale und mehr. Diese programmspezifischen Token sind spezielle Zeichenfolgen, die zur Wiederverwendung in Journey- oder Marketing-Assets entwickelt wurden, um einen vorbestimmten Wert zu ersetzen. Beispiel:

_Sie sind eingeladen, an unserer Expo am `{{my.Event Date}}` teilzunehmen._

Wenn Sie diese E-Mail über eine Journey unter einem Programm senden, bei dem _Ereignisdatum_ Mein Token auf `2026-01-01` gesetzt ist, sieht der Empfänger Folgendes:

_Sie sind eingeladen, am 01.01.2026 an unserer Expo teilzunehmen._

Meine Token können auch auf Ordnerebene zugewiesen werden. Ordner und Programme übernehmen alle meine Token, die für ein übergeordnetes Element in der Baumstruktur definiert sind. Ein geerbtes Token kann überschrieben werden, wenn für dasselbe Token auf einer niedrigeren Ebene ein anderer Wert definiert ist. Sie können beispielsweise eine E-Mail-Fußzeile am oberen Rand Ihrer Ordnerstruktur definieren, aber die Copyright-Sprache für ein Co-Marketing-Ereignis bei einem Partner ändern oder die URL eines Werbebanners für ein produktspezifisches Programm ändern.

Weitere Informationen zur Definition und Verwendung meiner Token finden Sie unter [Benutzerdefinierte Token für die Personalisierung](./personalization-my-tokens.md).

## Mitglied des Programmfilters {#member-of-program}

_Mitglied des Programms_ ist ein Filter, mit dem Sie Ihre dynamischen Listen segmentieren können, je nachdem, ob eine Person Mitglied eines Programms ist, in welchem Status sie sich befindet und ob sie in diesem Programm erfolgreich ist. Seien Sie vorsichtig, wenn Sie die Begrenzungen **_Programm_** und **_Status_** zusammen verwenden - verwenden Sie übereinstimmende Typen mit den Programmen, die Sie für Filter verwenden, da dies sonst versehentlich eine Zielgruppe erstellen könnte, die keine Mitglieder haben kann.
