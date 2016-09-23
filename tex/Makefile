DIR = config.d
SRC = $(wildcard *.tex)
EXEC = cassandra_fes.pdf

.PHONY: clean all

all: $(EXEC)

$(EXEC) : cassandra_fes.tex $(SRC)
	pdflatex $^
	pdflatex $^
	pdflatex $^

clean:
