FROM ubuntu:22.04

# non interactive fontend for lcales
ENV DEBIAN_FORNTEND=noninteractive

# install texlive and utils
RUN apt update \
    && apt -y install --no-install-recommends \
    biber \
    curl \
    git \
    latexmk \
    locales \
    make \
    pandoc \
    procps \
    texlive \
    texlive-bibtex-extra \
    texlive-extra-utils \
    texlive-fonts-extra \
    texlive-latex-extra \
    python3-pip \
    && rm -rf /var/lib/apt/lists/*


# install Pygments for minted package
RUN pip3 install Pygments


# generating locales
RUN sed -i -e 's/# en_US.UTF-8 UTF-8/en_US.UTF-8 UTF-8/' /etc/locale.gen \
    && dpkg-reconfigure --frontend=noninteractive locales \
    && update-locale LANG=en_US.UTF-8

ENV LANGUAGE=en_US.UTF-8 \
    LANG=en_US.UTF-8 \
    LC_ALL=en_US.UTF-8

# installing cpanm & missing latexindent dependencies
RUN curl -L http://cpanmin.us \
    | perl - --self-upgrade \
    && cpanm Log::Dispatch::File YAML::Tiny File::HomeDir
