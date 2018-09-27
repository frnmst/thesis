# thesis

## Title

Integrazione di una applicazione web con strumenti per la statistica 

## Guidelines

http://www.unife.it/economia/economia/laurearsi/Guidaperlaredazionedellatesitriennale.pdf

http://www.unife.it/scienze/informatica/laurearsi

http://www.unife.it/studenti/immatricolazioni-e-iscrizioni/prova-finale/redazione-tesi

http://www.unife.it/scienze/informatica/laurearsi/FRONTESPIZIO_tipo.doc/at_download/file

https://users.dimi.uniud.it/~stefano.mizzaro/dida/come-non-scrivere-la-tesi.html

## LaTeX

### Settings

To be defined

### Dependencies

All Texlive packages

Bibtex

Minted

## Arch Linux package dependencies

    # pacman -S make texlive-most minted curl biber zathura zathura-pdf-mupdf

## Compile the thesis

### First time run

    $ cd src/thesis
    $ make fullcompile
    $ zathura tesi.pdf

### Test changes

If you have compiled at least once without cleaning you may run the following:

    $ make
    $ zathura tesi.pdf

## Compile the presentation

### First time run

    $ cd src/presentation
    $ make
    $ zathura presentazione.pdf

## Clean

    $ make clean

or

    $ make fullclean

## Notice

The thesis sent to the university corresponds to commit 
[1e4d15fb6c8f8023124a685b57176fe891d78d37](https://github.com/frnmst/thesis/tree/1e4d15fb6c8f8023124a685b57176fe891d78d37).

## License

thesis (c) by Franco Masotti <franco.masotti@student.unife.it>

thesis is licensed under a
Creative Commons Attribution-ShareAlike 4.0 International License.

You should have received a copy of the license along with this
work. If not, see <http://creativecommons.org/licenses/by-sa/4.0/>.

