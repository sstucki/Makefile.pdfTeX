Makefile.pdfTeX – build LaTeX projects using GNU/Make
=====================================================

This repo contains a pair of scripts to build TeX projects using
GNU/Make and pdfTeX.  It provides a generic Makefile for LaTeX
projects (`Makefile.pdfTeX`) and a simple shell script (`texdeps.sh`)
for tracking dependencies between TeX sources and other files, such as
includes, bib-files, local style files, etc.  The dependency tracker
supports reasonably complex project setups such as nested includes and
TeX source files organized in nested sub-directories.

To work correctly, the scripts require a POSIX-compatible shell
(e.g. bash) and GNU/Make to be installed.  They use pdfTeX by default,
but can probably be used with other TeX engines as well.


*** Usage ***

Normally, it should be sufficient to just copy the two files
`Makefile.pdfTeX` and `texdeps.sh` somewhere in your project and
create a top-level Makefile containing the lines

```
PDFS = <file1>.pdf <file2>.pdf <etc.>
MAKEDEPS = <path to>/texdeps.sh
include <path to>/Makefile.pdfTeX
```

where `<file1>.pdf <file2>.pdf <etc.>` is a space-separated list of
PDF files to build and `<path to>` should be replaced by the actual
path to the scripts.  The scripts assume that there is a main TeX
source file for each of the PDFs, i.e. `<file1>.tex`, `<file2>.tex`
and so on.

The make variables `LATEX` and `BIBTEX` can be used to customize the
(Bib)TeX commands (e.g. for adding specific command line arguments).
They default to

```
LATEX = pdflatex
BIBTEX = bibtex
```

To have any effect, these variables must be set before including the
`Makefile.pdfTeX` file.

An example project and Makefile is contained in the `example/`
directory.


*** Why not just use `latexmk` or XYZ tool? ***

There are many other ways to build TeX projects, some much more
sophisticated than these simple scripts.  A non-exhaustive list is
given in this [TeX StackExchange
post](https://tex.stackexchange.com/questions/40738/how-to-properly-make-a-latex-project).
Among these, `latexmk` is probably the best known, and it's already
included in many TeX distributions.  So why not use that instead?

There is nothing wrong with `latexmk` or any of those other tools, and
you probably should use them!

Indeed they are likely much more robust and versatile than the two
scripts provided in this repo.  Still, I have found these scripts
useful in many of my own projects over the years, mostly because they
are easy to deploy and only depend on tools that are readily available
on most Unix-like systems (a shell and GNU/Make).  So I decided to
share them just in case others might also find them useful.

----
(c) Sandro Stucki 2021 – see the `LICENSE` file for more info
