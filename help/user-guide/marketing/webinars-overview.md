---
title: Interaktive Webinare
description: Lernen Sie die Konzepte hinter interaktiven Webinaren in Marketo Optimizer kennen, einschließlich des Webinar-Asset-Modells, der Mitgliedstaaten, Token und Aktivitäten.
keywords: 
role: User
feature: Channels
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 75b481faf0d66210329f95c8afabdfa59e7bcb79
workflow-type: tm+mt
source-wordcount: 1085
ht-degree: 2%

---


# Interaktive Webinare

Mit interaktiven Webinaren können Sie ein Live- oder simuliertes Webinar planen, bewerben, bereitstellen und verfolgen, ohne [!DNL Adobe Marketo Optimizer] verlassen zu müssen. Der Versand wird automatisch auf [!DNL Adobe Connect] ausgeführt, sodass Sie nie zwischen Produkten wechseln müssen, um eine Registrierungsseite zu entwerfen, die Live-Sitzung zu hosten oder Anwesenheitsdaten abzurufen.

>[!NOTE]
>
>Diese Funktion erfordert eine Lizenz und unterliegt zusätzlichen Bedingungen. Um weitere Informationen zu den zusätzlichen Nutzungsbedingungen zu erhalten, überprüfen Sie Ihren Vertrag oder kontaktieren Sie Adobe.

Sie können ein Webinar auf zwei Arten erstellen:

