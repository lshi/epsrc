# A LaTeX Style Implementing the Layout of EPSRC Funding Proposals

This LaTeX class provides a layout for EPSRC funding applications in the UK. It
focuses on the traditional proposal layout, that is summarized on the [EPSRC
website](https://www.ukri.org/councils/epsrc/guidance-for-applicants/what-to-include-in-your-proposal/overview-of-information-needed-for-your-proposal/)
as follows:

> All attachments must be completed in single-spaced typescript in Arial 11 or
> other sans serif typeface of equivalent size, with margins of at least 2cm.
> Arial narrow and Calibri are not allowable font types.
>
> Text in embedded diagrams or pictures, numerical formulae or references can be
> smaller, as long as it is legible. Text in tables and figure labels not within
> embedded diagrams or pictures should be at least 11 point.
>
> We recommend that all attachments are uploaded into Je-S as Adobe Acrobat files
> (PDF) as uploading word documents can result in layout changes to the document.
> Also, as Je-S does not support all Microsoft Office Word font types, unsupported
> fonts will be replaced, possibly resulting in layout changes to the document.

**Disclaimer:** While this class tries to follow this layout as closely as possible,
there is no guarantee that proposal written using the EPSRC class are accepted for
review (i.e., not desk rejected) and neither is there a guarantee of a positive
funding outcome.

## Usage

To ensure the consistency of common configurations across the various documents
that EPSRC requires, the class file uses a file `epsrc.config` that, if available,
is shared across all documents. A minimal example is:

```latex
\author{Poor Researcher}
\projectitle[PGMM]{Please Give Me Money}

```

Otherwise, the class file is loaded as usual:

```latex
\documentclass{epsrc}
```

This ensures a document following the basic layout on a4 paper with 2 cm margins
and a base font that is metrically compatible with Arial (the current setup uses
[Arimo](https://fonts.google.com/specimen/Arimo)). Moreover, the font size is
scaled to use 11 pt in Postscript Points.

### Package Options

The `epsrc` class only has one option, called `hideinfo` that is `false` by
default. This options configures if additional information using the `\info{}`
command are shown or now.

### Provided Commands

The provides the following commands:

* `\info{...}` for type-setting informative text for co-authors. In the final
  submission, this text is usually hidden (using the class option `hideinfo`).
* `\projectitle[shorttitle]{longtitle}` for setting the project title (and,
  optional, an acronym).
* `\project` for printing the full title of a project (long title and acronym)
* `\projectlong` for printing the long title of a project
* `\projectshort` for printing the short title of a project

### Bibliography

The package configures `biblatex` for type-setting bibliographies. All standard commands of the package `biblatex` can be used. Moreover, the class file provides
the following additional commands:

* `\citeapplicant{...}` as a variation of the `\cite{...}`, marking the citation
  a work of one of the applicants of the proposal. They are marked in the
  bibliography.
* `\singlecolprintbibliography` as an alternative to `\printbibliography` with a
  pre-configured single-column layout (this might be bending the EPSRC rules)
* `\twocolprintbibliography` as an alternative to `\printbibliography` with a
  pre-configured two-column layout (this might be bending the EPSRC rules)


## Authors

Main author: [Achim D. Brucker](http://www.brucker.ch/)

## License

This project is dual-licensed under a 2-clause BSD-style license and/or
the LPPL version 1.3c or (at your opinion) any later version.

```yaml
SPDX-License-Identifier: LPPL-1.3c+ OR BSD-2-Clause
```

## Upstream Repository

The upstream git repository, i.e., the single source of truth, for this
project is hosted by the
[Software Assurance & Security Research Team](https://logicalhacking.com) at
<https://git.logicalhacking.com/adbrucker/epsrc>.
