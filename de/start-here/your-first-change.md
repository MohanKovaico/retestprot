---
title: Ihre erste Änderung
internalDescription: Eine Seite bearbeiten und zu den Lesern bringen, aus dem Portal und aus einem Klon.
tags:
  - getting-started
  - git
  - writer
labels:
  - sample-content
seo:
  title: Nehmen Sie Ihre erste Änderung in einem Document360-Lotus-Projekt vor
  description: Bearbeiten Sie diese Seite, lassen Sie die Änderung prüfen und veröffentlichen Sie sie.
display:
  toc: true
  outline: true
---

Dieses Projekt versteht man am besten, indem man etwas darin ändert. Diese Seite lässt sich gefahrlos
ändern, denn sie ist Beispielinhalt und niemand verlässt sich auf sie.

## Aus dem Portal

[d360]: # 'multi-level-list styles="decimal,lower-alpha"'

1. Öffnen Sie diesen Artikel in <span data-variable="editorName">{{variable.editorName}}</span>.
2. Ändern Sie einen Satz. Hängen Sie zum Beispiel Ihren Namen an diesen hier.
3. Speichern Sie, dann wählen Sie Save to branch.
   1. Speichern behält einen Entwurf in Document360. Save to branch committet die Markdown-Datei auf den Branch.
   2. Der Branch, auf dem Sie arbeiten, wird während des Bearbeitens angezeigt.
4. Führen Sie die Änderung durch die Prüfung und veröffentlichen Sie sie dann.

[d360]: # "/multi-level-list"

> [!IMPORTANT]
> **Save to branch schreibt eine Datei; Veröffentlichen ist ein eigener Akt**
>
> In einem editorzentrierten Produkt fallen diese beiden oft zusammen. Hier nicht: Save to branch
> überträgt Ihre Arbeit auf einen Branch, und Leser sehen nichts, bis die Änderung veröffentlicht
> ist. Dieser Abstand ist der Sinn des Produkts.

## Aus einem Klon, wenn Ihnen das lieber ist

```bash
git clone <Ihr Repository>
cd docs/en/start-here
# bearbeiten Sie your-first-change.md mit dem Werkzeug Ihrer Wahl
git commit -am "Docs: first change"
git push
```

Document360 liest die Änderung, und der Artikel aktualisiert sich. Am Bearbeiten im eigenen Editor
ist nichts zweitrangig — die Datei, die Sie bearbeitet haben, *ist* der Artikel.

> [!TIP]
> **Beide Wege schreiben dieselbe Datei**
>
> Eine im Portal bearbeitete Seite und eine in Vim bearbeitete Seite erzeugen dasselbe Markdown. Es
> gibt kein „Portalformat“ und keinen Konvertierungsschritt, und genau das macht gemischte Teams
> praktikabel.

## Wie eine Änderung in Git aussieht

```diff
-The best way to understand this project is to read about it.
+The best way to understand this project is to change something in it.
```

Eine Änderung von einem Satz ist ein Diff von einer Zeile. Das ist der wichtigste praktische Grund,
warum das kanonische Markdown zählt: Ein Prüfer sieht den geänderten Satz und keine neu formatierte
Datei.

> [!CAUTION]
> **Formatieren Sie keine Absätze um, die Sie nicht bearbeitet haben**
>
> Einen Absatz auf eine andere Zeilenlänge umzubrechen macht aus einer Korrektur von einem Wort einen
> Diff, den niemand lesen kann. Wenn Ihr Editor beim Speichern umformatiert, schalten Sie das für
> Markdown ab.

## Was Sie als Nächstes versuchen können

- [ ] Ändern Sie einen Satz und beobachten Sie den Diff.
- [ ] Fügen Sie eine Hinweisbox ein, über das Blockmenü statt durch Tippen der Syntax.
- [ ] Schieben Sie diesen Artikel über seine Geschwister — beachten Sie, dass das `d360.json`
      bearbeitet, nicht die Datei.
- [ ] Löschen Sie diesen Artikel. Er ist Beispielinhalt, und ihn zu löschen ist eine völlig
      legitime erste Änderung.

[d360]: # 'callout kind="success"'

> **Wenn Sie diese vier können, können Sie dieses Projekt führen**
>
> Alles Weitere in dieser Dokumentation ist Detail obendrauf: bearbeiten, prüfen, veröffentlichen.

[d360]: # "/callout"

## Wohin als Nächstes

[Schreiben](../writing/README.md), wenn Sie gleich mit dem Schreiben loslegen wollen;
Struktur, wenn Sie lieber zuerst verstehen möchten, wie der Baum aufgebaut ist.
Beide sind so geschrieben, dass sie in jeder Reihenfolge lesbar sind.

[d360]: # 'snippet name="deleteMe"'
