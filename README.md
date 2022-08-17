# Introduction

This repository contains a LaTeX document, which can be used as a basis for documentation.

When using Visual Studio Code, ensure these extensions are installed:

* [Remote - Containers](https://code.visualstudio.com/docs/remote/containers) by Microsoft
* [LaTeX Workshop](https://github.com/James-Yu/LaTeX-Workshop) by James Yu

Alternatively, you can create this document by using XeTex and running the following command:

```bash
xelatex -shell-escape -output-directory target -interaction=nonstopmode main.tex
```

Note that if you build this locally, you will need the Pygments package to use minted. 
