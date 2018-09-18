#!/usr/bin/make -f

#
# Makefile
#
# thesis (c) by Franco Masotti <franco.masotti@student.unife.it>
#
# thesis is licensed under a
# Creative Commons Attribution-ShareAlike 4.0 International License.
#
# You should have received a copy of the license along with this
# work. If not, see <http://creativecommons.org/licenses/by-sa/4.0/>.
#

TEX_SRC=tesi

GITHUB_FRNMST_ROOT=https://raw.githubusercontent.com/frnmst

RSERVE_SANDBOX=$(GITHUB_FRNMST_ROOT)/rserve-sandbox/distro-package
RSERVE_SANDBOX_RSERV_CONF=$(RSERVE_SANDBOX)/Rserv.conf
RSERVE_SANDBOX_DOCKERFILE_IN=$(RSERVE_SANDBOX)/Dockerfile.in
RSERVE_SANDBOX_MAKEFILE=$(RSERVE_SANDBOX)/Makefile

default: compile

all: default

help:
	@echo "default clean fullclean getsourcefiles compile fullcompile all help"

clean:
	@echo "Removing object files..."
	@rm -rfv *.pdf *.toc *.aux *.log *.cp *.cps *.fn* *.tp* *.lot* *.lol* *.lof* *.bbl *.blg *.dvi *.out* *.pyg* *.bcf *.run.xml
	@echo "Object files removed."

fullclean: clean
	@rm -rf Rserv.conf Makefile.rserve Dockerfile.in
	@rm -rf _minted-$(TEX_SRC)

getsourcefiles:
	@curl -o Rserv.conf $(RSERVE_SANDBOX_RSERV_CONF)
	@curl -o Dockerfile.in $(RSERVE_SANDBOX_DOCKERFILE_IN)
	@curl -o Makefile.rserve $(RSERVE_SANDBOX_MAKEFILE)


# -shell-escape is necessary for minted
compile: clean
	@pdflatex -shell-escape $(TEX_SRC).tex
	@biber $(TEX_SRC)
	@pdflatex -shell-escape $(TEX_SRC).tex
	@pdflatex -shell-escape $(TEX_SRC).tex

fullcompile: fullclean getsourcefiles compile

.PHONY: default clean fullclean getsourcefiles compile fullcompile all help

