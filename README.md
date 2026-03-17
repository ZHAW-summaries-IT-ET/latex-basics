# IT_ZHAW_Summaries

Hii!

We try to create helpful Summaries for the Bsc. in Computer Science at the ZHAW :D

But be warned - this is by nooo means a complete collection of all materials, and there might be some mistakes. but it might still be helpful :)

good luck with your exams!

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
*coming soon*

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

