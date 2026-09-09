---
title: Abgeleitete Personas
description: Verwenden Sie abgeleitete Personas in Marketo Optimizer, um Personenlisten und Journey-Pfade auszuwählen. Erfahren Sie mehr über die standardmäßigen Rollenzuordnungen und den Filter „Abgeleitete Rolle“.
TQID: 'https://experienceleague.adobe.com/5HAnnC6dbU-sE9dzBWs479z1H4LlNSkhhoNSrQxSfqI'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 625
ht-degree: 0%

---

# Abgeleitete Personas

Die Persona-Klassifizierung transformiert Kundenrohdaten in semantisches Käuferverständnis, mit dem KI Kontext generieren und personalisierte Entscheidungen über jeden Kanal und jede Journey hinweg fördern kann. Dieses einheitliche Profil bietet folgende Möglichkeiten:

* _Journey-Verzweigung_ - Aufspaltung von Routenleitern nach Rolle, Interaktionstiefe und Rolle
* _Journey-Schlichtung_ - Bestimmt, zu welchem Nurture-Journey ein Lead derzeit gehört, wodurch Nachrichtenkollisionen über gleichzeitige Programme hinweg vermieden werden
* _Inhaltspersonalisierung_ - Inhalte, die rollenspezifische Erzählungen sind („für einen Manager“ oder „für einen Anwender„)
* _Sales Qualifier Context_ - Business Development Representatives (BDRs) erhalten eine Zusammenfassung auf einem Bildschirm, die die Identität der Person, ihre Interessen und ihre aktuelle Phase auf der Käufer-Journey zeigt

## Standard-Personas {#default-ersonas}

Für die Beta-Version von Marketo Optimizer werden die folgenden Standardpersonas entsprechend dem Auftragstitelattribut definiert:

| Persona | Stellenbezeichnungen |
| ------- | ---------- |
| [!UICONTROL CXO/EVP] | CEO, CIO, CTO, CMO, CFO, Executive Vice President of Strategy |
| [!UICONTROL SVP/VP] | SVP Marketing, VP Sales, SVP Operations, VP Product, VP IT |
| [!UICONTROL Senior Manager/Manager] | Senior Marketing Manager, IT Manager, Operations Manager, Sales Manager, HR Manager |
| [!UICONTROL Einzelner Beitragender] | Kundenbetreuer, Software-Ingenieur, Marketing-Spezialist, Customer Success-Vertreter |
| [!UICONTROL Analyst] | Business Analyst, Data Analyst, Market Research Analyst, Financial Analyst, Operations Analyst |
| [!UICONTROL Entwicklerin/Entwickler] | Frontend-Entwickler, Backend-Entwickler, Full-Stack-Entwickler, Mobile-App-Entwickler, DevOps-Ingenieur |
| [!UICONTROL Professionelles Personal] | HR Specialist, Legal Counsel, Compliance Officer, Project Manager, Procurement Specialist |
| [!UICONTROL Berater] | Unternehmensberater, IT-Berater, Business Process Consultant, Marketing Consultant |
| [!UICONTROL Sonstige] | Branchenspezialist, unabhängiger Berater, freiberuflicher Berater, Fachexperte |

>[!NOTE]
>
>In der kommenden Version zur allgemeinen Verfügbarkeit können Sie jede dieser Standardrollen entsprechend den Anforderungen Ihres Unternehmens bearbeiten. Es unterstützt auch benutzerdefinierte Persona-Definitionen und -Zuordnungen.

## Nach abgeleiteter Persona filtern {#derived-persona-filter}

[!DNL Marketo Optimizer] leitet für jeden Personendatensatz eine Rolle ab, indem die Datensatzattribute mit den definierten Rollen verglichen werden. Sie können das abgeleitete Ergebnis - die _abgeleitete Persona_ - als Filter verwenden, wenn Sie die Audience für eine Personenliste definieren oder eine Personen-Journey segmentieren.

Der _[!UICONTROL Abgeleitete Persona]_-Filter wird im Filterbedienfeld unter der Kategorie **[!UICONTROL Personenattribute]** angezeigt.

### Personenlisten {#people-lists}

Beim Verwalten von Mitgliedern in einer [statischen Personenliste](./people-lists.md#static-lists) oder Definieren von Regeln für eine [dynamische Personenliste](./people-lists.md#dynamic-lists) können Sie nach _Abgeleitete Persona_ filtern, um alle Personen anzusprechen, deren Attribute mit einer bestimmten konfigurierten Persona übereinstimmen.

![Abgeleitete Rollenfilterung für eine Personenliste](./assets/derived-persona-filter-people-list.png){width="750" zoomable="yes"}

**Statische Liste - Mitglieder hinzufügen**

1. Öffnen Sie die statische Liste und klicken Sie **[!UICONTROL oben]** auf „Personen hinzufügen“.

1. Erweitern Sie im Filterdialogfeld **[!UICONTROL Personenattribute]** und ziehen Sie **[!UICONTROL Abgeleitete Persona]** auf die Arbeitsfläche.

1. Wählen Sie in der Filterbedingung **[!UICONTROL ist]** und wählen Sie eine oder mehrere Rollen aus der Liste aus.

1. Klicken Sie **[!UICONTROL Fertig]**, um den Filter anzuwenden und passende Personen für die Liste zu qualifizieren.

**Dynamische Liste - Festlegen von Mitgliedschaftsregeln**

1. Öffnen Sie die dynamische Liste und wählen Sie die Registerkarte **[!UICONTROL Regeln]** aus.

1. Klicken Sie **[!UICONTROL Regeln bearbeiten]**.

1. Erweitern Sie im Filterdialogfeld **[!UICONTROL Personenattribute]** und ziehen Sie **[!UICONTROL Abgeleitete Persona]** auf die Arbeitsfläche.

1. Wählen Sie in der Filterbedingung **[!UICONTROL ist]** und wählen Sie eine oder mehrere Rollen aus der Liste aus.

1. Klicken Sie **[!UICONTROL Fertig]**, um die Regel zu speichern.

   Die Mitgliedschaft wird automatisch aktualisiert, wenn Personendatensätze anhand der Regel ausgewertet werden.

### Personen-Journey {#person-journeys}

Wenn Sie die Segmentierung für eine Personen-Journey in einem [_Aufspaltungs-_-Knoten](../marketing/split-merge-paths-nodes.md) konfigurieren, können Sie eine abgeleitete Rolle als Personenprofilfilter verwenden, um zu steuern, welche Personen in den Journey-Pfad eintreten.

![Abgeleitete Rollenfilterung für eine Bedingung eines aufgeteilten Pfads](./assets/derived-persona-filter-split-path.png){width="750" zoomable="yes"}

1. Klicken Sie auf **[!UICONTROL Arbeitsfläche Journey auf]** Knoten „Pfade aufteilen“.

1. Klicken Sie im Bedienfeld Knoteneigenschaften rechts auf **[!UICONTROL Bedingung anwenden]** oder **[!UICONTROL Bedingung bearbeiten]** für einen Pfad.

1. Erweitern Sie im Filterdialogfeld **[!UICONTROL Personenattribute]** und ziehen Sie **[!UICONTROL Abgeleitete Persona]** auf die Arbeitsfläche.

1. Wählen Sie in der Filterbedingung **[!UICONTROL ist]** und wählen Sie eine oder mehrere Rollen aus der Liste aus.

1. Klicken Sie **[!UICONTROL Fertig]**, um den Filter für den Pfad zu speichern.

