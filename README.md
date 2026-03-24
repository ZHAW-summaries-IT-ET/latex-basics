# IT_ZHAW_Summaries

Hii!

We try to create helpful Summaries for the Bsc. in Computer Science at the ZHAW :D

But be warned - this is by nooo means a complete collection of all materials, and there might be some mistakes. but it might still be helpful :)

good luck with your exams!

## Cloning the repository
Now clone the repo you wanna work on (**make sure that this repo is a submodule!!!** help: https://git-scm.com/book/en/v2/Git-Tools-Submodules)

### for existing repos
```bash
git clone --recurse-submodules <link to the repo>
```

**OR** (if you forgot to add --recurse-submodule and already cloned the repo)
- open in vscode
- open new terminal (easier than navigating there imo, but just do whatever you want)
```bash
git submodule init
git submodule update
```

**!! DO NOT EDIT THE LATEX-BASICS FILES OR ATTEMPT TO PUSH CHANGES !!**
(i WILL find you)

## Actually working on a LateX Summary

and now if you're in the main.tex file of any LateX project you should be able to build the pdf by pressing run (the little green triangle in the top right corner, and if you want to build & view the pdf press the page icon with the little magnifying glass).

Whenever you save a LateX file, it will automatically rebuild the pdf. Look at the existing LateX projects to see how a main.tex file should be setup (best examples in folder 4th Semester). The pdf can be found in the "output" folder.

If you want to past images use ctrl + shift + V. This will (should) automatically add the image to the repo.

**If you don't understand something, there's a good chance that looking at the files in the example folder will help!**

## LateX Setup
I use vscode, so good luck figuring this out if you're using smth different. In vscode install the following extension:
- James-Yu.latex-workshop (details: https://github.com/James-Yu/LaTeX-Workshop/wiki)

I recommend using some kind of installation manager (in general) so yeah, hopefully you know what that is. 
- install python3
then install all necessary python packages (I don't remember all of them, if you get an error while compiling just read the error message and install any other missing packages) these are just some basics:
- pip install pytest pylint black mypy

now for windows:
- install Miktex at: https://miktex.org/download 
- and perl at: https://strawberryperl.com/

for ubuntu:
- this should probably work: https://nevalsar.hashnode.dev/compiling-latex-with-ubuntu-and-visual-studio-code
- or else maybe this: https://iggyrrieta.medium.com/using-latex-on-visual-studio-code-eea538d69d90

### JSON settings
*make sure your json file includes the following settings*

```
"[latex]": {
        "editor.defaultFormatter": "James-Yu.latex-workshop"
    },
    "latex-workshop.intellisense.biblatexJSON.replace": {},
    "latex-utilities.formattedPaste.image.template": "\\includegraphics[width=\\linewidth]{${imageFileName}}",
    "latex-utilities.formattedPaste.imagePathOverride": "${currentFileDir}/images",
    "latex-workshop.latex.outDir": "../latex-compiled-pdfs",
    "latex-workshop.latex.autoClean.run": "onSucceeded",
    "latex-workshop.latex.autoBuild.run": "onSave",
    "latex-workshop.latex.clean.method": "glob",
    "latex-workshop.latex.clean.fileTypes": [
        "%DOCFILE%.aux",
        "%DOCFILE%.bbl",
        "%DOCFILE%.blg",
        "%DOCFILE%.idx",
        "%DOCFILE%.ind",
        "%DOCFILE%.lof",
        "%DOCFILE%.lot",
        "%DOCFILE%.out",
        "%DOCFILE%.toc",
        "%DOCFILE%.acn",
        "%DOCFILE%.acr",
        "%DOCFILE%.alg",
        "%DOCFILE%.glg",
        "%DOCFILE%.glo",
        "%DOCFILE%.gls",
        "%DOCFILE%.fls",
        "%DOCFILE%.log",
        "%DOCFILE%.fdb_latexmk",
        "%DOCFILE%.snm",
        "%DOCFILE%.synctex(busy)",
        "%DOCFILE%.synctex.gz",
        "%DOCFILE%.nav",
        "%DOCFILE%.vrb"
    ],
    "latex-workshop.latex.tools": [

        {
            "name": "latexmk",
            "command": "latexmk",
            "args": [
                "-shell-escape",
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "-pdf",
                "-outdir=%OUTDIR%",
                "%DOC%"
            ],
            "env": {}
        },
        {
            "name": "lualatexmk",
            "command": "latexmk",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "-lualatex",
                "-outdir=%OUTDIR%",
                "%DOC%"
            ],
            "env": {}
        },
        {
            "name": "xelatexmk",
            "command": "latexmk",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "-xelatex",
                "-outdir=%OUTDIR%",
                "%DOC%"
            ],
            "env": {}
        },
        {
            "name": "latexmk_rconly",
            "command": "latexmk",
            "args": [
                "%DOC%"
            ],
            "env": {}
        },
        {
            "name": "pdflatex",
            "command": "pdflatex",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "%DOC%"
            ],
            "env": {}
        },
        {
            "name": "bibtex",
            "command": "bibtex",
            "args": [
                "%DOCFILE%"
            ],
            "env": {}
        },
        {
            "name": "rnw2tex",
            "command": "Rscript",
            "args": [
                "-e",
                "knitr::opts_knit$set(concordance = TRUE); knitr::knit('%DOCFILE_EXT%')"
            ],
            "env": {}
        },
        {
            "name": "jnw2tex",
            "command": "julia",
            "args": [
                "-e",
                "using Weave; weave(\"%DOC_EXT%\", doctype=\"tex\")"
            ],
            "env": {}
        },
        {
            "name": "jnw2texminted",
            "command": "julia",
            "args": [
                "-e",
                "using Weave; weave(\"%DOC_EXT%\", doctype=\"texminted\")"
            ],
            "env": {}
        },
        {
            "name": "pnw2tex",
            "command": "pweave",
            "args": [
                "-f",
                "tex",
                "%DOC_EXT%"
            ],
            "env": {}
        },
        {
            "name": "pnw2texminted",
            "command": "pweave",
            "args": [
                "-f",
                "texminted",
                "%DOC_EXT%"
            ],
            "env": {}
        },
        {
            "name": "tectonic",
            "command": "tectonic",
            "args": [
                "--synctex",
                "--keep-logs",
                "%DOC%.tex"
            ],
            "env": {}
        }
    ],
```

