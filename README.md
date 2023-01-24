# cctbxsnips for the yasnippets package in Emacs

## CCTBX

[CCTBX](https://github.com/cctbx/cctbx_project) is the Computational Crystallography Toolbox. 
Its development is based at Berkley-Lawrence National Laboratory.
It provides code for doing computations with diffraction data and atomic coordinates of proteins and small molecules.
It has C++ and Python ports.
It is available in Anaconda in the conda-forge channel as cctbx-base for python3.8 through 3.11 for Windows, MacOS, and Linux.

### Blaine's cctbx install protocol

I assume that Anaconda has already been installed. We also create the Jupyter notebook kernel while we are at it. Execute one line at a time: Wait for the execuation to finish before executing the next line.

```bash
conda create --name cctbx39 python=3.9
conda activate cctbx39
conda install -c conda-forge cctbx-base -y
conda install ipykernel -y
python -m ipykernel install --user --name cctbx39 --display-name "cctbx python3.9"
```

The second to last command triggers the installation of Jupyter in the cctbx39 env.
The last command creates and installs the Jupyter kernel in `~/Library/Jupyter/kernels/cctbx39` on the Mac.
Select **cctbx python3.9** from the list of kernels when opening a new notebook in Jupyter.

Replace the *3.9* or *39* above with whatever version of Python you want to use (between 3.8 and 3.11).

## yasnippets

This a very popular snippet manager for Emacs.
There other snippets managers for Emacs.
yasnippets is not built into Emacs and must be installed separately.
It is available in MELPA.


## The problems that this repo addresses

1. **Facilitation of code reuse**. The use of code snippets can save time by reusing existing code. The presence of tab stops in code snippets can help ensure that all parameters that need customization to a new problem are considered. This can reduce subsequent debugging.

2. **Use of Emacs to edit Jupyter and Colab code and markdown cells** The exisitig snippet formats for Jupyter and Colab notebooks do not support tab triggers and tab stops: These are standard features of code snippet systems in most text editors. These limitations can be overcome by sending the active code cell to Emacs via the GhostText extension for the browser and the atomic-chrome package for Emacs.

## Installation

1. Install the snippets

```bash
cd ~/.emacs.d/snippets/python-mode
git clone https://github.com/MooersLab/cctbxsnips-Emacs.git
cd cctbxsnips-Emacs/yasnippets
mv * ../../.
cd ../..
rm -rf cctbxsnips-Emacs
```

2. **Optional** If you want to use these snippets from Emacs to edit live cells in Jupyter or Colab notebooks, install [GhostText](https://ghosttext.fregante.com/) in your browser and atomic-chome in [Emacs](https://github.com/alpha22jp/atomic-chrome).
