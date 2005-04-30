all: iswc2005.pdf

%.tex: %.rst
	rst2latex $*.rst >$*.tex

%.dvi: %.tex
	latex $*.tex

%.pdf: %.dvi
	dvipdf $*.dvi
