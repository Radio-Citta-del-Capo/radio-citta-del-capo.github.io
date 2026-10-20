# Sito di Radio Città del Capo

Archivio online di Radio Città del Capo (Bologna, 1987–2021).
Indirizzo: https://radio-citta-del-capo.github.io/

Sito statico: una sola pagina (`index.html`) che legge i contenuti dai file nella cartella `data/`.
Non serve un database. Per aggiungere materiale si modificano i file di dati.
Ogni modifica salvata nel ramo `main` va online da sola dopo un paio di minuti.

## Struttura delle cartelle

```
index.html            la pagina del sito (grafica e funzionamento)
data/                 i contenuti
  audio.json          registrazioni audio
  video.json          collegamenti ai video
  novantaseietre.json i numeri del giornale, con sommario e colophon
  immagini.json       foto e disegni (61)
  persone.json        indice dei nomi e "da verificare"
  programmi.json      le trasmissioni
  palinsesti.json     gli otto palinsesti
  cronologia.json     i 53 eventi della cronologia
audio/                i file mp3
pdf/                  i numeri di Novantaseietre (versioni compresse)
assets/loghi/         i tre loghi e il logo ritagliato dalla testata del 1994
assets/copertine/     le copertine dei numeri
assets/immagini/      le immagini ritagliate (file grande + miniatura _t)
```

Il sito non funziona aprendo `index.html` con un doppio clic: va aperto da un indirizzo web.

## Aggiungere un audio

1. Metti il file mp3 nella cartella `audio/` (massimo 100 MB; per file più grandi usa archive.org e metti in `file` l'indirizzo diretto del mp3).
2. In `data/audio.json` aggiungi un blocco come questo, separato dagli altri da una virgola:

```json
{
 "id": "speciale-ustica-1",
 "titolo": "Speciale Ustica, prima parte",
 "data": "27 giugno 1990",
 "durata": "62:40",
 "file": "audio/speciale-ustica-1.mp3",
 "sezione": "Speciali e inchieste",
 "descrizione": "Breve descrizione.",
 "fonte": "Materiali Pilli"
}
```

Gli audio con la stessa `sezione` vengono raggruppati insieme.

## Aggiungere un video

In `data/video.json` compila `titolo`, `descrizione` e `link` (YouTube, Vimeo o archive.org).

## Aggiungere un numero di Novantaseietre

Metti il PDF in `pdf/`, la copertina in `assets/copertine/` e aggiungi un blocco in `data/novantaseietre.json` seguendo gli altri.
