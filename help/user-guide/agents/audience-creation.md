---
title: Erstellen von Zielgruppen für Programme
description: Verwenden Sie die Fähigkeit zur Zielgruppenerstellung in Marketo Optimizer, um Personenlisten zu erstellen, Marketo Engage-Smart-Listen anzupassen und Listenregeln im Chat zu bearbeiten.
TQID: 'https://experienceleague.adobe.com/WFfKcQ3zfJmVDGstLmpPbC9iDF5JtBX67-izCC-CNds'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 1650dadf-b034-5ac9-a309-77ad1e2f5035id: 46e599c6-e20f-5f67-9824-93415016f66bid: 64b90904-e4f0-5c1b-a871-8c6a40b204a1id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 1464
ht-degree: 1%

---

# Erstellen von Zielgruppen für Programme

In [!DNL Adobe Marketo Optimizer] definieren [_Personenlisten_](../audiences/people-lists.md) die Zielgruppe für Personen-Journeys - entweder als dynamische filterbasierte Listen, die automatisch aktualisiert werden, oder als statische Listen mit fester Zugehörigkeit. In der [Chat](./chat-interface.md)Oberfläche erstellt, passt _Audience Creation_ [SKILL](./skills.md) mithilfe einer geführten Konversation Personenlisten an und bearbeitet sie.

* **Kenntnisse** - `audience-creation` und `people-list-comparison`
* **Aufruf** - Zielgruppenkriterien direkt beschreiben, eine [!DNL Marketo Engage] Smart-Liste hochladen oder eine vorhandene Liste zur Bearbeitung benennen
* **Lese-/Schreibvorgänge nach** - [!DNL Marketo Optimizer]; liest [!DNL Marketo Engage] bei der Anpassung von Smart Lists

## Unterstützte Workflows {#workflows}

Der -Mitarbeiter unterstützt drei Workflows zur Erstellung von Zielgruppen und bestimmt anhand Ihrer Anfrage, welcher Workflow gelten soll. Wenn der Zweck mehrdeutig ist, werden Sie gefragt, bevor Sie fortfahren.

| Workflow | Einsatz | Prompt-Beispiel |
|---|---|---|
| **Neu erstellen** | Sie möchten eine neue Personenliste, die durch Kriterien oder Mitgliedschaft definiert ist. | _„Erstellen Sie eine dynamische Liste von VPs für Marketing bei SaaS-Unternehmen in Nordamerika._ |
| **Anpassen einer [!DNL Marketo Engage] Smart List** | Sie haben bereits eine [!DNL Marketo Engage] Smart List oder Smart Campaign und möchten eine entsprechende Personenliste. | _„Passen Sie diese Smart-Liste von Marketo in eine Personen-Liste an.“_ (Asset anhängen) |
| **Bearbeiten einer vorhandenen Liste** | Sie möchten die Regeln einer bereits vorhandenen Liste hinzufügen oder ersetzen. | _„Regel für Lead-Score über 50 zu meiner Liste &#39;Enterprise Trials&#39; hinzufügen._ |

## Erstellen einer neuen Personenliste {#create-from-scratch}

Bevor Sie etwas generieren, bestätigt der Mitarbeiter alle vier folgenden Punkte. Es fragt nach allen, die fehlen - in einer einzigen Nachricht.

1. **Regeln/Kriterien** - Eine einfache Beschreibung dessen, wer in die Liste gehört.
1. **Name** - Wie nennt man die Liste?
1. **Location** - In welchem Programm die Liste leben soll. Geben Sie einen Programmnamen an, und Coworker findet ihn. Wenn mehrere Übereinstimmungen vorliegen, werden Sie aufgefordert, ihn auszuwählen.
1. **Type** - Dynamisch (filterbasiert, automatisch aktualisiert) oder Statisch (feste Mitgliedschaft). Dies ist erforderlich - Kollegen raten nicht; wenn Sie es nicht angeben, fragt es.

### Dynamische Listen {#dynamic-lists}

