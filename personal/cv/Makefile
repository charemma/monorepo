# Name der zu erstellenden PDF-Datei
PDF=Lebenslauf.pdf
# Name der LaTeX-Datei
TEX=Lebenslauf.tex
# Docker-Image-Name
IMAGE=latex-env

all: $(PDF)

# Ziel zum Erstellen des Docker-Images
build-image:
	docker build -t $(IMAGE) .

# Ziel zum Kompilieren des LaTeX-Dokuments
$(PDF): clean $(TEX) build-image
	rm -f $(PDF) *.aux *.log *.out *.toc *.lof *.lot
	docker run --rm -v `pwd`:/data -w /data $(IMAGE) lualatex -d $(TEX)

# Ziel zum Bereinigen der erzeugten Dateien
clean:
	rm -f $(PDF) *.aux *.log *.out *.toc *.lof *.lot


.PHONY: all build-image clean
