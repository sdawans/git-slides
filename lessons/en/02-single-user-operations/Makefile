default: clean 02a-single-user-operations.pdf 02b-ignoring-files.pdf 02c-rewriting-history.pdf
FIGURES=
#PAPER=letter
PAPER=a4

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
