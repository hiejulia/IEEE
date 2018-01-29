# Simplified IEEE Template [![Build Status](https://circleci.com/gh/latextemplates/IEEE/tree/master.svg?style=shield)](https://circleci.com/gh/latextemplates/IEEE/)

> Quick start for modern LaTeXing for an IEEE conference, based on the [Manuscript Template for Conference Proceedings](https://www.ieee.org/conferences_events/conferences/publishing/templates.html).

The official template is distributed via CTAN as the [IEEEtran package](https://ctan.org/pkg/ieeetran), which is actively maintained.
However, de-facto configurations (hyperref) and modern features of latex (microtype) are not configured.
This page does it.

This template is for the computer science conferences.
It is based on `bare_conf_compsoc.tex` distributed by IEEE.
In case you need other configurations, please adapt `paper.tex`.

## TOC

<!-- toc -->

- [Features](#features)
- [Quick start](#quick-start)
- [Tool hints](#tool-hints)
- [Using the template with your git repository](#using-the-template-with-your-git-repository)
- [FAQ](#faq)
  * [Q: I get the error `! pdfTeX error (font expansion): auto expansion is only possible with scalable fonts.`](#q-i-get-the-error---pdftex-error-font-expansion-auto-expansion-is-only-possible-with-scalable-fonts)
  * [Q: How can I reformat my .tex files?](#q-how-can-i-reformat-my-tex-files)
  * [Q: How I want to obey the one-sentence-per-line rule.](#q-how-i-want-to-obey-the-one-sentence-per-line-rule)
- [Links](#links)

<!-- tocstop -->

## Features

 * Provides skeletal [paper.tex](paper.tex) and [paper-compsocconf.tex](paper-compsocconf.tex) files.
 * Generated PDF allows for copy and paste of text without getting words with ligatures such as "workflow" destroyed.
   This is enabled by the [cmap] package, which encodes ligatures (such as fl) using unicode characters.
 * Support of hyperlinked references without extra color thanx to [hyperref].
 * Better breaking of long URLs.
 * Support for `\powerset` command.
 * Support todos as pdf annotations. This is enabled by the [pdfcomment] package.
 * [microtypographic extensions](https://www.ctan.org/pkg/microtype) for a better look of the paper.
 * Adds modern packages such as [microtype], [cleveref], [csquotes], [booktabs], [paralist], [hyperref], [hypcap], [upquote].
 * Shows how IEEE copyright notice can be added.
 * Optional: Support for [minted] package. Uncomment `\usepackage[newfloat]{minted}` to get started.
 * Ready-to-go configuration for [latexindent].

Examples:

- [paper.pdf](https://latextemplates.github.io/IEEE/paper.pdf) - regular paper.
- [paper-minted.pdf](https://latextemplates.github.io/IEEE/paper-minted.pdf) - paper showing minted in action.
- [paper-compsocconf.pdf](https://latextemplates.github.io/IEEE/paper.pdf) - papers for IEEE Computer Society conference papers.
- [paper-compsocconf-minted.pdf](https://latextemplates.github.io/IEEE/paper-minted.pdf) - paper for IEEE Computer Society conference papers showing minted in action.

## Quick start

 * Click on `Download ZIP` or [here](https://github.com/latextemplates/IEEE/archive/master.zip).
 * Extract `master.zip` in the folder where you want to write your paper.
 * In case you are working in the computer science field: Edit [paper-compsocconf.tex](paper-compsocconf.tex).
 * In case you are NOT working in the computer science field: Edit [paper.tex](paper.tex).
 * `latexmk paper-compsocconf` OR `latexmk paper`.

## Tool hints

There is currently no official biblatex support.
A first step towards that is done at the [biblatex-ieee package](https://ctan.org/pkg/biblatex-ieee).

MiKTeX installation hints are given at <https://github.com/latextemplates/scientific-thesis-template/blob/template/README.md#installation-hints-for-windows>.

- Grammar and spell checking is available at [TeXstudio].
  Please download [LanguageTool] (Windows: `choco install languagetool`) and [configure TeXstudio to use it](http://wiki.languagetool.org/checking-la-tex-with-languagetool#toc4).
  Note that it is enough to point to `languagetool.jar`.
  **If TeXstudio doesn't fit your need, check [the list of all available LaTeX Editors](http://tex.stackexchange.com/questions/339/latex-editors-ides).**
- Use [JabRef] to manage your bibliography (Windows: `choco install jabref`).


In case you want to get started using minted, do following steps:

1. Install python: `choco install python` - that uses [chocolatey](https://chocolatey.org/) to install Python
2. Install [pygments]: `pip instal pygments` - that uses the Pyhton package manager to install the pygments library
3. When latexing, use `-shell-escape`: `pdflatex -shell-escape paper`.
   You can also just execute `latexmk paper`.

## Using the template with your git repository

1. Initialize your git repository as usual
2. Add this repository as upstream: `git remote add upstream https://github.com/latextemplates/IEEE.git`
3. Merge the branch `upstream/master` into your `master` branch: `git merge upstream/master`.

After that you can use and push the `master` branch as usual.
Notes on syncing with the upstream repository [are available from GitHub](https://help.github.com/articles/syncing-a-fork/).

## FAQ

### Q: I get the error  `! pdfTeX error (font expansion): auto expansion is only possible with scalable fonts.`

Install the `cm-super` package using the MiKTeX package manager. Then, run `initexmf --mkmaps` on the command line. (Long description: http://tex.stackexchange.com/a/324972/9075)


### Q: How can I reformat my .tex files?

Execute `latexindent -l -s -sl -w paper.tex`


### Q: How I want to obey the one-sentence-per-line rule.

Execute `latexindent -m -l -s -sl -w paper.tex`.
Attention! This is work in progress and does not always produce best results.

## Links

 * German: Hinweise zu Ausarbeitungen: >http://wiki.flupp.de/studium/ausarbeitungen>
 * Other templates: <http://latextemplates.github.io/>

  [booktabs]: https://www.ctan.org/pkg/booktabs
  [cleveref]: https://ctan.org/pkg/cleveref
  [cmap]: https://www.ctan.org/pkg/cmap
  [csquotes]: https://www.ctan.org/pkg/csquotes
  [hypcap]: https://www.ctan.org/pkg/hypcap
  [hyperref]: https://ctan.org/pkg/hyperref
  [latexindent]: https://ctan.org/pkg/latexindent
  [microtype]: https://ctan.org/pkg/microtype
  [minted]: https://ctan.org/pkg/minted
  [newtx]: https://ctan.org/pkg/newtx
  [paralist]: https://www.ctan.org/pkg/paralist
  [pdfcomment]: https://www.ctan.org/pkg/pdfcomment
  [upquote]: https://www.ctan.org/pkg/upquote

  [JabRef]: https://www.jabref.org
  [LanguageTool]: https://languagetool.org/
  [TeXstudio]: http://texstudio.sourceforge.net/
  [pygments]: http://pygments.org/