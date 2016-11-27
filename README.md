# remark-preset-latex

[![standard-readme compliant][standard-readme-badge]][standard-readme]
[![LICENSE][license-badge]][license]
[![NPM][npm-badge]][npm]
[![CircleCI][circleci-badge]][circleci]

[npm]: https://www.npmjs.com/package/@paperist/remark-preset-latex
[license]: https://3846masa.mit-license.org
[circleci]: https://circleci.com/gh/Paperist/remark-preset-latex
[standard-readme]: https://github.com/RichardLitt/standard-readme

[npm-badge]: https://img.shields.io/npm/v/@paperist/remark-preset-latex.svg?style=flat-square&logo=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgBAMAAACBVGfHAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAAbUExURcwAAOeIiP////G7u/ri4tIZGdpFReJsbPC3t075sZwAAAAvSURBVCjPY2CgDWAThIMEsACjEhwIUCZg0dGCIqASwMAxMgXAgSzOwMAOC2TqAwBvzR4JxLaP0gAAAABJRU5ErkJggg==
[license-badge]: https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square&logo=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAAQBAMAAADt3eJSAAAAIGNIUk0AAHomAACAhAAA%2BgAAAIDoAAB1MAAA6mAAADqYAAAXcJy6UTwAAAAVUExURSBTICJcIiNgIiZoJTuhNyt3Kf///%2BCqxSgAAAAGdFJOUwpclbn%2B4Fj6/H8AAAABYktHRAZhZrh9AAAACXBIWXMAAA3XAAAN1wFCKJt4AAAAB3RJTUUH4AkEEjEV7MDQQwAAAGBJREFUCNc1TUEKgDAMi07vE/Q%2BRD8g%2B4BbvAvi/79iMjDQJm1CC6BbDzRsZI3incIpYeYFhCaYnLiyPYnYkwWZFWoFHrSuttCmmbwXh0eJQYVON4JthZTxCzzAmyb8%2BAAKXBRyN6RyZQAAAABJRU5ErkJggg==
[circleci-badge]: https://img.shields.io/circleci/project/Paperist/remark-preset-latex/master.svg?style=flat-square&logo=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAAQEAYAAABPYyMiAAAAIGNIUk0AAHomAACAhAAA%2BgAAAIDoAAB1MAAA6mAAADqYAAAXcJy6UTwAAAAGYktHRP///////wlY99wAAAAHdElNRQfgCQQSJS8EYt6kAAAAiklEQVRIx2M41nqs9Xi9WDQh%2BjQQnDnz%2BS5x9KS9xJrLgN/CSXtJs5h0BzHQ1mLCDmEgL4jJpyl0AOG4JTYE4Q6gdqIi1UMM2F1OrE9xBy2xDmGgrs8wHU5nB2CGBNEOQPcBoaigThQA08AgS4QDkA3pXRChe4SBskqHiiUhreoEsmtDyhxEfKIFAG4yoGuqR9fTAAAAAElFTkSuQmCC
[standard-readme-badge]: https://img.shields.io/badge/standard--readme-OK-green.svg?style=flat-square

> LaTeX preset for [wooorm/remark]

[wooorm/remark]: https://github.com/wooorm/remark

## Table of Contents

- [Install](#install)
- [Usage](#usage)
- [Contribute](#contribute)
- [License](#license)

## Install

```
npm i remark remark-cli @paperist/remark-preset-latex
```

## Usage

```
$ remark index.md -p @paperist/remark-preset-latex -o index.tex
```

## Syntax

Inspired by [pandoc-crossref](https://github.com/lierdakil/pandoc-crossref).

### Image labels

```markdown
![Caption](file.ext){#fig:label}

![Caption](file.ext){#fig:label2 width=5cm,height=5cm}
```

### Equation labels

```markdown
$$ math $$ {#eq:label}
```

### Table labels

```markdown
|  a  |  b  |  c  |
|:---:|:---:|:---:|
|  1  |  2  |  3  |

: Caption {#tbl:label}
```

### Section labels

```markdown
# Section {#sec:section}
```

### Code Block labels

**Not implemented**

<pre>
```{#lst:code .haskell caption="Listing caption"}
main :: IO ()
main = putStrLn "Hello World!"
```
</pre>

### References

```markdown
[@fig:label1] or [@fig:label1;@fig:label2;...]
```

```markdown
[@jones99] or [@jones99;@smith06;...]
```

### YAML

#### Templates

You can use [ejs] template.

[ejs]: https://github.com/mde/ejs

```tex
%% TeX Template written by ejs format.

\author{<%= author %>}
\title{<%= title %>}

\begin{document}

\maketitle

<%= body %>

\end{document}
```

```yaml
latex:
  baseTemplateFile: ./template.tex
  documentInfo:
    author: 3846masa
    title: Document Title
```

#### Bibliography

**Not implemented**

## Contribute

PRs accepted.

## License

MIT © 3846masa
