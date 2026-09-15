#VENV = $(HOME)/.local/pipx/venvs/jupyterlab
#JUPYTER = $(VENV)/bin/jupyter
JUPYTER = jupyter
SRCS = $(wildcard *.ipynb)
PDFS = $(foreach src, $(SRCS), $(basename $(src)).pdf)
RUNALL = $(foreach src, $(SRCS), runnb-$(basename $(src)))

ALL = $(PDFS)

all : $(ALL)

runall : $(RUNALL)

runnb-% : %.ipynb
	$(JUPYTER) execute $*.ipynb

%.pdf : %.ipynb 
	$(JUPYTER) nbconvert --to latex $*.ipynb
	pdflatex $*.tex

clean :
	rm -rf *.png
	rm -rf *.pdf
	rm -rf *.out *.log *.dvi *.aux *.tex *_files




