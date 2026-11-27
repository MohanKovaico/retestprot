---
title: Suche
internalDescription: Wie Leser Inhalte finden, was Autorinnen steuern, und das Lesen des Berichts erfolgloser Suchen.
tags:
  - readers
  - writer
labels:
  - sample-content
seo:
  title: Suche in einer Document360-Knowledge-Base
  description: Was eine Seite auffindbar macht und was bei Suchen zu tun ist, die nichts finden.
display:
  toc: true
  outline: true
---

Die meisten Leser durchstöbern Ihre Navigation nicht. Sie suchen, lesen eine Seite und gehen wieder.
Für diesen Leser zu schreiben ist eine andere Disziplin als ein Handbuch zu schreiben, das der Reihe
nach gelesen wird.

## Was eine Autorin steuert

[d360]: # 'table border="all" striped="true"'

| Hebel | Wo | Wirkung |
| :--- | :--- | :--- |
| Titel | `title` im Front Matter | Das stärkste Signal überhaupt |
| Überschriften | Der Artikeltext | Fast ebenso stark, und wie ein Leser überfliegt |
| SEO-Titel und -Beschreibung | `seo` im Front Matter | Was eine Suchmaschine anzeigt |
| Tags | `tags` im Front Matter | Gruppierung und Filterung |
| Ausschluss | `search.exclude` | Hält eine Seite aus den Ergebnissen |
| KI-Ausschluss | `search.excludeAi` | Hält eine Seite aus KI-Antworten |
| Externer Ausschluss | `search.excludeExternal` | Hält eine Seite aus der externen Suche |

[d360]: # "/table"

> [!IMPORTANT]
> **Betiteln Sie die Seite mit den Worten des Lesers, nicht mit Ihren**
>
> Er sucht „komme nicht rein“, nicht „Fehlerbehebung der Authentifizierung“. Er sucht „Rechnung“,
> nicht „Abgleich von Abrechnungsbelegen“. Ihr internes Vokabular ist das, was zwischen ihm und der
> Seite steht, die Sie längst geschrieben haben.

## Eine Seite schreiben, die antwortet

Vier Gewohnheiten, und sie kosten nichts:

[d360]: # 'multi-level-list styles="decimal,lower-alpha"'

1. **Antworten Sie im ersten Absatz.** Der Leser kam mitten im Problem an; der Hintergrund kann
   warten.
2. **Machen Sie jeden Abschnitt eigenständig.**
   1. Wer aus der Suche bei einer Überschrift ankommt, hat die darüber nicht gelesen.
   2. Weshalb „wie oben erklärt“ eine Wendung ist, die man auf den ersten Blick streichen sollte.
3. **Sagen Sie die Sache, dann erklären Sie sie.** Nicht umgekehrt.
4. **Nennen Sie, was die Seite nicht abdeckt**, und verlinken Sie auf das, was es tut.

[d360]: # "/multi-level-list"

> [!TIP]
> **Schreiben Sie die Überschrift als die Frage, die jemand eintippen würde**
>
> „Warum schlägt mein Import fehl?“ ist auffindbar. „Fehlerbehandlung im Import-Subsystem“ ist es
> nicht, so zutreffend es auch sein mag.

## Was im Index ist

Die Suche deckt den aktuellen Arbeitsbereich ab, so wie er auf dem verfolgten Branch live ist. Sonst
nichts.

| Im Index | Nicht im Index |
| :--- | :--- |
| Veröffentlichter Inhalt auf dem verfolgten Branch | Alles auf einem Arbeitsbranch |
| | Speicherstände auf einem Branch |
| | Unveröffentlichte Entwürfe |
| | Der Inhalt eines anderen Arbeitsbereichs |

Inhalt gelangt auf einem von zwei Wegen in den Index: Sie veröffentlichen ihn, oder er kommt mit
einem Import vom verfolgten Branch. Einen dritten Weg gibt es nicht, und darum ist eine Seite, die
existiert und nicht gefunden wird, fast immer eine Seite, die noch nicht veröffentlicht ist.

> [!IMPORTANT]
> **Ein Branch ist für die Suche mit Absicht unsichtbar**
>
> Das macht einen Arbeitsbranch für eine noch nicht angekündigte Funktion sicher. Es heißt auch, dass
> Sie die Auffindbarkeit erst prüfen können, wenn die Änderung live ist — prüfen Sie die Wortwahl
> also vor dem Zusammenführen, nicht danach.

## Fragen, die nichts gefunden haben

Die Liste der Fragen, auf die Leser nichts bekommen haben, ist die nützlichste redaktionelle Eingabe
überhaupt: jede davon eine Frage in den eigenen Worten eines Lesers, mit einer Zahl daneben.

| Was es bedeutet | Was zu tun ist |
| :--- | :--- |
| Es gibt keine Seite | Schreiben Sie sie |
| Eine Seite gibt es unter einem anderen Wort | Ändern Sie den Titel oder nehmen Sie das Wort des Lesers auf |
| Die Frage ist nicht beantwortbar | Ignorieren Sie sie |
| Es ist eine Frage für ein anderes Team | Geben Sie sie weiter |

[d360]: # 'callout kind="success"'

> **Sammeln Sie diese Fragen bewusst, denn hier sammelt sie niemand für Sie**
>
> Das Analytics-Modul gehört in der MVP-Auslieferung nicht zu diesem Projekttyp, die Liste muss also
> von dort kommen, wo Ihr Team Lesern ohnehin begegnet — vor allem aus der Supportwarteschlange. Eine
> halbe Stunde im Monat ersetzt jede Diskussion darüber, was als Nächstes zu dokumentieren ist.

[d360]: # "/callout"

## Eine Seite ausschließen

`search.exclude` hält eine Seite aus den Ergebnissen und lässt sie über einen Link erreichbar.
Legitime Verwendungen sind eng:

- [x] Eine Seite, die für ein Publikum existiert, das immer über einen Link kommt.
- [x] Eine veraltete Seite, die nur bleibt, damit eine alte Adresse auflöst.
- [ ] Nicht, um etwas zu verbergen, das Leser lieber nicht finden sollten — was nicht gelesen werden
      soll, sollte nicht veröffentlicht sein.

> [!CAUTION]
> **Eine ausgeschlossene Seite ist weiterhin öffentlich**
>
> Sie ist nicht auffindbar; sie ist nicht geschützt. Jeder mit der URL liest sie, und URLs wandern.

<details>
<summary>Wird Inhalt in einem Akkordeon indexiert?</summary>

Ja. Eingeklappter Inhalt wird indexiert und gefunden, und wer aus der Suche kommt, sieht ihn
geöffnet. Etwas in ein Akkordeon zu legen verbirgt es vor der Seite, nicht vor der Suche.

</details>

<details>
<summary>Warum erscheint meine neue Seite nicht in der Suche?</summary>

Prüfen Sie in dieser Reihenfolge: Sie ist auf dem verfolgten Branch veröffentlicht und liegt nicht
auf einem Arbeitsbranch oder als Entwurf; Sie suchen im Arbeitsbereich, zu dem sie gehört; sie ist
nicht `hidden`; sie trägt kein `search.exclude`; und es ist genug Zeit vergangen, damit der Index
sich erneuert. Die erste Prüfung erwischt die meisten Fälle.

</details>

[d360]: # 'snippet name="deleteMe"'
