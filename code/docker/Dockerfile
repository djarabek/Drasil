FROM fedora:44

RUN dnf install -y --setopt=install_weak_deps=False \
    g++ stack git diffutils \
    graphviz inkscape \
    texlive-luahbtex texlive-base texlive-fontspec texlive-preprint texlive-amsmath texlive-amsfonts texlive-mathtools texlive-unicode-math texlive-tabularray texlive-booktabs texlive-caption texlive-svg texlive-float texlive-enumitem texlive-adjustbox texlive-filecontents texlive-biblatex texlive-bibtex \
    && dnf clean all \
    && rm -rf /var/cache/dnf

RUN curl -L -O https://github.com/rust-lang/mdBook/releases/download/v0.5.3/mdbook-v0.5.3-x86_64-unknown-linux-gnu.tar.gz \
    && tar zxvf mdbook-v0.5.3-x86_64-unknown-linux-gnu.tar.gz \
    && mkdir -p ~/.local/bin \
    && mv mdbook ~/.local/bin \
    && rm mdbook-v0.5.3-x86_64-unknown-linux-gnu.tar.gz

ENV LANG=C.UTF-8
ENV PATH=/root/.local/bin:$PATH
