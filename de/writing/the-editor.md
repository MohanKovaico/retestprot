---
title: Der Editor
internalDescription: Editor V3 in einem Lotus-Projekt — was er schreibt und warum die gespeicherte Form zählt.
tags:
  - editor
  - writer
labels:
  - sample-content
seo:
  title: Editor V3 in einem Document360-Lotus-Projekt
  description: Wie der Editor und die Markdown-Datei zueinander stehen.
display:
  toc: true
  outline: true
---

<span data-variable="editorName">{{variable.editorName}}</span> ist ein Blockeditor. Sie schreiben
Absätze, fügen Blöcke aus einem Menü ein, und was in Ihrem Repository ankommt, ist eine
Markdown-Datei.

## Die zwei Dinge, die man verstehen sollte

1. **Was Sie sehen, ist nicht, was gespeichert wird.** Der Editor zeigt Ihnen eine gerenderte
   Hinweisbox; die Datei enthält Markdown, das eine beschreibt. Beides ist richtig — es ist derselbe
   Inhalt in zwei Formen.
2. **Die gespeicherte Form ist kanonisch.** Es gibt genau eine Art, wie der Editor jeden Block
   schreibt, und er schreibt ihn jedes Mal so. Das macht Diffs lesbar und Hin-und-Rück-Wege sicher.

> [!IMPORTANT]
> **Eine von Hand in älterer Syntax geschriebene Datei wird beim ersten Speichern umgeschrieben**
>
> Document360s Markdown akzeptiert eine veraltete Fence-Form für Blöcke als *Eingabe* und überführt
> sie beim nächsten Speichern des Artikels in die kanonische Form. In einem Git-gestützten Projekt
> ist diese Überführung ein Commit — auf Inhalten, die niemand bearbeitet hat. Wenn Sie Markdown von
> Hand schreiben, schreiben Sie es so, wie der Editor es schreibt, dann wird hinter Ihrem Rücken
> nichts umgeschrieben.

## Wie Blöcke auf der Platte aussehen

Ein Block wird von einem Paar Markerzeilen begrenzt, die Markdown-Kommentare und damit für jeden
anderen Markdown-Renderer unsichtbar sind:

```markdown
> [!NOTE]
> **The title**
>
> The body of the callout.
```

> [!CAUTION]
> **Die Leerzeilen um diese Marker tragen Bedeutung**
>
> Sie sind keine Formatierung. Ein Marker ohne Leerzeile davor und danach wird nicht als Marker
> erkannt, und der Block wird zu wörtlichem Text. Wenn Sie Dateien von Hand bearbeiten, lassen Sie
> diese Zeilen in Ruhe.

## Aufklappbares ist schlichtes HTML

Akkordeons, Tabs und FAQ-Einträge werden aus `<details>` und `<summary>` gebaut und funktionieren
daher auch, wenn jemand die Datei auf GitHub liest statt in Ihrer Knowledge Base:

```markdown
<details>
<summary>The visible label</summary>

The content, with a blank line above it and below it.

</details>
```

> [!NOTE]
> **Auch diese Leerzeilen zählen**
>
> Ein `<details>`, dessen Inhalt unmittelbar in der Zeile nach `</summary>` beginnt, wird in manchen
> Markdown-Renderern als wörtlicher Text dargestellt. Der Editor schreibt sie richtig; verloren gehen
> sie beim Bearbeiten von Hand.

## Schreiben außerhalb des Portals

Jeder Editor geht. Was das Projekt von Ihrer Datei braucht, ist:

- [x] Front Matter oben, mit den Schlüsseln in kanonischer Reihenfolge.
- [x] Blöcke in der oben gezeigten Markerform.
- [x] Die Leerzeilen um Marker und innerhalb von `<details>`.
- [ ] Sonst nichts. Es gibt keinen Build-Schritt und kein Lint-Gate, das Sie von Hand erfüllen
      müssten.

> [!TIP]
> **Die Syntax lernt man am schnellsten, indem man einen Block einfügt und die Datei liest**
>
> Fügen Sie im Editor einen Tab-Block ein, speichern Sie ihn mit Save to branch, und sehen Sie sich an, was im Repository
> erschienen ist. Fünf Minuten davon schlagen jede Syntaxreferenz, diese eingeschlossen.

## Zwei Dinge, die der Editor nicht zulässt

| Konstrukt | Warum |
| :--- | :--- |
| Bedingte Inhalte für ein bestimmtes Publikum | Keine Leseroberfläche erzwingt das Publikum, der Inhalt wäre also für alle sichtbar — der Validator weist ihn zurück, statt Sie im Glauben zu lassen |
| Verwandte-Artikel-Links ohne stabile Id | Der Link braucht eine Identität, auf die er zeigt, und ein noch nicht importierter Artikel hat keine |

[d360]: # 'snippet name="deleteMe"'
