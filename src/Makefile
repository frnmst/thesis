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

QVM=$(GITHUB_FRNMST_ROOT)/qvm/master
QVM_SRC=$(QVM)/qvm
QVM_CONFIG=$(QVM)/configvmrc

RSERVE_SANDBOX=$(GITHUB_FRNMST_ROOT)/rserve-sandbox/distro-package
RSERVE_SANDBOX_RSERV_CONF=$(RSERVE_SANDBOX)/Rserv.conf
RSERVE_SANDBOX_DOCKERFILE_IN=$(RSERVE_SANDBOX)/Dockerfile.in
RSERVE_SANDBOX_MAKEFILE=$(RSERVE_SANDBOX)/Makefile

CPLINT_R=$(GITHUB_FRNMST_ROOT)/cplint_r/master
CPLINT_R_PL=$(CPLINT_R)/prolog/cplint_r.pl

SWISH=$(GITHUB_FRNMST_ROOT)/swish/master
GPR_R_PL=$(SWISH)/examples/inference/gpr_R.pl
COINMSW_PL=$(SWISH)/examples/inference/coinmsw.pl
COINMSW_R_PL=$(SWISH)/examples/inference/coinmsw_R.pl

default: compile

all: default

help:
	@echo "default clean fullclean getsourcefiles compile fullcompile all help"

clean:
	@echo "Removing object files..."
	@rm -rfv *.pdf *.toc *.aux *.log *.cp *.cps *.fn* *.tp* *.lot* *.lol* *.lof* *.bbl *.blg *.dvi *.out* *.pyg*
	@echo "Object files removed."

fullclean: clean
	@rm -rf qvm configvmrc Rserv.conf cplint_r.pl Makefile.rserve Dockerfile.in coinmsw.pl coinmsw_R.pl
	@rm -rf _minted-$(TEX_SRC)

getsourcefiles:
	@curl -o qvm $(QVM_SRC)
	@curl -o configvmrc $(QVM_CONFIG)
	@curl -o Rserv.conf $(RSERVE_SANDBOX_RSERV_CONF)
	@curl -o cplint_r.pl $(CPLINT_R_PL)
	@curl -o Dockerfile.in $(RSERVE_SANDBOX_DOCKERFILE_IN)
	@curl -o Makefile.rserve $(RSERVE_SANDBOX_MAKEFILE)
	@curl -o gpr_R.pl $(GPR_R_PL)
	@curl -o coinmsw.pl $(COINMSW_PL)
	@curl -o coinmsw_R.pl $(COINMSW_R_PL)


# -shell-escape is necessary for minted
compile: clean
	@pdflatex -shell-escape $(TEX_SRC).tex
	@bibtex $(TEX_SRC).aux
	@pdflatex -shell-escape $(TEX_SRC).tex
	@pdflatex -shell-escape $(TEX_SRC).tex

fullcompile: fullclean getsourcefiles compile

.PHONY: default clean fullclean getsourcefiles compile fullcompile all help

