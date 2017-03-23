#!/usr/bin/make -f

#
# Makefile
#

TEX_SRC=tesi

GITHUB_FRNMST_ROOT=https://raw.githubusercontent.com/frnmst

QVM=$(GITHUB_FRNMST_ROOT)/qvm/master
QVM_SRC=$(QVM)/qvm
QVM_CONFIG=$(QVM)/configvmrc

default: compile

all: default

clean:
	@echo "Removing object files..."
	@rm -rfv *.pdf *.toc *.aux *.log *.cp *.cps *.fn* *.tp* *.lot* *.lol* *.lof* *.bbl *.blg *.dvi *.out*
	@rm -rf qvm configvmrc
	@rm -rf _minted-$(TEX_SRC)
	@echo "Object files removed."

getsourcefiles:
	@curl -o qvm $(QVM_SRC)
	@curl -o configvmrc $(QVM_CONFIG)

# -shell-escape is necessary for minted
compile: clean getsourcefiles
	@pdflatex -shell-escape $(TEX_SRC).tex
	@bibtex $(TEX_SRC).aux
	@pdflatex -shell-escape $(TEX_SRC).tex
	@pdflatex -shell-escape $(TEX_SRC).tex

.PHONY: default clean getsourcefiles compile all

