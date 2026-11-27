---
title: Die Knowledge-Base-Site
internalDescription: Was Leser erhalten, wie es mit dem Repository zusammenhängt, und was konfiguriert statt geschrieben wird.
tags:
  - admin
  - readers
labels:
  - sample-content
seo:
  title: Die Knowledge-Base-Site in einem Document360-Lotus-Projekt
  description: Was Ihre Leser sehen und welche Teile davon im Repository liegen.
display:
  toc: true
  outline: true
---

Ihre Leser bekommen eine Dokumentationswebsite: Navigation links, der Artikel in der Mitte, die Suche
oben. Sie wird von Document360 aus dem Inhalt Ihres Repositorys erzeugt und liegt selbst nicht im
Repository.

## Was woher kommt

[d360]: # 'table border="all" striped="true"'

| Teil der Website | Kommt aus |
| :--- | :--- |
| Artikelinhalt | Den Markdown-Dateien |
| Navigation und Reihenfolge | `d360.json` |
| Titel, Icons, SEO-Metadaten | Dem Front Matter jedes Artikels |
| Für Leser sichtbare Tags | `.document360/tags.json` plus den `tags` jedes Artikels |
| Im Text eingesetzte Variablen | `.document360/variables.json` |
| Branding, Theme, Domain | Der Projektkonfiguration, nicht dem Repository |
| Zugriffsregeln, falls vorhanden | Der Projektkonfiguration, nicht dem Repository |

[d360]: # "/table"

> [!IMPORTANT]
> **Konfiguration ist kein Inhalt und reist nicht mit einem Branch**
>
> Ihr Logo, Ihre Domain und wer die Website lesen darf, sind Projekteinstellungen. Sie liegen nicht
> im Repository, sind also nicht Teil eines Pull Request und werden durch das Zurücknehmen eines
> Commits nicht wiederhergestellt. Behandeln Sie sie als eigene Entscheidungen mit eigenem Nachweis.

## Was Leser nie sehen

| Erreicht die Website nie |
| :--- |
| `internalDescription` im Front Matter |
| Labels |
| Private-Note-Blöcke |
| Als `hidden` markierte Artikel |
| Artikel mit `search.exclude`, in Suchergebnissen |
| Alles auf einem unveröffentlichten Branch |

> [!WARNING]
> **„Leser sehen es nicht“ ist nicht dasselbe wie „geheim“**
>
> Jeder Punkt oben liegt im Repository, also kann jeder ihn lesen, der das Repository lesen kann. Das
> ist meist ein größerer Kreis, als Sie denken, und wird irgendwann einen externen Mitarbeiter
> einschließen. Halten Sie echte Geheimnisse ganz aus der Dokumentation heraus.

## Mehrere Sprachen

Wo Ihr Projekt mehrere Sprachen hat, bekommen Leser die, nach der ihr Browser fragt, mit Rückfall auf
die Standardsprache, wo ein Artikel keine Übersetzung hat. Eine teilweise übersetzte Knowledge Base
bleibt navigierbar, statt Lücken zu zeigen.

> [!NOTE]
> **Ein Rückfall ist besser als eine Lücke und schlechter als eine Übersetzung**
>
> Leser, die eine englische Seite in einer sonst deutschen Website sehen, wissen, was passiert ist.
> Leser, die auf eine fehlende Seite stoßen, nicht. Der Rückfall verschafft Ihnen Zeit; er beseitigt
> nicht die Notwendigkeit.

## Vorschau, bevor Leser es sehen

Sie können sich eine Änderung so ansehen, wie ein Leser sie sehen wird, bevor es sonst jemand tut.

- Ein **Entwurf auf dem verfolgten Branch** wird mit der gewöhnlichen Vorschau der
  Knowledge-Base-Site angezeigt.
- Ein **Arbeitsbranch** wird so angezeigt, wie Leser ihn sähen, einschließlich Entwürfen, die Sie
  noch nicht auf den Branch gespeichert haben. Bilder, die nur auf dem Branch existieren, erscheinen
  ebenfalls.
- Ein **Freigabelink** schickt einen Artikel oder eine Kategorie eines Branch an eine prüfende Person
  außerhalb des Projekts. Er zeigt nur dieses eine Element, ohne Navigation drumherum.

> [!IMPORTANT]
> **Ein Freigabelink stirbt mit seinem Branch**
>
> Wird der Branch zusammengeführt, geschlossen, gelöscht oder beendet, funktioniert der Link nicht
> mehr — er fällt nie stillschweigend auf die Live-Seite zurück. Sagen Sie das externen Prüfenden,
> sonst halten sie Ihre Dokumentation für kaputt.

Die Vorschau ist für angemeldete Personen und folgt den bestehenden Vorschau-Zugriffsregeln. Inhalt,
der nur auf dem Branch existiert, erbt den Zugriff seiner nächstgelegenen übergeordneten Kategorie
und wird nicht gezeigt, wenn keine zutrifft.

> [!CAUTION]
> **Die Darstellung im Editor ist eine Vorschau des Inhalts, nicht der Website**
>
> Der Editor zeigt die Blöcke richtig. Er zeigt nicht Ihr Theme, nicht Ihre Navigation um die Seite
> herum und nicht, wie sich der Artikel auf einem Telefon liest. Für alles Layoutempfindliche schauen
> Sie auf die veröffentlichte Website statt in den Editor.

## Barrierefreiheit dessen, was Sie schreiben

Drei Dinge, die Ihnen gehören und nicht der Plattform, und die keine Konfiguration repariert:

[d360]: # 'multi-level-list styles="decimal,lower-alpha"'

1. **Alternativtext an jedem Bild.** Eine Abbildung, deren Unterschrift „der Einstellungsbildschirm“
   lautet und deren Alternativtext leer ist, ist für einen Screenreader unsichtbar.
2. **Überschriften in Reihenfolge**, ohne Ebenen zu überspringen. Überschriften sind, wie sich
   Screenreader-Nutzende über eine Seite bewegen.
3. **Linktext, der allein Sinn ergibt.** „Front Matter“ statt „hier klicken“, denn Links werden oft
   als Liste gelesen.

[d360]: # "/multi-level-list"

[d360]: # 'callout kind="success"'

> **Das sind auch die drei Dinge, die der Suche helfen**
>
> Alternativtext, geordnete Überschriften und aussagekräftige Links verbessern, wie eine Seite
> indexiert wird und wie ein Assistent daraus antwortet. Barrierefreiheit und Auffindbarkeit wollen,
> wie sich zeigt, dasselbe.

[d360]: # "/callout"

[d360]: # 'snippet name="deleteMe"'
