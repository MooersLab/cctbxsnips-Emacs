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

1. Install the snippets

```bash
cd ~/.emacs.d/snippets/python-mode
git clone https://github.com/MooersLab/cctbxsnips-Emacs.git
cd cctbxsnips-Emacs/yasnippets
mv * ../../.
cd ../..
rm -rf cctbxsnips-Emacs
``

2. **Optional** If you want to use these snippets in Jupyter or Colab notebooks, install [GhostText](https://ghosttext.fregante.com/) in your browser and atomic-chome in [Emacs](https://github.com/alpha22jp/atomic-chrome).
