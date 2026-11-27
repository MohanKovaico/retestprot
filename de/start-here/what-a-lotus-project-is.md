---
title: Was ein Document360-Lotus-Projekt ist
internalDescription: Die Unterscheidung der Projekttypen und was es praktisch bedeutet, dass Git die Quelle der Wahrheit ist.
tags:
  - getting-started
  - git
  - writer
labels:
  - sample-content
seo:
  title: Was ein Document360-Lotus-Projekt ist
  description: Git als Quelle der Wahrheit, und was das für eine Autorin ändert.
display:
  toc: true
  outline: true
---

Document360 hat zwei Projekttypen. Dieses Projekt ist der Git-gestützte.

| | <span data-variable="productType">{{variable.productType}}</span> | <span data-variable="siblingType">{{variable.siblingType}}</span> |
| :--- | :--- | :--- |
| Quelle der Wahrheit | Ein Git-Repository | Document360 |
| Ein Artikel ist | Eine Markdown-Datei | Ein Datensatz in Document360 |
| Reihenfolge der Seiten | Eine Manifestdatei im Repository | Im Portal angeordnet |
| Wiederverwendbare Objekte | Dateien unter `.document360/` | Datensätze im Portal |
| Bearbeitung | <span data-variable="editorName">{{variable.editorName}}</span> oder ein beliebiger Editor | <span data-variable="editorName">{{variable.editorName}}</span> |

Beide werden unterstützt, und keiner ist ein Migrationsweg zum anderen.

## Was „Quelle der Wahrheit“ tatsächlich bedeutet

Drei Folgen, und das ist alles:

[d360]: # 'multi-level-list styles="decimal,lower-alpha"'

1. **Die Dateien sind der Inhalt.** Keine Kopie davon, kein Export davon. Wenn Sie das Repository
   klonen, haben Sie die Dokumentation.
2. **Die Historie ist Gits Historie.** Wer was wann geändert hat, ist ein Commit-Log — dasselbe Log,
   das Ihre Entwickler bereits zu lesen wissen.
3. **Alles, was eine Textdatei bearbeiten kann, kann Ihre Dokumentation bearbeiten.** Das Portal, Ihr
   eigener Editor, ein Skript oder der Pull Request einer Kollegin.

[d360]: # "/multi-level-list"

> [!NOTE]
> **Markdown ist die gespeicherte Form, kein Export**
>
> Die Datei auf der Platte ist das, was Document360 liest und schreibt. Es gibt keine separate
> Datenbankkopie, aus der das Markdown erzeugt wird, und genau das macht das Repository als Quelle
> der Wahrheit vertrauenswürdig.

## Für wen das passt

[d360]: # 'table border="all" striped="true"'

| Dieser Projekttyp passt zu Ihnen, wenn | Der andere passt womöglich besser, wenn |
| :--- | :--- |
| Ihre Doku neben Code liegt, der sich mit ihr ändert | Ihre Autorinnen nie ein Repository sehen wollen |
| Entwickler beitragen, oder beitragen sollten | Die Inhalte vollständig von einem Doku-Team geschrieben werden |
| Die Prüfung wie Code-Review aussehen soll | Die Genehmigung wie ein Workflow-Status aussehen soll |
| Sie bereits CI haben, durch die die Doku laufen soll | Sie keine Git-Praxis haben, auf der Sie aufbauen können |

[d360]: # "/table"

## Was sich nicht ändert

[d360]: # 'callout kind="success"'

> **Sie bekommen weiterhin eine Knowledge-Base-Site, Suche, Kategorien, Tags und Feedback**
>
> Git-gestützt zu sein ändert, wo die Inhalte gespeichert werden. Es verringert nicht, was Leser
> bekommen — das leserseitige Produkt ist dasselbe. Siehe [Ihre Leser](../your-readers/README.md).

[d360]: # "/callout"

## Der ehrliche Kompromiss

Ein Repository bringt Begriffe mit, die eine Autorin vorher nicht brauchte: Branches, Merges und
gelegentlich einen Konflikt. Document360 verbirgt das meiste davon für alle, die es verborgen haben
wollen, und im Rest dieses Abschnitts geht es um die Teile, die Sie doch erreichen.

> [!CAUTION]
> **Ein Git-gestütztes Projekt hat einen wirklich neuen Fehlerfall**
>
> Zwei Personen, die dieselbe Seite an verschiedenen Orten bearbeiten — was in einem editorzentrierten
> Produkt nicht passieren kann. [Wenn zwei Personen bearbeiten](../review-and-publishing/when-two-people-edit.md) ist die
> Seite dazu, und sie zu lesen lohnt sich vorher statt hinterher.

[d360]: # 'snippet name="deleteMe"'
