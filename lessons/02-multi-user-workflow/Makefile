default: clean 02-multi-user-workflow.pdf 02-b-svn-git-migrations.pdf
FIGURES=
PAPER=letter
#PAPER=a4

%.pdf: %.fig
	fig2dev -L pdf $< $@

%.pdf:  $(FIGURES) %.bbl %.tex
	pdflatex ${basename $@}
	pdflatex ${basename $@}

%.bbl: %.tex
	cd ../../; git submodule update --init
	pdflatex ${basename $@}
	-bibtex ${basename $@}

.PHONY: clean
clean:
	rm -f *.log *.aux *.blg *.pdf *.toc *.bbl *.out
