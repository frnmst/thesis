#!/usr/bin/make -f

#
# Makefile
#

TEX_SRC=tesi

GITHUB_FRNMST_ROOT=https://raw.githubusercontent.com/frnmst

QVM=$(GITHUB_FRNMST_ROOT)/qvm/master
QVM_SRC=$(QVM)/qvm
QVM_CONFIG=$(QVM)/configvmrc

RSERVE_SANDBOX=$(GITHUB_FRNMST_ROOT)//rserve-sandbox/distro-package
RSERVE_SANDBOX_RSERV_CONF=$(RSERVE_SANDBOX)/Rserv.conf

CPLINT_R=$(GITHUB_FRNMST_ROOT)/cplint_r/master
CPLINT_R_PL=$(CPLINT_R)/prolog/cplint_r.pl

default: compile

all: default

help:
	@echo "default clean fullclean getsourcefiles compile fullcompile all help"

clean:
	@echo "Removing object files..."
	@rm -rfv *.pdf *.toc *.aux *.log *.cp *.cps *.fn* *.tp* *.lot* *.lol* *.lof* *.bbl *.blg *.dvi *.out* *.pyg*
	@echo "Object files removed."

fullclean: clean
	@rm -rf qvm configvmrc Rserv.conf cplint_r.pl
	@rm -rf _minted-$(TEX_SRC)

getsourcefiles:
	@curl -o qvm $(QVM_SRC)
	@curl -o configvmrc $(QVM_CONFIG)
	@curl -o Rserv.conf $(RSERVE_SANDBOX_RSERV_CONF)
	@curl -o cplint_r.pl $(CPLINT_R_PL)

# -shell-escape is necessary for minted
compile: clean
	@pdflatex -shell-escape $(TEX_SRC).tex
	@bibtex $(TEX_SRC).aux
	@pdflatex -shell-escape $(TEX_SRC).tex
	@pdflatex -shell-escape $(TEX_SRC).tex

fullcompile: fullclean getsourcefiles compile

.PHONY: default clean fullclean getsourcefiles compile fullcompile all help

