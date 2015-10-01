##################################################################
# Makefile for LaTeX
##################################################################
# Use:
# make
# make clean
TEX:=$(shell ls *.tex)
FILES = *.tex Makefile *.bst *.pdf *.bib
FOLDER = StrongConvergenceOfTheExplicitLinearSteklovMethodForSDEsUnderNon-globallyLipschitzDrift/
TEXLIST = TexList.txt
FIGLIST = FigList.txt
CHORILIST = ChoriList.txt
OTHER = *~ *.aux *.dvi *.toc *.bbl *.blg *.out *.thm *.ps *.idx *.ilg *.ind *.tdo *.pdf *.tar.gz *.log *.spl *.synctex.gz
NAMETAR1:= $(shell date '+%Y%b%d_%H_%M')
NAMETAR = "$(NAMETAR1)_SecondSteklov.tar.gz"
NAMETARTEX = "$(NAMETAR1)_SecondSteklovTex.tar.gz"
NAMETARFIG = "$(NAMETAR1)_SecondSteklovFig.tar.gz"
NAMETARCHORI = "$(NAMETAR1)_Chorizo.tar.gz"
pdflatex: SecondArticle.tex
	pdflatex --synctex=1 SecondArticle.tex
	bibtex SecondArticle.aux
	pdflatex --synctex=1 SecondArticle.tex
	pdflatex --synctex=1 SecondArticle.tex

clean:
	rm -f $(OTHER)
#
tar:
	tar -cvf $(NAMETAR) -T $(TEXLIST)
#
tarFig:
	(cd ..&& tar -cvf $(NAMETARFIG) -T $(FIGLIST))
	
#
tarTex:
	(cd ..&& tar -cvf $(NAMETARTEX) -T $(TEXLIST))

tarChori:
	tar -cvf $(NAMETARCHORI) -T $(CHORILIST)
	
Chori:	Chorizo.sh
	sh Chorizo.sh
	pdflatex --synctex=1 StrongConvergenceLSMethod.tex
	bibtex StrongConvergenceLSMethod.aux
	pdflatex --synctex=1 StrongConvergenceLSMethod.tex
	pdflatex --synctex=1 StrongConvergenceLSMethod.tex
