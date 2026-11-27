---
title: Feedback
internalDescription: Bewertungen und Kommentare von Lesern, wie man sie liest und wie daraus Arbeit wird.
tags:
  - readers
  - writer
labels:
  - sample-content
seo:
  title: Leser-Feedback in einer Document360-Knowledge-Base
  description: Was Leser Ihnen sagen können und was Sie damit anfangen.
display:
  toc: true
  outline: true
---

Leser können Ihnen sagen, ob eine Seite geholfen hat oder nicht. Es ist ein kleines Signal, und es
ist das einzige, das von der Person kommt, für die die Seite geschrieben wurde.

## Bewerten

Jeder Artikel kann ein Hilfreich/Nicht-hilfreich-Element zeigen, je Artikel über `feedback.voting` im
Front Matter konfiguriert.

> [!NOTE]
> **Bewerten ist standardmäßig an, Sie werden den Schlüssel also meist nicht geschrieben sehen**
>
> Front Matter hält boolesche Werte nur dort fest, wo sie vom gespeicherten Standard abweichen. Ein
> Artikel ohne `feedback`-Block hat das Bewerten aktiviert; eine Datei mit `voting: false` hat es
> bewusst abgeschaltet.

## Eine Wertung ehrlich lesen

[d360]: # 'table border="all" striped="true"'

| Was Sie sehen | Was es wahrscheinlich bedeutet |
| :--- | :--- |
| Hohe Wertung, viele Stimmen | Die Seite funktioniert. Lassen Sie sie in Ruhe |
| Niedrige Wertung, viele Stimmen | Reparieren Sie das zuerst — es versagt bei den meisten Menschen |
| Niedrige Wertung, wenige Stimmen | Vielleicht eine schlechte Seite, vielleicht drei verärgerte Leser |
| Überhaupt keine Stimmen | Niemand liest sie, oder niemanden kümmert es genug, um zu stimmen |

[d360]: # "/table"

> [!IMPORTANT]
> **Eine Wertung sagt Ihnen, wo Sie hinsehen sollen, nie, was Sie ändern sollen**
>
> „Nicht hilfreich“ von vierzig Lesern sagt, dass die Seite versagt, und nichts darüber, warum. Die
> Kommentare, das, was der Support zum selben Thema hört, und die Seite selbst zu lesen, als hätten
> Sie das Problem — das sagt Ihnen, warum.

## Kommentare

Wo Kommentare aktiviert sind, können Leser in eigenen Worten sagen, was falsch war, und das ist mehr
wert als jede Menge Bewertungen.

[d360]: # 'callout kind="success"'

> **Wer einen Kommentar schreibt, hat Ihnen auf eigene Kosten einen Gefallen getan**
>
> Die Person wollte etwas erledigen und hat innegehalten, um Ihnen zu sagen, dass die Dokumentation
> versagt hat. Behandeln Sie den Kommentar als Fehlermeldung und antworten Sie — wer eine Antwort
> bekommt, meldet wieder.

[d360]: # "/callout"

## Aus Feedback Arbeit machen

[d360]: # 'multi-level-list styles="decimal,lower-alpha"'

1. Lesen Sie den Kommentar und die Seite zusammen, in dieser Reihenfolge.
2. Entscheiden Sie, um welche Art von Versagen es sich handelt.
   1. **Falsch** — die Seite sagt etwas Unwahres. Heute reparieren.
   2. **Fehlend** — die Seite deckt den Fall nicht ab. Ergänzen.
   3. **Unauffindbar** — die Antwort war da und wurde nicht gesehen. Ein Struktur- oder Titelproblem.
   4. **Kein Dokumentationsproblem** — das Produkt verwirrt. Sagen Sie es dem, dem das Produkt
      gehört.
3. Nehmen Sie die Änderung als gewöhnliche geprüfte Änderung vor.
4. Wo jemand Kontaktdaten hinterlassen hat und die Korrektur ihm gilt, sagen Sie es ihm.

[d360]: # "/multi-level-list"

> [!CAUTION]
> **Die vierte Kategorie ist die, die falsch einsortiert wird**
>
> Eine Seite, die einen verwirrenden Bildschirm erklären muss, wird immer schlecht abschneiden, wie
> gut sie auch geschrieben ist. Manche Dokumentationsfehler sind Produktfehler im
> Dokumentationskostüm, und die Seite ein drittes Mal umzuschreiben behebt sie nicht.

## Was man mit Feedback nicht tun sollte

| Nicht | Weil |
| :--- | :--- |
| Eine Feedback-Wertung als Ziel setzen | Der schnellste Weg, sie zu heben, ist, nicht mehr zu fragen |
| Bewerten auf einer schlecht bewerteten Seite abschalten | Sie verlieren das Signal und die Seite bleibt schlecht |
| Nach einem einzelnen „nicht hilfreich“ umschreiben | Ein Leser ist kein Muster |
| Einen Kommentar wegen scharfen Tons ignorieren | Ein verärgerter Leser hat bei den Fakten meist trotzdem recht |

[d360]: # 'callout kind="error"'

> **Streiten Sie nie in einem öffentlichen Kommentar mit einem Leser**
>
> Auch dann nicht, wenn er sich bei den Fakten irrt. Reparieren Sie, was reparierbar ist, antworten
> Sie schlicht, und tragen Sie die Meinungsverschiedenheit dorthin, wo sie nicht unter Ihrer
> Dokumentation veröffentlicht wird.

[d360]: # "/callout"

## Eine vierteljährliche Gewohnheit

[d360]: # 'divider style="dashed"'

---

- [ ] Jede Seite mit fallender Wertung, gelesen wie ein Leser sie läse.
- [ ] Jeder Kommentar des Quartals, in die vier Kategorien oben einsortiert.
- [ ] Die Fragen, die der Support beantwortet hat und die eine Seite hätte beantworten sollen.
- [ ] Alles, was im nächsten Quartal ein `status.expiresAt` trägt.

[d360]: # 'snippet name="deleteMe"'
