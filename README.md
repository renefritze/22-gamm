# 22-gamm-neu

René Fritze
rene.fritze@wwu.de

* [Slides](https://renefritze.github.io/22-gamm-neu)
* [PDF](https://github.com/renefritze/22-gamm/blob/master/slides/22_fritze_gamm.pdf)

repository_description.

[![Build Status](https://github.com/renefritze/22-gamm/actions/workflows/build.yml/badge.svg?main)](https://github.com/renefritze/22-gamm/actions/workflows/build.yml)
[![GitHub license](https://img.shields.io/github/license/renefritze/22-gamm.svg)](https://github.com/renefritze/22-gamm/blob/main/LICENSE)


## Install

1. Install [npm](https://www.npmjs.com/)
2. [Clone](https://git-scm.com/docs/git-clone) this repository
3. Install dependencies with `npm`

```
git clone https://github.com/renefritze/22-gamm
cd 22-gamm-neu
make install
```

See [Edits](#edits) and [Implementation](#implementation) for more details.

## Usage

1. Generate `static_html/index.html` (see `script.html` in [package.json](https://github.com/renefritze/22-gamm/blob/master/package.json))
2. Generate `slides/22_fritze_gamm.pdf` (see `script.pdf` in [package.json](https://github.com/renefritze/22-gamm/blob/master/package.json))

```
make html
make pdf
```

## Developer Notes

### Edits

The following can be edited before generating:

* `slides/22_fritze_gamm.md`: [Markdown](https://daringfireball.net/projects/markdown/) file with slide contents
* `slides/template.html`: Custom [reveal-md](https://github.com/webpro/reveal-md) template to generate slides with
* `static_html/edit/style.css`: [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) file to adjust styling of slides
* `static_html/edit/logo.png`: logo image to use

### Implementation


The slides [22-gamm-neu](https://github.com/renefritze/22-gamm) uses the following [npm](https://www.npmjs.com/) packages for its implementation:

npm | Purpose
--- | ---
[reveal-md](https://www.npmjs.com/package/reveal-md) | Converting `slides/22_fritze_gamm.md` to `static_html/index.html`
[decktape](https://www.npmjs.com/package/decktape) | Converting `slides/22_fritze_gamm.md` to `slides/22_fritze_gamm.pdf`
[windows-build-tools](https://www.npmjs.com/package/windows-build-tools) | Compiling dependencies for decktape on Windows Operating System (OS)

```
       reveal-md            <-- Convert markdown  slides to html

       decktape             <-- Convert markdown slides to pdf
          |
  windows-build-tools       <-- Compile decktape on Windows OS
```

### Deployment

Pushes to the main branch trigger a Github Action that builds the html slides and deploys the `static_html/` directory via the `gh-pages` branch to Github Pages.
For this to work goto Repository Settings -> Actions -> General -> Workflow permissions and set that to "read and write".

### Notes

- [Mermaid](https://mermaid-js.github.io/mermaid/) Support thanks to [plugin by @amra](https://github.com/amra/reveal-md-scripts)
