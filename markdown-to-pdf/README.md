# Creating PDF out of Markdown

## Requirements

- [Pandoc](https://pandoc.org/) which requires a Latex installation


## Setup

Copy eisvogel-dhtech.latex into the Pandoc templates folder (on Mac: `/Users/[user]/.local/share/pandoc/templates`).

## Creating a PDF

- Exchange the markdown header of the lesson with a header like this (make sure colons are used and the correct beginning/end separators):
```
---
title: "Git & GitHub"
subtitle: "subtitle"
author: [Julia Damerow, Fernanda Freire]
date: "2024-05-09"
subject: "Version Control"
keywords: [Git, GitHub]
doi: doi/1234
lang: "en"
...
```
- Run Pandoc specifying the `eisvogel-dhtech` template: 
```
pandoc git.md -f markdown -t pdf -s -o git.pdf -V colorlinks --template eisvogel-dhtech
```