Für dynamische Listen empfiehlt der Mitarbeiter proaktiv die Verwendung von Personalisierungsattributen, um die Zielgruppenbestimmung zu verfeinern. Diese Attribute sind **_standardmäßig enthalten - Sie schließen die Funktion ab, nicht_**:

| Attribut | Warum es hilft |
|---|---|
| **Abgeleitete Rolle** | KI-abgeleitete Käuferrolle für personalbasiertes Content-Targeting. |
| **Abgeleitete Absicht** | Abgeleitete Kaufabsichtssignale, die auf Marktkonten hindeuten. |
| **Interaktionsstufe** | Berechneter Interaktionsgrad, der interaktive Kontakte priorisiert. |

Informieren Sie Coworker , wenn Sie eine dieser Komponenten entfernen möchten, bevor der Vorgang fortgesetzt wird.

### Statische Listen {#static-lists}

* **Statisch, keine Kriterien** - Die Liste wird leer erstellt und kann manuell hinzugefügt werden.
* **Statisch aus Kriterien (ein Schnappschuss)** - Ein Mitarbeiter erstellt den passenden Satz und kopiert diese Personen in . Population ist asynchron - Ein Kollege bestätigt, dass die Liste erstellt wurde, merkt aber an, dass es einige Minuten dauern kann, bis Personen angezeigt werden. Sie wird nicht für sich in Anspruch nehmen, dass die Liste sofort bereit ist.

## Karte prüfen {#review-card}

Es wird nichts erstellt, bis Sie es genehmigen. Nachdem Sie Ihre Kriterien beschrieben haben, präsentiert der Mitarbeiter eine interaktive Karte _People List Creation Review_ (für Anpassungen aus [!DNL Marketo Engage] Listen heißt die Karte _People List Conversion Review_).

Jede Zeile in der Karte stellt eine Bedingung dar:

| Spalte | Bedeutung |
|---|---|
| **Anforderungen** (oder der Name der [!DNL Marketo Engage] für Anpassungen) | Ihre ursprüngliche Anfrage oder der Marketo-Quellfilter. |
| **(Regel)** | Die tatsächliche attributbasierte Regel, die für diese Bedingung generiert wurde. |
| **Einschließen** | Ein Kontrollkästchen zum Beibehalten oder Ablegen dieser Regel. |

**Konfidenzniveaus:**

* **Hohe Konfidenz** Zeilen werden sauber abgeglichen und standardmäßig aktiviert.
* **Geringe Konfidenz** Zeilen (ungefähre Zuordnungen oder alles, was gekennzeichnet ist) werden mit einem Hinweis angezeigt und sind standardmäßig deaktiviert.
* Zeilen, die das System nicht zuordnen konnte, zeigen **„Keine Entsprechung gefunden“** — diese haben keine Regel und bleiben deaktiviert.

Eine _Konversionszusammenfassung_ ergibt _N Konfidenz_ und _N Konfidenz_ mit einem Hinweis: Regeln mit geringer Konfidenz sind standardmäßig deaktiviert. Aktivieren Sie diese, um sie in den Chat einzubeziehen oder die gewünschte Änderung zu beschreiben.

**Kartenaktionen:**

* **Fortfahren** - Erstellt die Liste nur unter Verwendung der aktivierten Regeln.
* **Beschreiben Sie die gewünschten Änderungen im Chat** - Füllen Sie die Eingabe vorab mit _aus„Ich möchte Folgendes ändern: &quot;_, damit Sie verfeinern können; Coworker regeneriert und zeigt eine neue Karte an, wobei die Regeln beibehalten werden, die Sie bereits genehmigt hatten.

Sie können auch jederzeit eine Folgenachricht eingeben (z. B. _„auch auf Unternehmen mit mehr als 500 Mitarbeitern beschränken“_) und Coworker regeneriert die Karte.

## Attributzuordnung {#attribute-mapping}

Wenn Sie Kriterien beschreiben, übersetzt Coworker jede Bedingung in ein reales, bekanntes Attribut auf Personenebene. Auf der Überprüfungskarte können drei Ergebnisse angezeigt werden:

