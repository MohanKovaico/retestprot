---
title: Branches und Prüfung
internalDescription: Was ein Branch für eine Autorin ist, wie die Prüfung abläuft und wer genehmigen darf.
tags:
  - git
  - publishing
  - writer
labels:
  - sample-content
seo:
  title: Branches und Prüfung in einem Document360-Lotus-Projekt
  description: Wo Ihre Arbeit liegt, bevor sie veröffentlicht ist, und wie sie genehmigt wird.
display:
  toc: true
  outline: true
---

## Ein Branch, aus Sicht einer Autorin

Ein Branch ist eine Kopie der Dokumentation, die nur Ihre Arbeit beeinflusst. Sie schreiben darauf,
speichern so oft Sie mögen, und nichts davon ist für Leser sichtbar.

[d360]: # 'table border="all" striped="true"'

| | Auf einem Branch | Veröffentlicht |
| :--- | :--- | :--- |
| Wer es sieht | Sie und jeder, der auf den Branch schaut | Leser |
| Wie oft Sie speichern | So oft Sie mögen | — |
| Halbfertige Arbeit | In Ordnung | Nicht in Ordnung |
| Umkehrbar | Ja, vollständig | Nur durch erneutes Veröffentlichen |

[d360]: # "/table"

> [!IMPORTANT]
> **Jede Rolle sieht den Branch, auf dem sie arbeitet**
>
> Das war einst vor Autorinnen verborgen, in der Annahme, sie wollten es lieber nicht wissen.
> Stattdessen wird es gezeigt, denn wer nicht weiß, wo die eigene Arbeit liegt, kann nicht beurteilen,
> ob sie sicher ist, und diese Unsicherheit kostet mehr als der Begriff.

## Die Bedienelemente auf einem Branch

Save to branch ist die Hauptschaltfläche; Create pull request, Ready to merge, Merge and publish und
Sync liegen unter **More branch actions**. Zu wissen, welche was tut, ist der größte Teil des
Arbeitens auf einem Branch.

[d360]: # 'table border="all" striped="true"'

| | Tut |
| :--- | :--- |
| **Save** | Behält einen Entwurf nur in Document360. Nichts erreicht Git |
| **Save to branch** | Überträgt alle Ihre Entwürfe auf diesem Branch als einen Commit. Veröffentlicht nie, indexiert nie, öffnet nie einen Pull Request |
| **Create pull request** | Öffnet nach einem ersten Speichern einen Pull-Request-Entwurf |
| **Ready to merge** | Macht aus dem Entwurf einen offenen Pull Request |
| **Merge and publish** | Führt in den verfolgten Branch zusammen und veröffentlicht |

[d360]: # "/table"

> [!IMPORTANT]
> **Save und Save to branch sind verschiedene Schaltflächen, und der Unterschied zählt**
>
> Save lässt Ihre Arbeit in Document360, wo kein fremder Checkout sie sehen kann. Save to branch ist
> die, die sie nach Git bringt. Wer immer nur Save benutzt, hat Arbeit, die an einem Ort existiert,
> und wird an dem Tag überrascht sein, an dem jemand fragt, warum der Branch leer ist.

## Prüfung als Pull Request

Die Änderung wird zu einem Pull Request in GitHub, geprüft dort, wo Ihre Entwickler ohnehin Code
prüfen. Das Menü zeigt Nummer und Status und verlinkt darauf.

Die Sync-Aktion trägt den Namen des verfolgten Branch, zum Beispiel **Sync with main**. Sie wird
angeboten, wenn der Branch hinter dem verfolgten Branch zurückliegt, wenn er mit ihm in Konflikt
steht und während ein Konflikt gelöst wird. Sie speichert zuerst Ihre ungespeicherten Entwürfe, holt die Änderungen des verfolgten Branch herein
und öffnet alle Überschneidungen in der Konfliktprüfung.

**Merge and publish** ist mit sichtbarer Begründung deaktiviert, wenn es nicht laufen kann: noch ein
Entwurf, braucht einen Sync mit main, eine erforderliche Prüfung oder ein Check ist nicht
durchgelaufen, oder Sie haben keine Berechtigung zu veröffentlichen.

> [!NOTE]
> **Document360 umgeht Ihren GitHub-Prüfprozess nie**
>
> Verlangt der verfolgte Branch eine Pull-Request-Prüfung, ist das Bearbeiten darauf gesperrt und
> Ihnen wird stattdessen ein Branch angeboten. Verlangt Ihr Repository Checks, wartet Merge and
> publish darauf. Die Regeln, die Ihre Entwickler für Code aufstellen, gelten unverändert für
> Dokumentation.

[d360]: # 'callout kind="success"'

> **Beides kann zugleich wahr sein**
>
> Eine Genehmigung innerhalb von Document360, die sich als Pull Request materialisiert, ist genau die
> Kombination, für die es diesen Projekttyp gibt. Eine Autorin bekommt ein Prüferlebnis, das fürs
> Schreiben gebaut ist; eine Entwicklungsorganisation bekommt einen Pull Request an der Stelle, an
> der sie einen erwartet.

[d360]: # "/callout"

## Was ein Prüfer tatsächlich prüfen sollte

[d360]: # 'multi-level-list styles="decimal,lower-alpha"'

1. **Stimmt es?** Die einzige Frage, die sich nicht automatisieren lässt.
2. **Steht es am richtigen Ort?** Ein richtiger Artikel in der falschen Kategorie ist schwer zu
   finden.
3. **Gehört er jemandem?** Ein Artikel ohne Eigentümer ist ein Artikel, den niemand aktualisieren
   wird.
4. **Was ändert er sonst noch?**
   1. Eine Snippet-Änderung ändert jeden Artikel, der es verwendet.
   2. Eine Manifest-Änderung ändert die Navigation.
   3. Eine Umbenennung ändert Adressen, die Leser bereits haben.

[d360]: # "/multi-level-list"

> [!CAUTION]
> **Ein kleiner Diff ist nicht dasselbe wie eine kleine Änderung**
>
> Eine Zeile in einem Snippet sind zwanzig Seiten. Ein umsortierter Knoten ist Ihre ganze Navigation.
> Lesen Sie, was der Diff *tut*, nicht wie lang er ist.

## Branches kurzlebig halten

> [!WARNING]
> **Ein Branch, der einen Monat offen ist, ist ein Merge-Konflikt mit Datum**
>
> Je länger ein Branch läuft, desto mehr bewegt sich der veröffentlichte Inhalt darunter. Kleine,
> schnell geprüfte Änderungen sind für alle leichter als vierzehn Tage Arbeit, die auf einmal
> ankommen — und das gilt für Dokumentation ebenso wie für Code.

## Zuordnung

Änderungen, die Sie vornehmen, werden Ihnen zugeordnet. Wo Document360 Ihre Git-Identität kennt, wird
der Commit dieser Identität zugeordnet; wo nicht, wird die Änderung innerhalb von Document360
trotzdem Ihnen zugeordnet und der Commit trägt stattdessen die Identität des Projekts.

> [!NOTE]
> **Verknüpfen Sie Ihre Git-Identität, wenn Ihr Name auf den Commits stehen soll**
>
> Es kostet einen Schritt und sorgt dafür, dass sich die Historie des Repositorys richtig liest — was
> den Entwicklern, die sie prüfen, wichtig ist und jedem, der später fragt, wer etwas geschrieben
> hat.

[d360]: # 'snippet name="deleteMe"'
