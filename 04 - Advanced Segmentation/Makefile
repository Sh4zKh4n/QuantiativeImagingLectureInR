# For Linux or any machines with gcc compiler
pandoc = /usr/local/bin/pandoc
Rscript = /usr/local/bin/Rscript

mainFile = AdvSegmentation
presFile = $(wildcard *.Rpres)
mdFile = $(mainFile).md

# make the updated script
all: printable

clean:
	/bin/rm printable.html 
    
printable:  $(presFile)
	$(Rscript) --vanilla -e "library(knitrBootstrap);printed<-T;knit_bootstrap('AdvSegmentation.Rpres',output='printable.html')"

rocco:  $presFile
	$(Rscript) --vanilla -e "library(knitr);printed<-T;rocco('AdvSegmentation.Rpres','rocco.html')"

pdfversion:  $mdFile
	$(pandoc) -o printable.pdf Segmentation.md
