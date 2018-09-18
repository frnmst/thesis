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

TEX_SRC=presentazione

GITHUB_FRNMST_ROOT=https://raw.githubusercontent.com/frnmst

default: compile

all: default

help:
	@echo "default clean fullclean getsourcefiles compile fullcompile all help"

clean:
	@echo "Removing object files..."
	@rm -rfv *.pdf *.toc *.aux *.log *.cp *.cps *.fn* *.tp* *.lot* *.lol* *.lof* *.bbl *.blg *.dvi *.out* *.pyg* *.bcf *.run.xml
	@echo "Object files removed."

fullclean: clean
	@rm -rf _minted-$(TEX_SRC)

# -shell-escape is necessary for minted
compile: clean
	@pdflatex -shell-escape $(TEX_SRC).tex
	#@biber $(TEX_SRC)
	#@pdflatex -shell-escape $(TEX_SRC).tex
	@pdflatex -shell-escape $(TEX_SRC).tex

fullcompile: fullclean getsourcefiles compile

.PHONY: default clean fullclean getsourcefiles compile fullcompile all help

