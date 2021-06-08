# Integrating table of contents and equations

Here we discuss adding a table of contents and integrated equation into your `github_document` markdown. These can be nice features when trying to make an organized markdown file for a github repository. **Note**, I believe the table of contents syntax will work for an `html_document`, but the equations solution is specific to the `github_document` file markdown type.

## Table of Contents

Code: `toc: True`

Optionally, you can specify how many levels you want in your table of contents using - `toc_depth: 3`

## Equations

Code: `pandoc_args: "--webtex"`

## Simple example header

```
---
title: "Github_markdown_template"
output: 
  github_document:
    toc: true
    toc_depth: 3
    pandoc_args: "--webtex"
---
```

## Template File 

[Markdown](https://github.com/DrK-Lo/lotterhoslabprotocols/blob/gh-pages/_data/github_markdown_template.md) or [Rmd](https://github.com/DrK-Lo/lotterhoslabprotocols/blob/gh-pages/_data/github_markdown_template.Rmd)
