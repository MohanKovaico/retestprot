---
type: page
title: Schreiben
icon: ✍️
tags:
  - editor
  - writer
labels:
  - sample-content
seo:
  title: Schreiben in einem Document360-Lotus-Projekt
  description: Der Editor, die verfügbaren Blöcke und wie Sie Inhalte wiederverwenden.
display:
  toc: true
---

| Seite | Behandelt |
| :--- | :--- |
| [Der Editor](the-editor.md) | <span data-variable="editorName">{{variable.editorName}}</span> und was er auf die Platte schreibt |
| [Blöcke](blocks.md) | Jeden Block, den Sie einfügen können, und was daraus in Markdown wird |
| [Wiederverwendung](reuse.md) | Snippets, Variablen und Glossarbegriffe |

## Eine Sache, die man vorher wissen sollte

Ihr Artikel ist eine Markdown-Datei, und die Blöcke, die Sie einfügen, werden in einer bestimmten
Form in diese Datei geschrieben. Sie müssen nicht darüber nachdenken — aber wenn Sie einen Diff
ansehen oder eine Datei außerhalb des Portals bearbeiten, hilft es zu wissen, dass diese Form
beabsichtigt ist und dass ihr Einhalten verhindert, dass der Editor Ihre Datei später umschreibt.

> [!NOTE]
> **Schreiben Sie im Editor, lesen Sie das Markdown, wenn Sie neugierig sind**
>
> Niemand muss die Syntax lernen, um dieses Produkt zu benutzen. Diese Seiten zeigen sie nur deshalb,
> weil Sie in einem Git-gestützten Projekt früher oder später einen Diff sehen werden, und ein
> unerklärter Diff beunruhigt.

## Die Gestalt eines Artikels

Jeder Artikel besteht aus Front Matter und dann Inhalt:

```markdown
---
title: The article's title
tags:
  - writer
---

Content starts here.
```

Das Front Matter trägt die Metadaten — Titel, Tags, SEO, Anzeigeoptionen. Den vollständigen
Schlüsselsatz finden Sie unter Front Matter.

[d360]: # 'snippet name="deleteMe"'
