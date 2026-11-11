# Algorithms for temporal graph problems

Slides for a talk at St Andrews, November 2026.
Jess Enright, School of Computing Science, University of Glasgow.

Joint work with Sam Hand, Laura Larios-Jones, Tom Davot, Jayakrishnan Madathil,
Kitty Meeks and others.

Adapted from the AARMS talk of September 2026 (`enright-aarms-2026-talk`):
aimed at a pure maths / combinatorics audience, with added material on pursuit
and burning games on temporal graphs.

## Building

Beamer with the Glasgow theme, and **must be compiled with XeLaTeX** (the theme
uses `fontspec`). The source carries a `% !TEX TS-program = xelatex` line, so in
TeXShop you can open `enright-st-andrews-2026.tex` and press Typeset.

From the command line:

    xelatex enright-st-andrews-2026.tex
    xelatex enright-st-andrews-2026.tex

Run it twice so the counters settle.

## Requirements

* XeLaTeX (TeX Live 2023 or later, or MacTeX).
* The `fira` package from TeX Live. The theme loads the Fira `.otf` files **by
  file name**, so the fonts need not be installed at system level.
* No `-shell-escape` is needed.

## Structure

The temporal c-closedness material sits **after the thanks slide** as back-up,
and is not part of the main talk.
