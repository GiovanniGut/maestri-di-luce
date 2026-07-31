# 📖 Guida ai Prompt d'Autore

## La grammatica del prompt fotografico nel 2026

Questa guida raccoglie i principi per costruire prompt fotorealistici con i generatori
attuali — **ChatGPT Images 2.0**, **Nano Banana 2 / Pro**, **Midjourney v8** — evitando
l'estetica "plastica" e le abitudini ereditate dai modelli di due anni fa.

---

## 1. Tre cose che sono cambiate

**Il negative prompt non esiste più (tranne su Midjourney).** ChatGPT e Gemini non lo
supportano. Scrivere `3d render, plastic skin, cartoon` nel testo non esclude nulla:
rischia anzi di evocare proprio quelle cose. La sostituzione è meccanica — **si riscrive
tutto in positivo**:

| ❌ Vecchio negative | ✅ Descrizione positiva |
|---|---|
| `no plastic skin` | pelle con pori visibili, lentiggini, linee sottili |
| `no 3d render, no cgi` | una fotografia vera, con la grana della pellicola |
| `no blur` | ogni piano nitido, dal primo piano all'orizzonte |
| `no smooth skin, no airbrushed` | volto non ritoccato, texture della pelle intatta |
| `no color` | bianco e nero, stampa ai sali d'argento |

**I flag `--ar` e `--no` valgono solo su Midjourney.** Su ChatGPT il formato si chiede a
parole o dal menu; su Gemini è un parametro dell'API (`aspect_ratio`), non testo. Un
`--ar 16:9` incollato in ChatGPT viene letto come testo e basta.

**La tag soup ha perso.** I modelli 2026 ragionano prima di disegnare e premiano la prosa
descrittiva. Non una lista di sostantivi separati da virgole, ma una scena raccontata:

> ❌ `pescatore, porto, nebbia, 35mm, tri-x, bianco e nero, alto contrasto`
>
> ✅ *Un pescatore anziano ripara le reti sulla banchina di un porto avvolto dalla nebbia
> del mattino. Ripreso con una Leica 35mm a f/5.6. Bianco e nero ad alto contrasto su
> Tri-X, la grana ben visibile, le silhouette che emergono dalla foschia.*

---

## 2. La struttura a sei livelli (che regge ancora)

L'ordine cambia poco; cambia la forma in cui lo si scrive.

1. **Soggetto** — chi o cosa, con dettagli fisici ed emotivi
2. **Azione e contesto** — cosa succede, dove, quando
3. **Ottica** — corpo macchina, focale, apertura (35mm, 85mm, f/1.4, f/64)
4. **Illuminazione** — qualità e direzione della luce (chiaroscuro, golden hour, flash diretto)
5. **Emulsione** — la chimica dell'immagine (Tri-X 400, Portra 400, Dye Transfer)
6. **Firma visiva** — ciò che rende riconoscibile uno stile, descritto in positivo

Su **Nano Banana 2** conviene comprimere: il modello perde vincoli quando il prompt si
allunga troppo. Su **Nano Banana Pro** e **ChatGPT** si può stratificare: ragionano prima
di generare e tengono tutti i vincoli insieme.

---

## 3. Nominare il maestro: quando conviene

Il diritto d'autore protegge le opere, non gli stili — citare un fotografo in un prompt
non riproduce nessuna sua fotografia. Il vincolo reale è di **policy**: ChatGPT rifiuta i
riferimenti a stili di **artisti viventi**; Gemini è più permissivo. Nell'archivio la
linea passa a metà: Adams, Cartier-Bresson, Lange, Newton, Maier, Leiter, Lindbergh,
Fan Ho, Güler e Salgado sono scomparsi; Wes Anderson, Crewdson, Depardon, Leibovitz,
Eggleston e McCurry sono viventi.

C'è però un argomento più forte del vincolo di policy. **Scrivere "in the style of Saul
Leiter" è la tag soup definitiva:** quattro parole che delegano tutto al modello e non
lasciano niente da regolare. La versione estesa è più lunga da scrivere, ma controllabile:

> *Ripreso attraverso un vetro rigato di pioggia, il soggetto per metà nascosto da una
> forma scura in primo piano; compressione da teleobiettivo che appiattisce la strada in
> strati; colore Kodachrome caldo e desaturato con un solo accento saturo — un ombrello
> rosso — sospeso nella foschia.*

Se il risultato non convince, qui sai esattamente quale frase togliere.

---

## 4. Riferimenti per immagine: la vera novità

È la risposta 2026 alla questione dello stile, e supera sia il nome sia la descrizione.

- **Nano Banana** accetta fino a **14 immagini di riferimento**: 10 oggetti, 4 personaggi,
  3 riferimenti di stile.
- **ChatGPT Images 2.0** mantiene la coerenza di personaggi e oggetti su un batch di fino
  a 8 immagini.
- **Midjourney v8** usa `--sref` (stile) e `--oref` (soggetto / omni reference).

⚠️ **ChatGPT e Gemini non scaricano immagini da un URL incollato nel prompt** — l'immagine
va allegata. Midjourney è l'eccezione: lavora proprio con i link.

---

## 5. Il testo dentro l'immagine, finalmente

GPT Image 2 dichiara circa il 99% di accuratezza sul testo; Nano Banana Pro è il primo
modello Google su cui *"scrivi SALDI in bianco grassetto sul prodotto"* produce
sistematicamente testo leggibile invece di scarabocchi decorativi. Insegne, targhe,
titoli e menù si possono chiedere e ottenere: non serve più aggirare il problema.

---

## 6. Template di esempio

### 🏔️ Il Sistema Zonale (Ansel Adams)

**Focus:** contrasto e nitidezza infinita.

> Un picco di granito emerge da un banco di nuvole in movimento. Ripreso con banco ottico
> di grande formato a f/64. Stampa monocroma ai sali d'argento con l'intera scala tonale
> intatta, dai neri profondi e materici ai bianchi puliti e dettagliati; ogni piano nitido,
> dalla roccia in primo piano alla cresta lontana; cielo scurito da un filtro rosso, così
> che le nuvole si stacchino come volumi scolpiti.

### 📷 Il Momento Decisivo (Henri Cartier-Bresson)

**Focus:** geometria spontanea, nessuna messa in scena.

> Un uomo salta una pozzanghera, colto a mezz'aria mentre il suo riflesso si specchia
> nell'acqua. Ripreso con Leica M3 e 50mm a f/8. Reportage 35mm in bianco e nero colto
> nell'istante in cui la geometria si compone; sola luce naturale disponibile; grana Tri-X
> ben visibile; il soggetto ignaro della macchina, le linee dello sfondo che cadono in un
> ordine non pianificato.

### 🌧️ Astrazione Urbana (Saul Leiter)

**Focus:** il soggetto nascosto, il colore poetico.

> Un ombrello rosso attraversa una strada di New York sotto la pioggia. Ripreso con
> teleobiettivo 135mm a f/4, attraverso un vetro appannato e rigato d'acqua; il soggetto
> per metà nascosto da una forma scura in primo piano; compressione che appiattisce la
> strada in strati sovrapposti; colore Kodachrome caldo e desaturato con un solo accento
> saturo sospeso nella foschia.

---

*"La fotografia è un segreto che parla di un segreto. Più ti dice, meno sai."*
— **Diane Arbus**
