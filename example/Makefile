###
#
# Makefile -- Runs `pdflatex' to generate PDFs
#
# This is a Makefile template for generating PDFs from LaTeX sources.
# To use this file, adjust the list of targets (PDF files) through the
# `PDFS' variable.  The generic build rules should take care of the
# rest.
#
# This file depends on the generic `Makefile.pdfTeX' makefile, as well
# as the `texdeps.sh' dependency file generator script.  If the later
# is not located in the same directory as this Makefile, you will need
# to adjust the `MAKEDEPS' variable (before including the generic
# `Makefile.pdfTeX' makefile), e.g.
#
#   MAKEDEPS = <path to texdeps.sh>/texdeps.sh
#
# Author: Sandro Stucki
#
# For more info, see https://github.com/sstucki/Makefile.pdfTeX/


### Targets (PDFs to generate) ###

PDFS = main.pdf other.pdf


### Settings ###

# Location of the dependency file generator script
MAKEDEPS = ../texdeps.sh

# Inlcude generic rules for generating PDFs from TeX sources
include ../Makefile.pdfTeX
