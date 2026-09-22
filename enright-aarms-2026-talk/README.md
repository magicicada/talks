# Algorithms for temporal graph problems

Slides for the AARMS talk, September 2026.
Jess Enright, School of Computing Science, University of Glasgow.

Joint work with Sam Hand, Laura Larios-Jones, Tom Davot, Jayakrishnan Madathil,
Kitty Meeks and others.

## Building

The deck is Beamer with the Glasgow theme, and **must be compiled with XeLaTeX**
(the theme uses `fontspec`). The source carries a `% !TEX TS-program = xelatex`
line, so in TeXShop you can simply open `main-enright.tex` and press Typeset.

From the command line:

    xelatex main-enright.tex
    xelatex main-enright.tex

Run it twice so the section/frame counters settle.

## Requirements

* XeLaTeX (TeX Live 2023 or later, or MacTeX).
* The `fira` package, which ships with a full TeX Live install. The theme loads
  the Fira Sans and Fira Mono `.otf` files **by file name**, so the fonts do not
  need to be installed at the system level.
* No `-shell-escape` is needed.

## Contents

Everything in this directory is used by the deck: `main-enright.tex`, the four
theme files (`beamerthemeglasgow.sty`, `beamercolorthemeglasgow.sty`,
`beamerfontthemeglasgow.sty`, `UoG_keyline.pdf`), and the figures.
