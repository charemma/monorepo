FROM debian:latest

ENV TEXMFVAR=/var/lib/texmf

RUN apt-get update && apt-get install -y \
    texlive-luatex \
    texlive-fonts-recommended \
    texlive-fonts-extra \
    texlive-latex-extra \
    texlive-lang-german \
    fonts-lato \
    && rm -rf /var/lib/apt/lists/*

RUN fc-cache -fv \
    && luaotfload-tool --update --force \
    && chmod -R a+rwX /var/lib/texmf

WORKDIR /data
