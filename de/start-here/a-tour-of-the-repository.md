---
title: Ein Rundgang durch das Repository
internalDescription: Jede Datei und jeder Ordner in einem Lotus-Doku-Stamm, und was sie liest oder schreibt.
tags:
  - getting-started
  - git
  - structure
labels:
  - sample-content
seo:
  title: Ein Rundgang durch ein Document360-Lotus-Repository
  description: Wozu jede Datei und jeder Ordner in Ihrem Doku-Stamm da ist.
display:
  toc: true
  outline: true
---

So sieht Ihre Dokumentation auf der Platte aus.

Ihr Doku-Stamm ist der Ordner, den das Projekt laut Konfiguration liest — in diesem Beispiel `docs/`.

```text
docs/
├── d360.json                    das Navigationsmanifest
├── .document360/                Wiederverwendungsobjekte, mit dem Inhalt versioniert
│   ├── tags.json
│   ├── labels.json
│   ├── variables.json
│   └── snippets/
│       └── global/
│           └── <name>.md
└── en/                          ein Ordner je Sprache
    ├── <category>/
    │   ├── README.md            die eigene Seite der Kategorie
    │   └── <article>.md
    └── api-reference/           Ablage der API-Referenz, sofern das Projekt eine hat
        └── <slug>/
            ├── README.md
            └── openapi.yaml
```

## `d360.json`

Das Manifest, das jede Seite im Baum platziert. **Die Reihenfolge in der Datei ist die Reihenfolge in
der Navigation.**

```json
{
  "serializerVersion": 1,
  "languages": [{ "code": "en", "default": true }],
  "nodes": [
    {
      "paths": [{ "langs": ["en"], "path": "start-here/README.md" }],
      "children": [
        { "paths": [{ "langs": ["en"], "path": "start-here/your-first-change.md" }] }
      ]
    }
  ]
}
```

Jeder Knoten trägt `paths`, das Sprachen auf einen sprachrelativen Dateipfad abbildet, und optional
`children`. Ein Knoten mit Kindern ist eine Kategorie; einer ohne ist ein Artikel.

> [!IMPORTANT]
> **Eine Seite in der Navigation zu verschieben ist eine Änderung an dieser Datei, kein Verschieben
> auf der Platte**
>
> Der Ort der Datei und ihre Position im Baum sind getrennte Tatsachen. Sie können die gesamte
> Knowledge Base umsortieren, ohne eine einzige Datei umzubenennen — und das heißt auch: eine auf der
> Platte umbenannte Datei muss hier umbenannt werden, sonst fällt sie aus dem Baum.

## `.document360/`

Ihre Wiederverwendungsobjekte, als Dateien gespeichert, damit sie wie alles andere versioniert und
geprüft werden.

[d360]: # 'table border="all" striped="true"'

| Datei | Enthält |
| :--- | :--- |
| `tags.json` | Tag-Gruppen und Tags |
| `labels.json` | Label-Gruppen und Labels |
| `variables.json` | Variablen und ihre Werte |
| `snippets/global/<name>.md` | Ein Snippet, je eine Datei |

[d360]: # "/table"

Katalogeinträge tragen keine `guid`. Der Import-Abgleich erkennt ein Tag oder ein Label an seiner
`uniqueId`, eine Tag- oder Label-Gruppe an ihrem Namen und eine Variable an ihrem Namen.

> [!NOTE]
> **Das Glossar ist auch hier, nur anders geformt**
>
> Tags, Labels und Variablen sind Katalogdateien; ein Glossarbegriff ist eine Markdown-Datei je
> Begriff, im Glossarordner des Arbeitsbereichs, mit dem Begriff und seinen Synonymen im Front Matter
> und der Definition im Textkörper. Wie die Kataloge synchronisiert er sich in beide Richtungen.

## `en/` und die Sprachordner

Jeder Inhalt liegt unter einem Sprachordner. Hier `en/`, und je ein Nachbarordner pro zusätzlicher
Sprache, jeder mit denselben Pfaden.

## Kategorien und `README.md`

Ein Ordner ist eine Kategorie, und sein `README.md` ist die eigene Seite der Kategorie. Der `type` im
Front Matter dieser Datei sagt, um welche Art Kategorie es sich handelt:

| `type` | Die Kategorieseite ist |
| :--- | :--- |
| `page` | Eine Seite mit eigenem Inhalt |
| `index` | Eine Seite, die direkt zu ihrem ersten Artikel führt |
| *fehlt* | Ein schlichter Ordner ohne eigene Seite |

## `api-reference/`

Wo ein Projekt eine API-Referenz hat, liegt sie in `api-reference/<slug>/` als `README.md` plus genau
eine Spezifikationsdatei.

> [!TIP]
> **`api-reference/` ist Ablage, keine Position**
>
> Wo die Referenz *erscheint*, entscheidet `d360.json`, wie bei allem anderen. Der Name des Ordners
> sagt, was der Inhalt ist, nicht, wo Leser ihn finden — eine API-Referenz kann also überall in Ihrer
> Navigation stehen, auch mitten zwischen Ihren Anleitungen.

## Was Sie nicht finden werden

- Keine Build-Ausgabe. Die Knowledge-Base-Site erzeugt Document360, sie wird nicht eingecheckt.
- Keinen Datenbankexport. Die Dateien sind der Inhalt.
- Keine Sperrdatei und keinen Index, den Sie von Hand im Gleichklang halten müssten.

[d360]: # 'snippet name="deleteMe"'
