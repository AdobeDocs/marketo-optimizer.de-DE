---
title: Content Governance für Vorlagen
description: Verwenden Sie Governance-Einstellungen in Marketo Optimizer, um Inhalte in E-Mail-Vorlagen auf Struktur- oder Komponentenebene zu sperren und so zu steuern, welche E-Mail-Autoren bearbeiten können.
TQID: 'https://experienceleague.adobe.com/0QZuUrqbF97W7c9yZzBYY39EC7DmbadKxXOJxjxDDy8'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 608
ht-degree: 0%

---


# Content Governance für Vorlagen

Mit der Inhaltssperrung können Vorlagenautoren Governance-Regeln definieren, die einschränken, welche Teile einer E-Mail-Vorlage geändert werden können, wenn die Vorlage in einer E-Mail verwendet wird. Dies hilft Marken- und Compliance-Teams, wichtige Design-Elemente wie Kopfzeilen, Logos und rechtliche Inhalte zu schützen und es Marketing-Teams zu ermöglichen, die Nachricht innerhalb der genehmigten Struktur anzupassen.

>[!NOTE]
>
>Das Sperren von Inhalten ist eine Funktion der Governance auf Editor-Ebene. Es steuert, was Autorinnen und Autoren im E-Mail-Design-Bereich bearbeiten können, verhindert jedoch nicht die über die API vorgenommenen Änderungen.

Nur Benutzer mit der Berechtigung **[!UICONTROL Inhaltsvorlagen verwalten]** können Governance-Einstellungen konfigurieren.

## Governance aktivieren {#enable}

>[!NOTE]
>
>In dieser Beta-Version werden nur E-Mail-Vorlagen unterstützt.

1. Öffnen Sie die Vorlage im Design-Bereich.
1. Klicken Sie auf der Arbeitsfläche auf die Komponente **[!UICONTROL Hauptteil]**, um sie auszuwählen.
1. Wählen Sie das _Einstellungen_ für das rechte Bedienfeld aus,
1. Schalten Sie **[!UICONTROL Governance]**.
1. Wählen Sie **[!UICONTROL Modus]** die Art der Governance aus, die Sie anwenden möchten:

   | Modus | Beschreibung |
   | ---- | ----------- |
   | **[!UICONTROL Inhaltssperrung]** | Bestimmte Strukturen oder Komponenten selektiv sperren. Entsperrte Bereiche bleiben von Autoren bearbeitbar. |
   | **[!UICONTROL Schreibgeschützt]** | Die gesamte Vorlage sperren. Autoren können sie auf eine E-Mail anwenden, aber keinen Teil ihres Inhalts ändern. |

1. Wenn Sie den Inhaltssperrmodus ausgewählt haben, können Sie weiter definieren, wie Benutzer mit der Vorlage interagieren können.

   Schalten Sie die Option Hinzufügen von Inhalten aktivieren ein und wählen Sie eine der folgenden Optionen:

   * **[!UICONTROL Zulassen von Struktur und Hinzufügen von]**: Benutzer können Strukturen zwischen vorhandenen hinzufügen und Inhaltskomponenten oder Fragmente innerhalb bearbeitbarer Strukturen hinzufügen.

   * **[!UICONTROL Nur Inhaltshinzufügen zulassen]** - Benutzer können Inhaltskomponenten oder Fragmente in bearbeitbaren Strukturen hinzufügen, aber keine Strukturen hinzufügen oder duplizieren.

### Sperren einer Struktur {#lock-structure}

1. Wählen Sie auf der Arbeitsfläche die Struktur (Spaltenlayout) aus, die Sie schützen möchten.
1. Aktivieren Sie in der rechten Leiste den Umschalter **[!UICONTROL Struktur sperren]**.

Alle Inhalte, die in einer gesperrten Struktur verschachtelt sind, werden automatisch gesperrt. Damit eine bestimmte Komponente innerhalb einer gesperrten Struktur bearbeitbar bleibt, wählen Sie die Komponente aus und aktivieren Sie **[!UICONTROL Bearbeitbar]** in der rechten Leiste.

Standardmäßig können Autoren eine gesperrte Struktur nicht löschen. Um das Löschen zuzulassen, aktivieren Sie die Option **[!UICONTROL Löschen zulassen]** in der rechten Leiste.

### Sperren einer Komponente {#lock-component}

Innerhalb einer bearbeitbaren Struktur können Sie einzelne Inhaltskomponenten sperren.

1. Wählen Sie die Komponente auf der Arbeitsfläche aus.
1. Aktivieren Sie in der rechten Leiste den **[!UICONTROL Inhalt sperren]** und wählen Sie den Sperrtyp aus:

   | Sperrtyp | Beschreibung |
   | --------- | ----------- |
   | **[!UICONTROL Gesperrt]** | Verhindert Inhalts- und Stiländerungen. Autoren können keinen Text bearbeiten oder das Erscheinungsbild der Komponente ändern. |
   | **[!UICONTROL Nur bearbeitbare Inhalte]** | Ermöglicht Autoren die Bearbeitung von Text und Inhalten, verhindert jedoch Stiländerungen wie Farben, Schriftarten und Abstände. |
   | **[!UICONTROL Bearbeitbar]** | Ermöglicht vollständige Änderungen auch innerhalb einer gesperrten Struktur. |

Standardmäßig können Autoren eine gesperrte Komponente nicht löschen. Um das Löschen zuzulassen, aktivieren Sie die Option **[!UICONTROL Löschen zulassen]** in der rechten Leiste.

### Hinzufügen von Inhalten zulassen {#allow-additions}

Bei Verwendung **[!UICONTROL Modus „Inhaltssperrung]** können Sie Autoren ermöglichen, der Vorlage neuen Inhalt hinzuzufügen, während gesperrte Elemente geschützt bleiben:

1. Aktivieren **[!UICONTROL Hinzufügen von Inhalten zulassen]**.
1. Wählen Sie aus, ob Autoren sowohl Strukturen als auch Inhaltskomponenten oder nur Inhaltskomponenten hinzufügen können.

## Gesperrte Elemente identifizieren {#identify}

Der **[!UICONTROL Navigationsbaum]** in der linken Leiste zeigt Schloss- und Stiftsymbole, die Autoren dabei helfen, schnell zu identifizieren, was sie ändern können und was nicht:

* Ein **Sperrsymbol** zeigt ein gesperrtes Element an.
* Ein **Bleistiftsymbol** zeigt ein Element an, das bearbeitet werden kann.

Um die Sichtbarkeit weiter zu verbessern, aktivieren Sie den Umschalter **[!UICONTROL Bearbeitbare Bereiche hervorheben]**, um bearbeitbare Bereiche von gesperrten Bereichen auf der Arbeitsfläche visuell zu unterscheiden.

## Aspekte

Governance-Einstellungen werden mit der Vorlage gespeichert. Jede E-Mail, die aus einer verwalteten Vorlage erstellt wird, übernimmt die Sperrkonfiguration zum Zeitpunkt der Anwendung. Die Aktualisierung der Governance-Einstellungen einer Vorlage hat keine Auswirkungen auf die zuvor damit erstellten E-Mails.
