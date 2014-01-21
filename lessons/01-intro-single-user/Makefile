default: clean 01-intro-single-user.pdf
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
	bibtex ${basename $@}

.PHONY: clean
clean:
	rm -f *.log *.aux *.blg *.pdf *.toc *.bbl *.out
