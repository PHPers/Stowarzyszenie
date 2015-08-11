all: statut.html


statut.html: statut.md data/statut-header.html data/statut-footer.html data/style.css
	pandoc statut.md -o statut-in.html
	cat data/statut-header.html statut-in.html data/statut-footer.html > statut.html

clean:
	rm -f statut-in.html
	rm -f statut.html
	rm -rf out

out: statut.html
	mkdir -p out
	cp statut.html out/
	cp data/style.css data/normalize.css out/
