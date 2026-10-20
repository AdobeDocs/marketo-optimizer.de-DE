---
title: Benutzerzugriff und Berechtigungen
description: 'Verwalten des Benutzerzugriffs in der Adobe Admin Console: Erstellen Sie Benutzergruppen, weisen Sie Produktprofile zu und legen Sie rollenbasierte Berechtigungen für Marketo Optimizer fest.'
TQID: 'https://experienceleague.adobe.com/IY7Fvbk8GG2Xudh6vC4N9Bwk-sejvh-MMRIHHxvS-nc'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3cf5f37e-e87e-5179-812b-53ce05d7eebb
    internal-label: Setup
  - id: 46e599c6-e20f-5f67-9824-93415016f66b
    internal-label: Audiences
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: f65df8d5e83eca29ffaaabf51e7c80ed223d175a
workflow-type: tm+mt
source-wordcount: '2584'
ht-degree: 34%
---
# Benutzerzugriff und Berechtigungen

Nachdem die Bereitstellung abgeschlossen und Sandboxes gebunden sind, führen Sie die folgenden Schritte aus, um Ihrem Team und Ihren Benutzern [!DNL Marketo Optimizer] Zugriff zu gewähren.

1. [Erstellen eines  [!DNL Marketo Optimizer] -Produktprofils](#create-profile) in der Admin Console (nur einmalige/Ersteinrichtung).
1. [Hinzufügen einer Benutzergruppe](#add-user-group) in der Admin Console.
1. [Zuweisen des Produktprofils](#assign-profile) zur Benutzergruppe in der Admin Console.
1. [Benutzer zur neuen Gruppe hinzufügen](#add-users) in der Admin Console.
1. [Bearbeiten von integrierten Rollen](#edit-role-permissions) oder [Erstellen einer benutzerdefinierten Rolle](#create-a-custom-role) mit Produktberechtigungen und der erforderlichen [!DNL Marketo Optimizer]-Sandbox in Experience Platform.
1. [Hinzufügen von &#x200B;](#add-users-to-a-role) oder [Gruppen](#add-user-groups-to-a-role) zu Rollen in Adobe Experience Platform.

Informationen zum Einrichten empfohlener Benutzergruppen und Rollen für Administratoren, Benutzer mit Zugriff und schreibgeschützte Benutzer finden Sie unter [Vorgeschlagene &#x200B;](./permissions-reference.md#suggested-user-types) und [Erstellen von Benutzergruppen und Rollen für vorgeschlagene Benutzertypen](#create-suggested-roles).

## Produktprofil konfigurieren {#config-profile}

Als Administrator können Sie diese Aufgaben im [!DNL Adobe Admin Console] ausführen. Dies ist ein zentraler Ort, um Ihre Adobe-Produktlizenzen und Benutzende zu verwalten. In der Admin Console können Sie Benutzende an einem zentralen Ort anstatt in Ihren individuellen Lösungen erstellen und verwalten. Weitere Informationen zu den Funktionen und Leistungsmerkmalen von finden Sie auf der Seite Übersicht über Admin Console [&#128279;](https://helpx.adobe.com/business/enterprise/deploy-apps-updates.html).

### Die Admin Console aufrufen {#admin-console}

Bevor Sie die Admin Console zum Verwalten von Benutzenden in Ihrem Team verwenden können, müssen Sie sicherstellen, dass Sie auf die Admin Console zugreifen können und über die entsprechenden Berechtigungen verfügen.

1. Als System-Admin sollten Sie im Rahmen des Onboarding-Prozesses mehrere E-Mails von Adobe erhalten.

   Suchen Sie die Begrüßungs-E-Mail mit Informationen zum Namen der Organisation, auf die Sie Zugriff erhalten haben.

1. Klicken Sie auf **[!UICONTROL Link]** Erste Schritte“ in Ihrer Begrüßungs-E-Mail, um zur Admin Console zu navigieren.

   Wenn Sie die E-Mail nicht finden können, öffnen Sie einen Browser unter [https://adminconsole.adobe.com](https://adminconsole.adobe.com) direkt zur Admin Console.

1. Melden Sie sich mit Ihrer Adobe ID an.

   Nach erfolgreicher Anmeldung sehen Sie die _Übersicht_ der Adobe Admin Console.

1. Wenn Sie Zugriff auf mehrere Organisationen haben, stellen Sie sicher, dass Sie sich bei der richtigen Organisation angemeldet haben.

   Um Ihre Organisation zu ändern, klicken Sie oben rechts auf den Organisationsnamen und wählen Sie die Organisation aus, auf die Sie Zugriff benötigen.

1. Wählen Sie **[!UICONTROL Administratoren]** auf der Karte _[!UICONTROL Benutzer]_ aus, um zu überprüfen, ob Sie ein Systemadministrator sind.

   ![Admin Console-Übersichtsseite mit Administratoren, die auf der Karte „Benutzer“ ausgewählt wurden.](./assets/admin-console-overview-administrators.png){width="800" zoomable="yes"}

1. Suchen Sie durch Eingabe Ihrer Adobe ID-E-Mail-Adresse, Ihres Benutzernamens, Vor- oder Nachnamens.

   * Wenn Ihr Zugriff richtig konfiguriert ist, gibt die Suche Ihren Eintrag zurück.

   * Wenn in der Spalte **[!UICONTROL ADMINISTRATORROLLE]** der Wert &quot;`System`&quot; angezeigt wird, bedeutet dies, dass Sie (oder die angezeigte Person) System-Admin sind.

### [!DNL Marketo Optimizer] Produktprofil erstellen {#create-profile}

Wenn Sie Benutzenden Zugriff auf eine Adobe-Lösung gewähren, möchten Sie ihnen nicht unbedingt uneingeschränkten Zugriff gewähren. Produktprofile ermöglichen es jeder Lösung, über eigene Benutzerberechtigungen zu verfügen. Verwenden Sie die Admin Console, um Produktprofile zuzuweisen.

Weitere Informationen zur Verwendung von Produktprofilen für Benutzerberechtigungen finden Sie unter [_Verwalten von Produktprofilen für Unternehmensbenutzer_](https://helpx.adobe.com/business/enterprise/products-entitlements/manage-product-profiles/product-profiles.html){target="_blank"} in der Dokumentation zu Admin Console.

![Symbol, das angibt, dass Administratorzugriff erforderlich ist, um dieses Verfahren abzuschließen.](../assets/do-not-localize/icon-admin-user.svg){width="30"} Ein Systemadministrator oder [!DNL Experience Platform] Produktadministrator kann die folgenden Schritte unter [https://adminconsole.adobe.com](https://adminconsole.adobe.com) ausführen.

1. Wählen Sie die Registerkarte **[!UICONTROL Produkte]** aus.

1. Öffnen Sie die [!DNL Marketo Optimizer]-Instanz, der Sie das Profil hinzufügen möchten, und klicken Sie auf **[!UICONTROL Neues Profil]**.

1. Geben Sie einen Produktprofilnamen ein, z. B. _Zugriff_.

1. Klicken Sie **[!UICONTROL Weiter]** und dann **[!UICONTROL Speichern]**.

### Hinzufügen einer Benutzergruppe {#add-user-group}

Eine Benutzergruppe ist eine Sammlung von Benutzern, denen ein gemeinsamer Berechtigungssatz gewährt wird. Sie können Benutzer in Ihrer Benutzergruppe hinzufügen oder entfernen. Die Gruppenberechtigungen bleiben unverändert, während die Benutzer innerhalb der Gruppe wechseln.

Weitere Informationen dazu, wie Benutzergruppen zum Verwalten von Berechtigungen verwendet werden, finden Sie unter [Verwalten von Benutzergruppen](https://helpx.adobe.com/business/enterprise/users/users-and-groups/user-groups.html){target="_blank"} in der Dokumentation zu Admin Console.

![Symbol, das angibt, dass Administratorzugriff erforderlich ist, um dieses Verfahren abzuschließen.](../assets/do-not-localize/icon-admin-user.svg){width="30"} Ein Systemadministrator kann die folgenden Schritte unter [https://adminconsole.adobe.com](https://adminconsole.adobe.com) ausführen.

1. Wählen Sie die **[!UICONTROL Benutzer]** aus.

1. Wählen **[!UICONTROL Benutzergruppen]** im linken Navigationsbereich aus.

1. Klicken **[!UICONTROL oben]** auf „Neue Benutzergruppe“.

1. Geben Sie einen Namen für die Benutzergruppe ein, z. B. _Optimizer-Benutzer_ und klicken Sie auf **[!UICONTROL Speichern]**.

   ![Dialogfeld „Neue Benutzergruppe“ in der Admin Console mit eingegebenem Gruppennamen.](./assets/admin-console-new-user-group.png){width="600" zoomable="yes"}

### Produktprofil zuweisen {#assign-profile}

![Symbol, das angibt, dass Administratorzugriff erforderlich ist, um dieses Verfahren abzuschließen.](../assets/do-not-localize/icon-admin-user.svg){width="30"} Ein Produktadministrator kann die folgenden Schritte unter [https://adminconsole.adobe.com](https://adminconsole.adobe.com) ausführen.

1. Klicken Sie auf die von Ihnen erstellte Benutzergruppe.

1. Wählen Sie die Registerkarte **[!UICONTROL Zugewiesene Produktprofile]** und klicken Sie auf **[!UICONTROL Profil zuweisen]**.

1. Klicken Sie auf **+** und fügen Sie jede Instanz der folgenden Produkte hinzu:

   * [!UICONTROL Adobe Marketo Optimizer - Zugriff]
   * [!UICONTROL Adobe Experience Platform - AEP-default-all-users]
   * [!UICONTROL Adobe Experience Platform-Datenerfassung - Standardzugriff auf die Datenerfassung für alle]
   * [!UICONTROL Adobe Experience Platform - Standardzugriff auf alle Produktionsumgebungen]

   ![Registerkarte „Zugewiesene Produktprofile“ in der Admin Console mit Profilen, die zu einer Benutzergruppe hinzugefügt wurden.](./assets/admin-console-product-profiles.png){width="600" zoomable="yes"}

1. Klicken Sie auf **[!UICONTROL Speichern]**.

### Benutzer zur neuen Gruppe hinzufügen {#add-users}

Informationen zur Benutzerverwaltung finden Sie unter [_Adobe Admin Console-Benutzer_](https://helpx.adobe.com/business/enterprise/users/understand-user-management/user-management-overview.html){target="_blank"} in der Dokumentation zu Admin Console.

![Symbol, das angibt, dass Administratorzugriff erforderlich ist, um dieses Verfahren abzuschließen.](../assets/do-not-localize/icon-admin-user.svg){width="30"} Ein System- oder Produktadministrator kann die folgenden Schritte unter [https://adminconsole.adobe.com](https://adminconsole.adobe.com) ausführen. Ein Produktadministrator kann nur Benutzer hinzufügen, die bereits in seiner Organisation vorhanden sind.

1. Wenn die Benutzer noch nicht Mitglieder Ihrer Organisation sind, fügen Sie jeden Benutzer hinzu:

   * Klicken _[!UICONTROL unter &quot;]_&quot; auf **[!UICONTROL Benutzer hinzufügen]**.

   * Geben Sie die E-Mail-Adresse des Benutzers ein und klicken Sie auf **[!UICONTROL Als neuen Benutzer hinzufügen]**.

     ![Dialogfeld „Neuen Benutzer hinzufügen“ in der Admin Console mit einer eingegebenen E-Mail-Adresse.](./assets/admin-console-user-group-add-users.png){width="600" zoomable="yes"}

   * Geben Sie den Vor- und Nachnamen ein und klicken Sie dann auf **[!UICONTROL Speichern]**.

1. Fügen Sie jeder Benutzer der Gruppe hinzu:

   * Klicken Sie auf den Benutzernamen.

   * Scrollen Sie auf der Seite mit den Benutzerdetails zu **[!UICONTROL Benutzergruppen]**.

   * Klicken Sie links auf _Mehr_ ( **…** ) und wählen Sie **[!UICONTROL Benutzergruppen bearbeiten]**.

   * Klicken Sie auf _Hinzufügen_ ( **+** ) unter **[!UICONTROL Benutzergruppen]**.

     ![Dialogfeld „Benutzergruppen bearbeiten“ in der Admin Console mit einer für einen Benutzer ausgewählten Benutzergruppe.](./assets/admin-console-user-edit-user-groups.png){width="600" zoomable="yes"}

   * Wählen Sie die zuvor erstellte Benutzergruppe aus und klicken Sie auf **[!UICONTROL Anwenden]**.

   * Klicken **[!UICONTROL auf &quot;]**&quot; für die Benutzeränderungen.

## Zuweisen von Produktberechtigungen {#assign-product-permissions}

Berechtigungen sind Einzelrechte, mit denen Sie die einem Produktprofil zugewiesenen Berechtigungen definieren können. Jede Berechtigung wird unter einer Funktion gruppiert, z. B. Journey oder Inhalte von Personen, die Funktionen in [!DNL Marketo Optimizer] darstellen.

Im _Berechtigungen_ von Adobe Experience Platform können Admins Benutzerrollen und Zugriffsrichtlinien definieren, um Zugriffsberechtigungen für Funktionen und Objekte innerhalb einer Produktanwendung zu verwalten. In dieser App können Sie Rollen erstellen und verwalten sowie die gewünschten Ressourcenberechtigungen für diese Rollen zuweisen. Mit Berechtigungen können Sie auch die Sandboxes und die Benutzer verwalten, die einer bestimmten Rolle zugeordnet sind.

Weitere Informationen zu Rollenberechtigungen in Experience Platform finden Sie unter [Verwalten von Berechtigungen für eine Rolle](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/abac/permissions-ui/permissions){target="_blank"} in der Dokumentation zu Experience Platform.

1. Navigieren Sie zu [experience.adobe.com](https://experience.adobe.com/).

1. Wählen Sie im Bedienfeld _[!UICONTROL Schnellzugriff]_ die Option **[!UICONTROL Berechtigungen]** aus.

   >[!NOTE]
   >
   >Wenn „Berechtigungen _[!UICONTROL nicht angezeigt wird]_ müssen Sie möglicherweise auf **[!UICONTROL Alle anzeigen]** klicken und diese aus den verfügbaren Programmen auswählen.

   ![Berechtigungsanwendung, die im Bedienfeld „Schnellzugriff“ in Experience Platform ausgewählt wurde.](./assets/aep-permissions.png){width="700" zoomable="yes"}

### Ressourcen zu Berechtigungen {#permissions}

Eine vollständige Liste der Berechtigungen, die den Zugriff auf [!DNL Marketo Optimizer] Funktionen steuern, einschließlich Beschreibungen und der für jeden Benutzertyp empfohlenen Berechtigungen, finden Sie auf der Seite [Produktberechtigungen](./permissions-reference.md) .

>[!IMPORTANT]
>
>[!DNL Marketo Optimizer] Zugriff erfordert, dass Sie eine bestimmte Sandbox aktivieren, die mithilfe der folgenden Namenskonvention bereitgestellt wird: `Mktoaep` + [!DNL Marketo Engage] Abonnementpräfix. Wenn Ihr verknüpftes [!DNL Marketo Engage]-Abonnementpräfix beispielsweise _AcmeAssoc_ lautet, ist die für den [!DNL Marketo Optimizer] erforderliche Sandbox _MktoaepAcmeAssoc_. Diese Sandbox zu jeder Rolle hinzufügen.

>[!NOTE]
>
>Sie müssen Systemadministrator sein, um die Kachel _[!UICONTROL Berechtigungen]_ in Experience Platform sehen zu können.

### Rollenberechtigungen bearbeiten {#edit-role-permissions}

Für integrierte oder benutzerdefinierte Rollen können Sie sich jederzeit entscheiden, Berechtigungen hinzuzufügen oder zu löschen. Wenn Sie eine standardmäßige oder benutzerdefinierte Rolle ändern, wirkt sich dies auf jeden Benutzer aus, der dieser Rolle zugewiesen ist.

>[!IMPORTANT]
>
>[!DNL Marketo Optimizer] Zugriff erfordert, dass Sie eine bestimmte Sandbox aktivieren, die mithilfe der folgenden Namenskonvention bereitgestellt wird: `Mktoaep` + [!DNL Marketo Engage] Abonnementpräfix. Wenn Ihr verknüpftes [!DNL Marketo Engage]-Abonnementpräfix beispielsweise _AcmeAssoc_ lautet, ist die für den [!DNL Marketo Optimizer] erforderliche Sandbox _MktoaepAcmeAssoc_.

>[!NOTE]
>
>Ein Produktadministrator mit Zugriff auf Experience Platform-Berechtigungen kann die folgenden Schritte ausführen.

_So ändern Sie die Berechtigungen für eine Rolle :_

1. Wählen **[!UICONTROL Rollen]** im linken Navigationsbereich aus.

1. Klicken Sie auf **_Rollennamen_** Optimizer-Benutzer“.

1. Klicken Sie auf der Detailseite oben **[!UICONTROL auf]** Bearbeiten“.

   ![Seite mit Rollendetails in Experience Platform-Berechtigungen mit ausgewählter Option „Bearbeiten“.](./assets/aep-permissions-role-prime-edit.png){width="800" zoomable="yes"}

   Im Rolleneditor wird im Menü _[!UICONTROL Ressourcen]_ die Liste der Ressourcen angezeigt, die für die von Experience Cloud unterstützten Programme gelten.

1. Sandbox auswählen, die für [!DNL Marketo Optimizer] Zugriff bereitgestellt wurde (`Mktoaep<Marketo subscription prefix>`).

   ![Sandbox-Auswahlliste im Rolleneditor, in der die Marketo Optimizer-Sandbox angezeigt wird, die hinzugefügt werden kann.](./assets/aep-permissions-optimizer-sandbox.png){width="500" zoomable="yes"}

1. Klicken Sie auf _Hinzufügen_-Symbol (**+**) für jede der funktionalen Ressourcen.

   ![Rolleneditor in Experience Platform mit der B2B-Journey-Ressource, die mit den aufgelisteten Berechtigungen hinzugefügt wurde.](./assets/aep-permissions-b2b-list.png){width="700" zoomable="yes"}

1. Fügen Sie die spezifischen Berechtigungen für jede der Ressourcen hinzu oder wählen Sie **[!UICONTROL Alle hinzufügen]** aus.

1. Klicken Sie auf **[!UICONTROL Speichern]**.

   <!-- ![Experience Platform - B2B Journeys permissions saved for Channel Manager role](assets/aep-permissions-role-edit-b2b-journeys-done.png){width="700" zoomable="yes"} -->

1. Klicken Sie **[!UICONTROL Schließen]**, um zur Detailseite zurückzukehren.

### Benutzer zu einer Rolle hinzufügen {#add-users-to-a-role}

![Symbol, das angibt, dass Administratorzugriff erforderlich ist, um dieses Verfahren abzuschließen.](../assets/do-not-localize/icon-admin-user.svg){width="30"} Ein Systemadministrator oder Experience Platform-Administrator kann die folgenden Schritte ausführen.

1. Öffnen Sie die Rollendetails und wählen Sie die Registerkarte **[!UICONTROL Benutzer]** aus.

   Auf dieser Registerkarte wird eine Liste aller Benutzer angezeigt, die der Rolle zugewiesen wurden.

1. Klicken Sie **[!UICONTROL Benutzer hinzufügen]**.

   ![Registerkarte „Benutzer“ auf der Seite mit den Rollendetails in Experience Platform mit der Option „Benutzer hinzufügen“.](./assets/aep-permissions-role-prime-add-users.png){width="800" zoomable="yes"}

1. Suchen Sie im _[!UICONTROL Benutzer hinzufügen]_ die Benutzer, die Sie der Rolle hinzufügen möchten, und wählen Sie sie aus.

   * Sie können das Suchwerkzeug verwenden, um die Benutzerliste zu filtern.

   * Wählen Sie das Kontrollkästchen für jede Person aus.

   ![Dialogfeld „Benutzer hinzufügen“ in Experience Platform mit aktivierten Benutzer-Kontrollkästchen zum Hinzufügen zu einer Rolle.](assets/aep-permissions-role-add-users-dialog.png){width="600" zoomable="yes"}

1. Klicken Sie **[!UICONTROL Speichern]**, wenn Sie alle Benutzenden ausgewählt haben, die Sie hinzufügen möchten.

### Hinzufügen von Benutzergruppen zu einer Rolle {#add-user-groups-to-a-role}

Informationen zur Benutzerverwaltung finden Sie unter [_Adobe Admin Console-Benutzer_](https://helpx.adobe.com/business/enterprise/users/understand-user-management/user-management-overview.html){target="_blank"} in der Dokumentation zu Admin Console.

![Symbol, das angibt, dass Administratorzugriff erforderlich ist, um dieses Verfahren abzuschließen.](../assets/do-not-localize/icon-admin-user.svg){width="30"} Ein Systemadministrator oder Experience Platform-Administrator kann die folgenden Schritte ausführen.

1. Öffnen Sie die Rollendetails und wählen Sie die Registerkarte **[!UICONTROL Benutzergruppen]** aus.

   Auf dieser Registerkarte wird eine Liste aller Benutzergruppen angezeigt, die der Rolle zugewiesen sind.

1. Klicken Sie **[!UICONTROL Gruppen hinzufügen]**.

   ![Registerkarte „Benutzergruppen“ auf der Seite mit den Rollendetails in Experience Platform mit der Option „Gruppen hinzufügen“.](./assets/aep-permissions-role-prime-add-groups.png){width="800" zoomable="yes"}

1. Suchen Sie im _[!UICONTROL Gruppen hinzufügen]_ die Gruppen, die Sie der Rolle hinzufügen möchten, und wählen Sie sie aus.

   * Sie können das Suchwerkzeug verwenden, um die Liste der Benutzergruppen zu filtern.

   * Aktivieren Sie das Kontrollkästchen für jede Benutzergruppe.

   ![Das Dialogfeld „Gruppen hinzufügen“ in Experience Platform mit aktivierten Kontrollkästchen für Benutzergruppen zum Hinzufügen zu einer Rolle.](assets/aep-permissions-role-add-groups-dialog.png){width="600" zoomable="yes"}

1. Klicken Sie **[!UICONTROL Speichern]**, wenn Sie alle Gruppen ausgewählt haben, die Sie hinzufügen möchten.

### Erstellen einer benutzerdefinierten Rolle {#create-a-custom-role}

![Symbol, das angibt, dass Administratorzugriff erforderlich ist, um dieses Verfahren abzuschließen.](../assets/do-not-localize/icon-admin-user.svg){width="30"} Ein Systemadministrator oder Experience Platform-Administrator kann die folgenden Schritte ausführen.

1. Wählen Sie **[!UICONTROL linken Navigationsbereich die Option]** Rollen“ und dann **[!UICONTROL Rolle erstellen]** aus.

1. Geben _[!UICONTROL im Dialogfeld Neue Rolle erstellen]_ einen Namen für die Rolle ein, z. B. _B2B-Marketer_ und eine Beschreibung (optional).

1. Klicken Sie auf **[!UICONTROL Bestätigen]**.

1. Sandbox auswählen, die für [!DNL Marketo Optimizer] Zugriff bereitgestellt wurde (`Mktoaep<Marketo subscription prefix>`).

   ![Sandbox-Auswahlliste im Rolleneditor mit ausgewählter Marketo Optimizer-Sandbox.](./assets/aep-permissions-optimizer-sandbox.png){width="500" zoomable="yes"}

1. Hinzufügen von Produktberechtigungen:

   Informationen dazu, welche Produktfunktionen Sie für die Rolle verwenden möchten, finden Sie in der Liste der [Produktberechtigungen](./permissions-reference.md).

   Suchen Sie in der _[!UICONTROL Ressourcen]_-Liste auf der linken Seite die B2B-Elemente und klicken Sie auf das _Hinzufügen_-Symbol (**+**), um jedes Attribut hinzuzufügen, das Sie für die Rolle aktivieren möchten.

   Sie können im Suchwerkzeug _B2B_ eingeben, um die Liste nach vielen der B2B-bezogenen Produktberechtigungen zu filtern, die für [!DNL Marketo Optimizer] gelten.

   ![Rolleneditor in Experience Platform mit B2B-Ressourcen, die im Suchfeld gefiltert wurden.](./assets/aep-permissions-b2b-list.png){width="700" zoomable="yes"}

1. Klicken **[!UICONTROL oben]** auf „Speichern“.

1. Gehen Sie zu den Rollendetails und wählen Sie die Registerkarte **[!UICONTROL Benutzergruppen]** aus.

1. Klicken Sie **[!UICONTROL Gruppen hinzufügen]**.

1. Aktivieren Sie das Kontrollkästchen neben der Benutzergruppe, die Sie zuvor in der Admin Console erstellt haben.

1. Klicken Sie auf **[!UICONTROL Speichern]**.

Ihre benutzerdefinierte Rolle ist konfiguriert und Benutzerinnen und Benutzer in der zugewiesenen Gruppe können jetzt auf die ausgewählten [!DNL Marketo Optimizer] zugreifen.

### Erstellen von Benutzergruppen und Rollen für vorgeschlagene Benutzertypen {#create-suggested-roles}

Gehen Sie wie folgt vor, um die von _Admin_, _All Access User_ und _Read Only Access User_ [&#x200B; Benutzertypen &#x200B;](./permissions-reference.md#suggested-user-types). Für jeden Benutzertyp erstellen Sie eine Benutzergruppe in der Admin Console und eine Rolle in Experience Platform und fügen dann die Gruppe zur Rolle hinzu. Die vorgeschlagenen Berechtigungen für jeden Benutzertyp sind unter [_Produktberechtigungen_](./permissions-reference.md) aufgeführt.

#### Erstellen der Admin-Benutzergruppe und -Rolle {#create-admin-group}

![Symbol, das angibt, dass Administratorzugriff erforderlich ist, um dieses Verfahren abzuschließen.](../assets/do-not-localize/icon-admin-user.svg){width="30"} Systemadmins können die folgenden Schritte ausführen.

1. Fügen Sie in der Admin Console [Benutzergruppe hinzufügen](#add-user-group) mit dem Namen _Marketo Optimizer-_ hinzu und [das Produktprofil &#x200B;](#assign-profile).

1. Fügen Sie der Gruppe die Benutzer hinzu, die [!DNL Marketo Optimizer] eingerichtet und verwaltet haben.

1. Machen Sie die Benutzer zu Produktadministratoren, damit sie Benutzer und Gruppen verwalten können.

1. Wählen Sie in &lbrace;0Experience Platform _[!UICONTROL Berechtigungen]_ die Option **[!UICONTROL Rollen]** > **[!UICONTROL Rolle erstellen]**

1. Geben Sie den Namen ein, z. B. _Marketo Optimizer Administrator_ und klicken Sie auf **[!UICONTROL Bestätigen]**.

1. Sandbox auswählen, die für [!DNL Marketo Optimizer] Zugriff bereitgestellt wurde (`Mktoaep<Marketo subscription prefix>`).

   >[!IMPORTANT]
   >
   >Dieser Schritt ist für einen ordnungsgemäßen Zugriff von entscheidender Bedeutung.

1. Klicken Sie für jede der folgenden Kategorien auf das Symbol _Hinzufügen_ (**+**) und wählen Sie **[!UICONTROL Alle hinzufügen]**:

   * _[!UICONTROL B2B-Admin-Konfigurationen]_
   * _[!UICONTROL B2B-Assets]_
   * _[!UICONTROL B2B-Kanal-Konfigurationen]_
   * _[!UICONTROL B2B-Gesprächserlebnis]_
   * _[!UICONTROL B2B-Ziele]_
   * _[!UICONTROL B2B-Ordner-Token]_
   * _[!UICONTROL B2B-Ordner]_
   * _[!UICONTROL B2B-Intent-Konfiguration]_
   * _[!UICONTROL B2B-Journey]_
   * _[!UICONTROL B2B-Labs]_
   * _[!UICONTROL B2B-Organisationsregeln]_
   * _[!UICONTROL B2B-Personenlisten]_
   * _[!UICONTROL B2B-Programm-Token]_
   * _[!UICONTROL B2B-Programmtypen]_
   * _[!UICONTROL B2B-Programme]_
   * _[!UICONTROL B2B-Reporting]_
   * _[!UICONTROL Dashboards]_
   * _[!UICONTROL Ziele]_
   * _[!UICONTROL Data Governance]_
   * _[!UICONTROL Datenaufnahme]_
   * _[!UICONTROL Profil-Management]_

   >[!TIP]
   >
   >Verwenden Sie **[!UICONTROL Alle hinzufügen]** nur für die Administratorrolle. Wenn neue Funktionen veröffentlicht werden, werden die Berechtigungen, die für sie vorbereitet wurden, automatisch auf die Administratorrolle angewendet, sodass Sie die Rolle nicht bearbeiten müssen. Wählen Sie für die anderen Benutzertypen nur die Berechtigungen aus, die für diesen Typ unter &quot;[_&quot; empfohlen_](./permissions-reference.md).

1. Klicken Sie auf **[!UICONTROL Speichern]**.

1. Wählen Sie in den Rollendetails die Registerkarte **[!UICONTROL Benutzergruppen]**, klicken Sie auf **[!UICONTROL Gruppen hinzufügen]**, wählen Sie _Marketo Optimizer-_ und klicken Sie auf **[!UICONTROL Speichern]**.

#### Erstellen der Benutzergruppe und der Rolle „Zugriff auf alle“ {#create-all-access-group}

![Symbol, das angibt, dass Administratorzugriff erforderlich ist, um dieses Verfahren abzuschließen.](../assets/do-not-localize/icon-admin-user.svg){width="30"} Systemadmins können die folgenden Schritte ausführen.

1. Fügen Sie in der Admin Console [Benutzergruppe hinzufügen](#add-user-group) mit dem Namen _Marketo Optimizer-_ hinzu, [ihr das &#x200B;](#assign-profile) zuweisen und [Benutzende hinzufügen](#add-users) der Gruppe.

1. Wählen Sie in Experience Platform-Berechtigungen [Erstellen einer benutzerdefinierten Rolle](#create-a-custom-role) mit dem Namen _Marketo Optimizer All Access User_.

1. Sandbox auswählen, die für [!DNL Marketo Optimizer] Zugriff bereitgestellt wurde (`Mktoaep<Marketo subscription prefix>`).

1. Klicken Sie für jede Kategorie [Produktberechtigungen](./permissions-reference.md) auf das Symbol _Hinzufügen_ (**+**) und wählen Sie nur die Berechtigungen aus, die für Alle Zugriffsbenutzer empfohlen werden.

   Alle Access-Benutzer können täglich in jeder Funktion arbeiten, erhalten jedoch keine Admin-, Kanal- oder Setup-Berechtigungen.

1. Klicken Sie auf **[!UICONTROL Speichern]**.

1. Wählen Sie in den Rollendetails die Registerkarte **[!UICONTROL Benutzergruppen]**, klicken Sie auf **[!UICONTROL Gruppen hinzufügen]**, wählen Sie _Marketo Optimizer-_ aus und klicken Sie auf **[!UICONTROL Speichern]**.

#### Erstellen der Benutzergruppe und Rolle für schreibgeschützten Zugriff {#create-read-only-group}

![Symbol, das angibt, dass Administratorzugriff erforderlich ist, um dieses Verfahren abzuschließen.](../assets/do-not-localize/icon-admin-user.svg){width="30"} Systemadmins können die folgenden Schritte ausführen.

1. Fügen Sie in der Admin Console [Benutzergruppe hinzufügen](#add-user-group) mit dem Namen _Marketo Optimizer-_ hinzu, [ihr das &#x200B;](#assign-profile) zuweisen und [Benutzer hinzufügen](#add-users) der Gruppe.

1. Wählen Sie in den Experience Platform[Berechtigungen „Benutzerdefinierte Rolle erstellen](#create-a-custom-role) mit dem Namen &quot;_Marketo Optimizer Read Only Access User_.

1. Sandbox auswählen, die für [!DNL Marketo Optimizer] Zugriff bereitgestellt wurde (`Mktoaep<Marketo subscription prefix>`).

1. Klicken Sie für jede Kategorie [Produktberechtigungen](./permissions-reference.md) auf das Symbol _Hinzufügen_ (**+**) und wählen Sie nur die Berechtigungen aus, die für Benutzer mit Lesezugriff empfohlen werden.

   Schreibgeschützter Zugriff Benutzer können nur Funktionen anzeigen.

1. Klicken Sie auf **[!UICONTROL Speichern]**.

1. Wählen Sie in den Rollendetails die Registerkarte **[!UICONTROL Benutzergruppen]**, klicken Sie auf **[!UICONTROL Gruppen hinzufügen]**, wählen Sie _Schreibgeschützte Marketo Optimizer-Benutzergruppe_ und klicken Sie auf **[!UICONTROL Speichern]**.