* **Gesprächserlebnis** - Bitten Sie den Kollegen, ein Webinar in natürlicher Sprache zu planen, zu bewerben und darüber zu berichten. Siehe [Erstellen von Webinaren mit &#x200B;](../agents/webinar-creation.md).

* **Point-and-Click** - Verwenden Sie den Arbeitsbereich _[!UICONTROL Programme]_, um ein Webinar-Asset hinzuzufügen, es zu entwerfen, Co-Hosts und Moderatoren hinzuzufügen, Journey für die Promotion und Nachbereitung zu erstellen und das Reporting zu überprüfen. Siehe [Erstellen und Entwerfen eines Webinars](create-webinar.md) und [Webinar-Promotion und Follow-up-Journey &#x200B;](webinar-journeys.md).

## Webinar als Medienelement

Ein Webinar ist ein Asset, das einem [Programm](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/prime/marketing-management/programs/programs) gehört, genau wie eine E-Mail oder Landingpage. Wenn Sie ein Webinar zu einem Programm hinzufügen, wird es dort registriert und macht seine Token, Attribute und Aktivitäten für alle Journey und Assets in diesem Programm verfügbar.

>[!IMPORTANT]
>
>Ein Programm kann derzeit ein Webinar-Asset besitzen. Die Unterstützung mehrerer Webinare pro Programm ist für eine künftige Version geplant.

## Mitgliedstaaten

Für jede Person, die Mitglied eines Programms ist, das ein Webinar enthält, bewerben sich drei unabhängige Staaten gleichzeitig. Sie können in Zielgruppen- und Journey-Bedingungen separat referenziert werden.

| Bundesland | Eigentümerin oder Eigentümer | Werte |
|---|---|---|
| Status des Programmmitglieds | Programm | Konfigurierbar pro [Programmtyp](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/prime/admin/program-types) |
| Webinar-Status | Webinar-Asset | Eingeladen, registriert, anwesend, No-Show, Teilgenommen auf Anfrage |
| Journey-Status | Journey | Aktueller Knoten, angehaltene, abgeschlossene und andere Journey-Laufzeitstatus |

### Webinar-Status

Der Webinar-Status hat fünf Werte. [!DNL Adobe Connect] setzt den Wert normalerweise automatisch, Sie können den Status aber auch mit einer Journey-Aktion festlegen, wenn Sie ihn überschreiben müssen. Um die Anwesenheit widerzuspiegeln, die in einem anderen System aufgezeichnet wurde, können Sie beispielsweise den Status auf Ihrer Journey festlegen.

| Status | Wie sie festgelegt ist | Quelle |
|---|---|---|
| Eingeladen | Ein Journey _Knoten „Aktion ausführen_, in der Regel, wenn die Einladungs-E-Mail gesendet wird | Autorengesteuert |
| Registriert | Ein _Aktion ausführen_ Journey-Knoten, wenn sich die Person registriert. Dadurch wird auch [!DNL Adobe Connect], die Join-URL der Person zu generieren | Autorengesteuert |
| Teilnahme | Ein Ereignis von [!DNL Adobe Connect] nach der Ausführung des Live-Webinars | Systemgesteuert, mit Authoring-Überschreibung über eine Journey verfügbar |
| Nichterscheinen | Ein Ereignis von [!DNL Adobe Connect] nach der Ausführung des Live-Webinars | Systemgesteuert, mit Authoring-Überschreibung über eine Journey verfügbar |
| Attended on demand | Ein Ereignis von [!DNL Adobe Connect], bei dem eine Person, die später nicht live teilgenommen hat, die Aufzeichnung ansieht | Systemgesteuert, mit Authoring-Überschreibung über eine Journey verfügbar |

>[!IMPORTANT]
>
>Unabhängig davon, ob der Webinar-Status automatisch oder von einer Journey aus festgelegt wird, bewegt er sich nur in eine Richtung, genau wie [Programmstatus](./programs.md#statuses). Eine Person kann in einen späteren Status wechseln (z. B _&quot;_&quot; in _Teilgenommen_), jedoch nicht zurück in einen früheren Status. Planen Sie eine beliebige Autorenüberschreibungen mit diesem linearen Verlauf.

Um eine Person von einer Journey in einen anderen Status zu versetzen, verwenden Sie die Aktion **[!UICONTROL Webinar-Mitgliedsstatus ändern]**. Siehe [Webinar-Promotion und Follow-up-Journey &#x200B;](webinar-journeys.md).

## Webinar-Token

Webinar-Token stehen überall dort zur Verfügung, wo Sie E-Mail-Inhalte personalisieren können (Betreff, Text, Preheader und Absender). Suchen Sie sie im Personalisierungseditor unter **_Kontext > Webinar_**.

Token auf Asset-Ebene befinden sich direkt im Webinar-Ordner:

&#x200B;- Titel
&#x200B;- Beschreibung
&#x200B;- Startdatum/Uhrzeit, Enddatum/Uhrzeit
&#x200B;- Dauer
&#x200B;- Zeitzone
&#x200B;- Moderatoren
&#x200B;- Aufnahme-URL

>[!NOTE]
>
>Co-Hosts werden im Abschnitt Webinar-Team der Webinar-Seite angezeigt, sind jedoch nicht als Personalisierungs-Token verfügbar.

Token pro Empfänger sind in einem Unterordner **Mitglied** verfügbar:

&#x200B;- **Status** - Der aktuelle Webinar-Status des Empfängers (eingeladen, registriert, teilgenommen, nicht gezeigt oder auf Abruf teilgenommen). Siehe [Webinar-Status](#webinar-status).
&#x200B;- **URL wird** - der persönliche [!DNL Adobe Connect] des Empfängers. Dies wird erst behoben, nachdem der Webinar-Status des Empfängers registriert wurde oder später. Es wird für jeden zu einem früheren Zeitpunkt leer aufgelöst.
&#x200B;- **Aufzeichnungs-URL** - Wird aufgelöst, nachdem die Aufzeichnung nach der Live-Sitzung veröffentlicht wurde, und bleibt bis dahin leer. Verwenden Sie sie bedingt in E-Mails nach dem Webinar, damit kein Link angezeigt wird, bevor eine Aufzeichnung angezeigt wird.

>[!NOTE]
>
>Webinar-Token werden derzeit nur in E-Mail-Inhalten gerendert (Betreff, Text, Preheader und Absender). Die Unterstützung für Webinar-Token in Landingpages und Formularen ist für eine zukünftige Version geplant.
>
>Da diese Token als leer aufgelöst werden, anstatt einen Fehler auszulösen, wird eine E-Mail oder Seite, die auf sie verweist, an jedem Punkt im Webinar-Lebenszyklus sicher gerendert. Vorschau des Inhalts vor und nach Verfügbarkeit der Werte zur Bestätigung, dass das Layout in beide Richtungen aussieht.

## Webinar-Aktivitäten

Jedes Webinar zeigt automatisch Aktivitäten an, die Sie als _Lauschen auf Ereignisse_ Trigger, _Aufspaltungspfad_ Bedingungen, Zielgruppenfilter und Berichtsmetriken verwenden können:

* Stellt eine Frage
* Antwortet auf eine Umfrage
* Klicks auf einen Link
* Lädt ein Asset herunter
* Hebt die Hand

>[!NOTE]
>
>Änderungen des Webinar-Status (eingeladen, registriert, teilgenommen, nicht angezeigt, On-Demand) sind derzeit nicht als eigene Filter für _Auf Veranstaltungen_) verfügbar. Um eine Journey zum Webinar-Status zu verzweigen, verwenden Sie eine Bedingung _Aufspaltungspfad_ im Webinar-Status direkt (beschrieben in [_Erstellen einer Post-Webinar-Journey_](webinar-journeys.md#build-post-webinar-journey)), anstatt auf eine Aktivität mit Statusänderung zu warten.

Die Interaktion von Personen, die die Aufzeichnung anschauen, nachdem das Live-Ereignis aufgenommen wurde, als dieselben Aktivitäten, getaggt mit einem Modus von On-Demand. Im Gegensatz zu den Aktivitäten wird bei der Interaktion auf Abruf ein separater Webinar-Status erstellt: Eine Person, die nicht live dabei war und sich später die Aufzeichnung ansieht, wechselt von **No-Show** zu **Attended on Demand**.

## Voraussetzungen

Bevor Sie mit der Erstellung eines Webinars beginnen, stellen Sie sicher, dass Folgendes vorhanden ist.

| Voraussetzung | Details |
|---|---|
| Ein Programm | Das Webinar wird innerhalb eines vorhandenen Programms hinzugefügt. Marketing-Operations-Analyst*innen erstellen das Programm normalerweise zuerst. |
| Webinar-Lizenz (Kapazität) | Eine Webinar-Lizenz, auch als Kapazitätsberechtigung bezeichnet, muss verfügbar sein, bevor Sie ein Webinar planen können. Wenn Sie beim Setup eine Kapazität auswählen, stehen möglicherweise Add-ons mit höherer Kapazität zur Verfügung. Wenden Sie sich an Ihr Adobe-Accountteam, um Ihre verfügbare Kapazität zu erhöhen. |
| [!DNL Adobe Connect] | Versand läuft in [!DNL Adobe Connect]. Die Bereitstellung erfolgt automatisch im Hintergrund. Sie müssen [!DNL Marketo Optimizer] nicht mit der Erstellung oder Durchführung eines Webinars beauftragen. |

### Berechtigungen

Der Zugriff auf Webinar-Funktionen hängt von den Ihnen zugewiesenen Berechtigungen für Webinare ab.

| Rolle | Was sie gewährt |
|---|---|
| B2B-Webinare anzeigen | Die Liste der Webinare sowie eine Webinar-Konfiguration, Details und Berichte anzeigen. Die Steuerelemente „Erstellen“, „Entwerfen“, „Bearbeiten“ und „Eingeben“ sind mit dieser Berechtigung nicht verfügbar und Sie können keinem Webinar als Co-Host oder Moderator zugewiesen werden. |

<!-- 
| Manage B2B webinars | Full lifecycle access: create, design, configure, schedule, edit, deliver, host, and delete a webinar. The Create, Design, Edit, and Manage controls are available only for users with this role. |
| Webinar co-host | After you are added as a co-host, this permission enables you to design and enter that webinar with co-host controls. |
| Webinar presenter | After you are added as a presenter, this permission enables you to view and enter that webinar with presenter capabilities. It grants no authoring or design access on its own. |

>[!NOTE]
>
>Co-hosts and presenters are currently defined by entering a name and email rather than selected from a picker of role-eligible users — see [Add co-hosts and presenters](create-webinar.md#add-co-hosts-and-presenters). The _Webinar co-host_ and _Webinar presenter_**_ roles still govern what that person can do when they are added as a co-host or presenter.

-->
