# MY REPORTS

I needed to write a bunch of reports for my Cybersecurity class and so I've borrowed and modified a template by [Valerio Casalino](https://github.com/5amu/) 😉.

## Install

```bash
.
├── .local
│   └── share
│       └── pandoc
│           ├── reports-font-settings.latex
│           ├── reports-fonts.latex
│           ├── reports.latex
│           └── reports.theme
├── LICENSE
├── README.md
├── makereport
└── template
    └── template.md

5 directories, 8 files
```

To install this script you'll have to put the **.local/share/pandoc/*** files in the same directory in your home, then move the **template/template.md** file in your reports folder (mine is in ~/Documents/reports) and finally, you have to move the **makereport** file to a folder in your $PATH (mine is in ~/bin)

```bash
# copy the template files
cp .local/share/pandoc/reports* ~/.local/share/pandoc
# copy the template markdown
cp -R template ~/Documents/reports
# copy the script
cp makereport ~/bin
```

## Usage

to use it we first create our report structure in the folder where we are going to work:

```bash
mkdir "our-report" && cd "our-report"
makereport -t "whatever.md"
```

then we'll edit our Markdown file (remember to set your details in the Front Matter)

### Front Matter

this is the default front matter. The title will be automatically substituted by the name of the report created in the previous step.

```yaml
---
# mainfont: "Noto Serif Regular"
mainfont: "Noto Sans Regular"
sansfont: "Noto Sans Regular"
monofont: "Noto Sans Mono Regular"

# Information about the document
title: "W10D4 - Raccolta Informazioni"
classification: PUBLIC
#callout: '[my website](https://danix.xyz)'

# Information about the author
author: Danilo 'danix' Macrì
email: mia.mail@mio.sito
legal: false

# Set of information about the client and the specific activity
client: metasploitable
#activity: recon
activity: pentesting
activity_type: Multiple tests
startdate: 11/09/2025
engagetime: 1
---
```

### Exporting the pdf

After we finish working on our report we can export it to pdf. While in the same folder we will run our command again, but this time like this:

```bash
makereport -o "report title.pdf" "whatever.md"
```

and after a few seconds we'll have our report in the same folder.

## Dependancies

This script depends on:

- [pandoc](https://pandoc.org/)
- [pdflatex](https://www.tug.org/applications/pdftex/)

you should be able to install both from your package manager

## Thanks

- [Valerio Casalino](https://github.com/5amu/) - The original author of this script (thanks again)

- lots of ☕ and various web searches (latex is kind of hard)

- *my mom for making me so smart* ❤️