1. **Übereinstimmung (hohe Konfidenz)** - Ihre Bedingung wird direkt einem Attribut zugeordnet (z. B. _„email is acme.com“_ wird dem `email` Attribut zugeordnet). Standardmäßig aktiviert.
1. **Annähernd (geringe Konfidenz)** - Das Attribut, das dem Namen oder Datenmodell am nächsten liegt, unterscheidet sich (z. B. ein Marketo _Betrag_-Filter, der als _Lead-Score_). Wird mit einem Hinweis angezeigt, der den Unterschied erklärt; standardmäßig deaktiviert.
1. **Nicht gefunden** — Die Bedingung konnte keinem bekannten Attribut zugeordnet werden. Wird als _Kein Äquivalent gefunden“ angezeigt_ es wird keine Regel generiert.

Deshalb kann eine Liste, die Sie beschreiben, mit weniger Regeln zurückkommen als die von Ihnen angegebenen Bedingungen - nicht übereinstimmende Bedingungen werden explizit angezeigt, anstatt im Hintergrund gelöscht zu werden. Wenn wichtige Kriterien als „not found“ (nicht gefunden) landen, formulieren Sie sie mit dem echten Namen des Attributs um und versuchen Sie es erneut mit einem Kollegen.

>[!NOTE]
>
>Wenn Sie Tabellenspalten Feldern zuordnen (eine Feldzuordnungskarte mit _Source-Spalte_, _Zielfeld_, ein Konfidenzprozentsatz und eine _Liste Nicht zugeordnete_), ist dies der Lead-Importfluss und nicht die Erstellung von Zielgruppen. Siehe die [Import-Leads-Qualifikation](./skills.md#audiences-people).

## Regeln für eine vorhandene Liste bearbeiten {#edit-rules}

Wenn Sie Regeln für eine Liste ändern möchten, die Sie bereits haben, legt Coworker fest, welche Liste und welcher Bearbeitungsmodus verwendet werden soll:

* **Hinzufügen/Anhängen** (Standard für _„Regeln hinzufügen“_, _„Weitere Regeln hinzufügen“_) — neue Regeln werden mit den vorhandenen zusammengeführt.
* **Ersetzen** (Standard für _„Ersetzungsregeln“_, _„Regeln ändern in“_) — Neue Regeln ersetzen alle vorhandenen Regeln in der Liste.

„Mitarbeiter“ fasst zusammen, was angewendet wird, gibt klar an, ob es hinzugefügt oder ersetzt wird, und bittet Sie, dies zu bestätigen, bevor es einen Commit ausführt. Nach der Anwendung werden die Gesamtzahl der Regeln und die Anzahl der hinzugefügten oder ersetzten Elemente angezeigt.

>[!NOTE]
>
>Bearbeitungen verwenden einen zusammenführungsfähigen Pfad, sodass ein „Hinzufügen“-Vorgang Ihre vorhandenen Regeln nie unbeaufsichtigt überschreibt.

## Zielgruppenüberschneidung {#overlap}

Bitten Sie Ihren Kollegen, zwei Personenlisten zu vergleichen (z. B. _„Überschneidung zwischen „Webinar im 3. Quartal“ und „Unternehmenskonten“ anzeigen“_) und es wird eine Karte _Überschneidung von_&quot; gerendert:

* Ein Kopfzeilenabzeichen, das die Anzahl anzeigt: **&quot;{N} gemeinsam.“**
* Eine Statistikzeile mit der Gesamtzahl der Mitglieder jeder Liste und der Überschneidung als **„X% von A ・ Y% von B“.**
* Eine Mitgliedertabelle der Personen in beiden Listen mit einer Spalte **Name** und einer zweiten Spalte, die Sie steuern können - **E-Mail** (Standard), **Unternehmen** oder **Stellenbezeichnung** je nachdem, was Sie gefragt haben.
* Klicken Sie auf einen beliebigen Namen, um diese Person im Arbeitsbereich zu öffnen.
* Wenn es keine Überschneidungen gibt, sagt die Karte so deutlich: _Keine Mitglieder zwischen diesen beiden Listen.“_

**Einschränkungen:**

| Beschränkungen | Detail |
|---|---|
| **Tabellengröße** | Zeigt bis zu 200 Mitglieder; darüber hinaus wird _„Zeige 200 von N — bitte mich, die Abfrage zu verfeinern, um die Ergebnisse einzugrenzen.“_ |
| **Berechnung der Überschneidung** | Wird nach E-Mail-Adresse berechnet. Personen ohne E-Mail werden von der Schnittmenge ausgeschlossen. |
| **Listengröße** | Liest ungefähr die ersten ~1.000 Mitglieder jeder Liste aus. Bei größeren Listen sagt Ihnen der Kollege, dass die Ergebnisse unvollständig sind. |
| **Dynamische Listen als Entwurf** | Nicht vergleichbar: Eine Liste, die noch nicht veröffentlicht wurde, hat kein Live-Segment. Coworker fordert Sie auf, diese zuerst zu veröffentlichen oder stattdessen eine statische Liste zu verwenden. |

## QA-Validierung {#qa-validation}

Nach dem Erstellen oder Aktualisieren einer Liste bietet Coworker: _„Soll ich überprüfen, ob die Liste korrekt konfiguriert ist?“_ Wenn Sie akzeptieren, ruft es die Liste erneut ab und meldet die folgenden Prüfungen:

| nachprüfen | Ergebnis |
|---|---|
| Liste unter dem richtigen Programm/Ordner gefunden | Bestanden/Nicht bestanden |
| Die Filteranzahl entspricht dem angewendeten | _N_ Filter/fehlende Übereinstimmung |
| Personalization-Attribute vorhanden (falls enthalten) | Vorhanden/fehlend |
| Der Listenname entspricht den Anforderungen | Bestanden/Nicht bestanden |
| Geschätzte Mitgliederzahl | _count_ oder nicht zutreffend |

## Einschränkungen {#limitations}

| Einschränkung | Detail |
|---|---|
| **Static-list adaption von[!DNL Marketo Engage]** | Sie können eine [!DNL Marketo Engage] statische Liste (oder eine E-Mail oder ein anderes nicht gefiltertes Asset) nicht in eine Personenliste anpassen. Statische Listen sind explizite Mitglieder-IDs und können nicht als Filter ausgedrückt werden. Ein Mitarbeiter fragt stattdessen nach einer Smart-Liste oder einer Smart-Kampagne. |
| **Aktivitäts- und mitgliedsbasierte Filter** | Bei der Anpassung von [!DNL Marketo Engage] haben Filter wie _E-Mail wurde geöffnet_, _Besuchte Webseite_, _Formular wurde ausgefüllt_, _Mitglied der Liste_ und _Mitglied der Smart Campaign_ keine Entsprechung in der Personenliste und werden als „Keine Entsprechung gefunden“ zurückgegeben. |
| **Bedingungen auf Unternehmensebene** | Wenn möglich, in das nächste Attribut auf Personenebene übersetzt (Personenlisten werden mit Personenattributen betrieben) und mit geringer Konfidenz gekennzeichnet, wenn die Anpassung locker ist. |
| **Tief verschachtelte UND/ODER-Logik** | Komplexe verschachtelte Logik kann auf eine UND/ODER-Ebene der obersten Ebene reduziert werden. Ein Mitarbeiter merkt dies an, wenn es dazu kommt. |
| **Namenskollisionen** | Nicht automatisch aufgelöst - wenn der Name verwendet wird, bittet Sie der Mitarbeiter um einen anderen Namen, anstatt im Hintergrund ein Suffix anzuhängen. |
| **Genehmigung erforderlich** | Ein Mitarbeiter erstellt oder ändert erst dann eine Liste, wenn Sie auf **[!UICONTROL Fortfahren]** klicken, bestätigen oder eine eindeutige Genehmigung erteilen (_„Genehmigt“_, _„Sieht gut aus“_, _„Erstellen“_). |
| **Statische Momentaufnahme der Population** | Die Mitgliedschaft in statischen Listen, die anhand von Kriterien erstellt wurden, wird innerhalb weniger Minuten ausgefüllt - nicht sofort. |

