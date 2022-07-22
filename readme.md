
<!-- README.md is generated from README.Rmd. Please edit that file -->

# rebib : Parse/Convert embedded LaTeX bibliography to BibTex

<!-- badges: start -->
<!-- badges: end -->

rebib is a spun off package from
[texor](https://github.com/Abhi-1U/texor) project.

The decision to do this was based on the fact that the bibliography
section in texor package was expanding significantly, enough to have its
own package.

-   Reads bib chunks to produce minimum viable bibtex equivalent

## Installation

install the development version from GitHub with:

``` r
# install.packages("remotes")
remotes::install_github("Abhi-1U/rebib")
# install.packages("pak")
pak::pak("Abhi-1U/rebib")
```

## General Usage

here is a quick example to use rebib package with a sample Rjournal
article (included with the package
[inst/article](https://github.com/Abhi-1U/rebib/tree/master/inst/article))

``` r
wd <-  system.file("article", package = "rebib")
rebib::handle_bibliography(wd)
cat(readLines(paste(wd,"example.bib",sep="/")),sep = "\n")
```

## Sample Conversion

Embedded bibliography :

    \bibitem[R Core Team]{R}
    R Core Team
    \newblock R: A Language and Environment for Statistical Computing
    \newblock \emph{R Foundation for Statistical Computing}, Vienna, Austria \penalty0 2016.
    \newblock URL : \url{https://www.R-project.org/}, ISBN 3-900051-07-0

generated BibTeX :

    @book{ R,
    author = {{ R Core Team }},
    title = {{  R: A Language and Environment for Statistical Computing }},
    journal = {{  R Foundation for Statistical Computing, Vienna, Austria  2016. ISBN 3-900051-07-0 }},
    url = {{ https://www.R-project.org/, }}
    }
