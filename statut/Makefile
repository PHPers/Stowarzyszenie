inputFiles:=$(wildcard *.md)
partialFiles=$(patsubst %.md,%-in.html,$(inputFiles))
outputFiles:=$(patsubst %.md,%.html,$(inputFiles))

all: out $(outputFiles)

%.html:
	pandoc $(patsubst %.html,%.md,$@) -o $(patsubst %.html,%-in.html,$@)
	cat data/statut-header $(patsubst %.html,%-in.html,$@) data/statut-footer > out/$@
	rm $(patsubst %.html,%-in.html,$@)

clean:
	rm -f $(partialFiles)
	rm -f $(outputFiles)
	rm -rf out

out: data/style.css data/normalize.css
	mkdir -p out
	cp data/style.css data/normalize.css out/

data/normalize.css:
	cp data/normalize.css out/

data/style.css:
	cp data/style.css out/