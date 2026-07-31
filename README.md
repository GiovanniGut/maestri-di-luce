# 📸 Maestri di Luce | Atelier del Prompt AI

> "La fotografia è una risposta alla vita." — **Dorothea Lange**

**Maestri di Luce** è una camera oscura digitale per il ragionamento visivo: uno strumento
che traduce il DNA tecnico di 16 grandi fotografi in prompt pronti per i generatori di
immagini del 2026.

🔗 **[Apri l'Atelier](https://giovannigut.github.io/maestri-di-luce/)**

---

## Cosa fa

Scegli un maestro, definisci il soggetto in italiano, e l'app costruisce il prompt nella
forma che il motore di destinazione capisce davvero. Tre grammatiche diverse — perché nel
2026 i generatori non parlano più la stessa lingua.

| Motore | Cosa riceve | Note |
|---|---|---|
| **ChatGPT Images 2.0** (`gpt-image-2`) | prosa descrittiva, formato a parole | reasoning nativo, fino a 8 immagini coerenti, 2K |
| **Nano Banana 2** (`gemini-3.1-flash-image`) | prosa **condensata** | veloce ed economico; perde vincoli sui prompt lunghi |
| **Nano Banana Pro** (`gemini-3-pro-image`) | prosa lunga e stratificata | qualità studio, 4K, grounding su Search |
| **Midjourney v8** | keyword dense + flag | l'unico che usa ancora `--ar`, `--no`, `--sref`, `--oref` |

## La vista comparativa

Il pulsante **Confronta i quattro motori** apre lo stesso scatto scritto nelle quattro
grammatiche, affiancate, ciascuna con il conteggio parole e il proprio pulsante di copia.
Si aggiorna dal vivo mentre tocchi i parametri.

È il modo più rapido per vedere che le differenze non sono cosmetiche: Midjourney riceve
keyword separate da virgole e chiude con `--ar`, ChatGPT riceve prosa e il formato scritto
a parole, Nano Banana 2 riceve una versione volutamente più corta — perché sui prompt
lunghi perde i vincoli finali, mentre il Pro li tiene tutti.

## Le tre scelte che contano

**Motore di destinazione.** Non è un dettaglio cosmetico: `--ar` e `--no` funzionano
*solo* su Midjourney. Su ChatGPT e Gemini finiscono nel prompt come testo letterale e
peggiorano il risultato. L'app li emette solo dove servono.

**Citazione del maestro.** Tre livelli, con il secondo come default:

1. **Solo tecnica** — nessun riferimento all'autore.
2. **Grammatica del maestro** — il nome resta fuori, ma la sua firma visiva viene scritta
   per esteso. È l'opzione più controllabile: se il risultato non convince, sai quale
   parametro toccare.
3. **Citazione esplicita** — il nome entra nel prompt. L'app avvisa quando il maestro è
   vivente e il target è ChatGPT, che per policy rifiuta i riferimenti a stili di artisti
   viventi.

**Lingua.** Inglese (default, lessico tecnico più preciso) o italiano — i modelli 2026 lo
reggono bene.

## Allontanarsi dal maestro: il grafico si trascina

Il radar dei cinque assi — contrasto, saturazione, grana, realismo, messa in scena — non è
più decorativo: **trascini un vertice e il prompt cambia**. Il pentagono grigio tratteggiato
resta lì a segnare dove sta il maestro, la forma blu è dove sei arrivato tu.

La firma del maestro **non viene riscritta**: in coda al prompt compare una correzione
esplicita — *"Rispetto a questa base, correggi così: contrasto più morbido, gamma compressa
verso i grigi medi"*. Parti da Salgado, abbassi il contrasto, e ottieni Salgado meno duro
senza perdere tutto il resto.

Ogni asse ha due direzioni e due intensità. Sotto i 18 punti di scostamento non viene
scritto nulla: un trascinamento involontario non sporca il prompt.

## I tuoi assetti

**Salva assetto attuale** mette da parte l'intera calibrazione — maestro, tono, ottica,
apertura, luce, pellicola, formato, motore, citazione, lingua e la posizione dei cinque
assi — sotto un nome che scegli tu. La riapri con un clic e cambi solo il soggetto.

Soggetto e azione restano deliberatamente **fuori**: un assetto è un modo di guardare, non
uno scatto. Il chip si illumina di verde quando i parametri correnti corrispondono a un
assetto salvato, così vedi sempre se stai lavorando dentro o fuori da una tua calibrazione.

## Il cassetto delle immagini di riferimento

Trascini le foto nel riquadro e assegni a ciascuna un ruolo — **stile**, **personaggio**,
**oggetto** o **composizione**. I contatori mostrano quanto manca al limite del motore
scelto: Nano Banana accetta 3 riferimenti di stile, 4 personaggi e 10 oggetti, per un
massimo di 14 immagini, e l'app avvisa in rosso quando lo superi. Il prompt si aggiorna da
solo — *"In allegato: un riferimento di stile e due di personaggio…"* — perché al modello
va detto quante immagini riceve e con che ruolo.

**Le immagini non vengono spedite a nessuno.** Restano nel tuo browser come miniature
(lato lungo 160px, pochi kB l'una) e servono a ricordarti quali file allegare quando apri
ChatGPT o Gemini. Sopravvivono alla chiusura della pagina.

Midjourney fa eccezione: è l'unico che lavora con i link, quindi in quella modalità al
posto del riquadro compaiono i campi URL, che finiscono nel prompt come `--sref` e `--oref`.

## Niente negative prompt

ChatGPT e Gemini non supportano i negative prompt, e scrivere *"no plastic skin"* nel
testo rischia di evocare proprio ciò che vuoi escludere. Per questo ogni maestro ha una
**firma visiva in positivo**: non *"niente pelle di plastica"* ma *"pelle con pori
visibili, lentiggini e linee sottili"*. Le negazioni restano disponibili solo in modalità
Midjourney, dove `--no` funziona davvero.

## Chiave API (opzionale)

L'app funziona come generatore di prompt senza alcuna configurazione: costruisci, copi,
incolli. Se vuoi anche il pulsante **Ottimizza** — che riscrive il prompt in prosa
descrittiva — puoi inserire una chiave di **Anthropic (Claude)**, **Google (Gemini)** o
**OpenAI**. La guida è dentro l'app, nell'icona ⚙️.

> ⚠️ **Se una tua chiave Gemini ha smesso di funzionare, non è colpa tua.** Google ha
> sostituito le vecchie *standard key* con le *auth key*: dal 19 giugno 2026 quelle non
> ristrette vengono rifiutate, e da settembre 2026 lo saranno tutte. Creane una nuova su
> [AI Studio](https://aistudio.google.com/apikey) — quelle generate oggi sono già del tipo
> corretto.

La chiave resta nel `localStorage` del tuo browser e viaggia solo verso il fornitore che
hai scelto. Trattandosi di una pagina pubblica, usa una chiave dedicata con un tetto di
spesa basso. Il pulsante **Cancella chiave** la rimuove del tutto.

## 📚 Risorse

1. [**Guida ai Prompt d'Autore**](./Guida_Prompt_Fotografi.md) — la grammatica del prompt nel 2026
2. [**Infografica Interattiva**](https://giovannigut.github.io/maestri-di-luce/infographic_atelier.html) — anatomia del prompt

## 🛠️ Stack

Pagina statica singola. HTML5, Tailwind CSS, JavaScript ES6+, Chart.js.
Nessuna build, nessun backend, nessuna dipendenza da installare.

---

*Progetto sviluppato per elevare la cultura del prompt e la sensibilità visiva.*
