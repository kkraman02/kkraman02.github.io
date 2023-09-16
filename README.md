# roscube-doc

This is the source of https://adlink-ros.github.io/roscube-doc

After modifying source file and pushing to GitHub, GitHub action will do the deployment automatically.

* Install necessary packages

```bash
sudo apt install python3-pip
# We need to pin docutils to 0.16.0 since https://github.com/sphinx-doc/sphinx/issues/9051
python3 -m pip install -r requirements.txt
```

## Test the website

```bash
make html
```

## Test the pdf

* Install necessary packages

```bash
sudo app install latexmk
sudo apt install texlive-latex-extra
```

* Generate pdf

```bash
make latexpdf
```