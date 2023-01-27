# cctbxsnips for the yasnippets package in Emacs

## CCTBX

[CCTBX](https://github.com/cctbx/cctbx_project) is the Computational Crystallography Toolbox. 
Its development is based at Berkeley-Lawrence National Laboratory.
It provides code for computations with diffraction data and atomic coordinates of proteins and small molecules.
It has C++ and Python ports.
It is available in Anaconda in the conda-forge channel as cctbx-base for python3.8 through 3.11 for Windows, macOS, and Linux.

### Blaine's cctbx install protocol

I assume that Anaconda has already been installed. We also create the Jupyter notebook kernel while we are at it. Execute one line at a time: Wait for the execution to finish before executing the next line.

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

This a popular snippet manager for Emacs.
There other snippets managers for Emacs.
yasnippets is not built into Emacs and must be installed separately.
It is available in MELPA.


## The problems that this repo addresses

1. **Facilitation of code reuse**. The use of code snippets can save time by reusing existing code. The presence of tab stops in code snippets can help ensure that all parameters that need customization to a new problem are considered. Thus, tab stops can reduce subsequent debugging.

2. **Use of Emacs to edit Jupyter and Colab code and markdown cells** The existnig snippet formats for Jupyter and Colab notebooks do not support tab triggers and tab stops: These are standard features of code snippet systems in most text editors. We can overcome these limitations by sending the active code cell to Emacs via the GhostText extension for the browser and the atomic-chrome package for Emacs.

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

2. **Optional** If you want to use these snippets from Emacs to edit live cells in Jupyter or Colab notebooks, install [GhostText](https://ghosttext.fregante.com/) in your browser and atomic-chrome in [Emacs](https://github.com/alpha22jp/atomic-chrome).

Below is the related configuration for my Emacs initialization file. 
Note that I have set the default programming language scope to Python so that code cells in Jupyter notebooks open in Emacs as being in the Python-mode went sent to Emacs from the web browser that is running the Jupyter session.

```elisp
;; atomic-chrome, used to interact with GhostText extension for Google Chrome.
(use-package atomic-chrome
      :ensure t)
;; uncomment the line below to start the server on start-up of Emacs.      
;; (atomic-chrome-start-server)
(setq atomic-chrome-default-major-mode 'python-mode)
(setq atomic-chrome-extension-type-list '(ghost-text))
;;(atomic-chrome-start-httpd)
(setq atomic-chrome-server-ghost-text-port 4001)
(setq atomic-chrome-url-major-mode-alist
      '(("github\\.com" . gfm-mode)
        ("overleaf.com" . latex-mode)
        ("750words.com" . latex-mode)))
; Select the style of opening the editing buffer by atomic-chrome-buffer-open-style.
; full: Open in the selected window.
; split: Open in the new window by splitting the selected window (default).
; frame: Create a new frame and window in it. Must be using some windowing pacakge.
(setq atomic-chrome-buffer-open-style 'split)
```

## Related repositories

- [Jupyterlab cctbx snippets](https://github.com/MooersLab/jupyterlabcctbxsnips) CCTBX snippets for JupyterLab with the jupyterlab-snippets extension or the jupyterlab-snippets-mutlimenus extension.
- [Jupyterlab cctbx plus snippets](https://github.com/MooersLab/jupyterlabcctbxsnipsplus) The variant of the jupyterlabcctbxsnips library with comments to guide editing of the snippets.
- [Colab cctbx snippets](https://github.com/MooersLab/colabcctbxsnips) Colab snippets.
