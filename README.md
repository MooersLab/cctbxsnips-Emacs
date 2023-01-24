# cctbxsnips for the yasnippets package in Emacs

## CCTBX

CCTBX is the crystallographic Computatoinal Tool Box. 
Its development is based at Berkley-Lawrence National Laboratory.
It provides code for doing computations with diffraction data and atomic coordinates.
It has C++ and Python ports.

## yasnippets

This a very popular snippet manager for Emacs.
There other snippets managers for Emacs.
yasnippets is not built into Emacs and must be installed separately.
It is available in MELPA.


## The problems that this repo addresses

1. **Facilitation of code reuse**. The use of code snippets can save time by reusing existing code. The presence of tab stops in code snippets can help ensure that all parameters that need customization to a new problem are considered. This can reduce subsequent debugging.

2. **Use of Emacs to edit Jupyter and Colab code cells** The exisitig snippet formats for Jupyter and Colab notebooks do not support tab triggers and tab stops: These are standard features of code snippet systems in most text editors. These limitations can be overcome by sending the active code cell to Emacs via the GhostText extension for the browser and the atomic-chrome package for Emacs.

## Installation

```bash
cd ~/.emacs.d/snippets/python-mode
git clone http

``
