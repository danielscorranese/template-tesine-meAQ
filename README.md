# template-tesine-meAQ
Modello LaTeX per la redazione delle tesine d'esame dei Corsi Accademici di Musica Elettronica del Conservatorio "A. Casella" de L'Aquila.

## Requisiti

Per compilare il PDF sono necessari:
- Distribuzione LaTeX completa (TeX Live, MiKTeX o simili)
- Motore `lualatex` **oppure** `xelatex`/`pdflatex` (consigliato l'uso di `lualatex`)
- Pacchetto `biber` per la gestione della bibliografia (BibLaTeX)

Su Windows si consiglia l’installazione di MiKTeX o TeX Live (via TeX Live Manager), includendo i pacchetti standard.

## File principali

- `main.tex` – file principale del documento
- `meAQ_Casella.sty` – stile personalizzato del Conservatorio
- `bibliografia.bib` – file BibTeX con le voci bibliografiche
- `figures/` – cartella con le immagini usate nel testo

Prima della compilazione, modifica in `main.tex` i seguenti comandi con i tuoi dati:

```tex
\newcommand{\TitoloTesina}{...}
\newcommand{\AutoreTesina}{...}
\newcommand{\CorsoEsame}{...}
\newcommand{\DataEsame}{...}
\newcommand{\CorsoAccademico}{...}
```

e inserisci/aggiorna le voci bibliografiche nel file `bibliografia.bib`.

## Compilazione da riga di comando

Posizionati nella cartella del progetto e lancia in ordine:

```bash
lualatex main
biber main
lualatex main
lualatex main
```

In alternativa, con `latexmk` (se installato):

```bash
latexmk -lualatex main.tex
```

Al termine troverai il file `main.pdf` pronto per la stampa.

## Compilazione con VS Code + LaTeX Workshop [SUGGERITO]

1. Installa l’estensione **LaTeX Workshop** dal marketplace di VS Code.
2. Apri la cartella del progetto in VS Code.
3. Apri `main.tex` (deve essere il file attivo).
4. Modifica `main.tex` e salva, il pdf viene generato automaticamente all'interno della cartella del progetto.

