PROJECT:=UncertaintyPrinciple

BUILD_DIR:=build

OUTPUT:=${BUILD_DIR}/${PROJECT}.pdf

FLAGS:=-xelatex -synctex=1 -interaction=nonstopmode -file-line-error -output-directory=${BUILD_DIR}

TEXS:=$(filter-out .fig.tex,$(wildcard *.tex))

FIGS_PDF:=$(addprefix ${BUILD_DIR}/,$(FIGS:.tex=.pdf))

default: ${BUILD_DIR} ${OUTPUT}
	@echo Makefile: Done!

${OUTPUT}: ${TEXS} ${FIGS_PDF}
	latexmk ${FLAGS} ${PROJECT}.tex 

${BUILD_DIR}/%.fig.pdf:%.fig.tex 
	latexmk ${FLAGS} $<

${BUILD_DIR}:
	mkdir -p ${BUILD_DIR}

run:default
	firefox file:///$(shell cygpath -a -m ${OUTPUT})

clean:
	rm ${BUILD_DIR}/${PROJECT}.*

output:
	@echo ${OUTPUT}