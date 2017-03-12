#!/usr/bin/make -f

#
# Makefile
#

TEX_SRC=tesi

default: compile

all: default

clean:
	@echo "Removing object files..."
	@rm -rfv *.pdf *.toc *.aux *.log *.cp *.cps *.fn* *.tp* *.lot* *.lof* *.bbl *.blg *.dvi
	@echo "Object files removed."

compile:
	@pdflatex $(TEX_SRC).tex
	@bibtex $(TEX_SRC).aux
	@pdflatex $(TEX_SRC).tex
	@pdflatex $(TEX_SRC).tex

.PHONY: default clean compile all

