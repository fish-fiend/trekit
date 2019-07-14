
<!-- README.md is generated from README.Rmd. Please edit that file -->

# lcars <img src="man/figures/logo.png" style="margin-left:10px;margin-bottom:5px;" width="120" align="right">

**Author:** [Matthew Leonawicz](https://leonawicz.github.io/blog/)
<a href="https://orcid.org/0000-0001-9452-2771" target="orcid.widget">
<image class="orcid" src="https://members.orcid.org/sites/default/files/vector_iD_icon.svg" height="16"></a>
<br/> **License:** [MIT](https://opensource.org/licenses/MIT)<br/>

[![CRAN
status](http://www.r-pkg.org/badges/version/lcars)](https://cran.r-project.org/package=lcars)
[![CRAN
downloads](http://cranlogs.r-pkg.org/badges/grand-total/lcars)](https://cran.r-project.org/package=lcars)
[![Rdoc](http://www.rdocumentation.org/badges/version/lcars)](http://www.rdocumentation.org/packages/lcars)
[![Travis build
status](https://travis-ci.org/leonawicz/lcars.svg?branch=master)](https://travis-ci.org/leonawicz/lcars)
[![AppVeyor build
status](https://ci.appveyor.com/api/projects/status/github/leonawicz/lcars?branch=master&svg=true)](https://ci.appveyor.com/project/leonawicz/lcars)
[![Codecov test
coverage](https://codecov.io/gh/leonawicz/lcars/branch/master/graph/badge.svg)](https://codecov.io/gh/leonawicz/lcars?branch=master)

## Library Computer Access/Retrieval System ([LCARS](https://en.wikipedia.org/wiki/LCARS))

The `lcars` package provides simple approximations to LCARS style and
appearance to give static plots and interactive data analysis an LCARS
theme. This splits the package into two areas:

  - One key feature in `lcars` is the ability to wrap ggplot objects in
    an LCARS-themed border using `lcars_border`.
  - There is also support for an LCARS-themed Shiny UI using `lcarsPage`
    and related functions.

While the former is fun and useful for static graphs, the latter is much
more exciting because it means you can make something with the look and
feel of LCARS that also *actually functions*\!

![](man/figures/README-banner.png)

That’s right. Make your Shiny app, view it on a touch screen device like
your very own Federation issue data PADD, and transport yourself into
the future of the Star Trek universe with this 1980s sci-fi television
aesthetic\!

The static plot border and Shiny `lcarsBox` widget both give plenty of
control over the style. Given their different fundamental designs, they
provide somewhat different aspects of design control via their
respective function arguments.

## Installation

You can install the released version of `lcars` from
[CRAN](https://CRAN.R-project.org) with:

``` r
install.packages("lcars")
```

You can install the development version of `lcars` from GitHub with:

``` r
# install.packages("remotes")
remotes::install_github("leonawicz/lcars")
```

## Example

``` r
library(lcars)
library(ggplot2)

g <- ggplot(iris, aes(Sepal.Length, Sepal.Width, color = Species)) + 
  geom_point() + facet_wrap(~Species, 2) + theme_lcars_light()

len_frac <- c(0.3, 0.5, 0.2, 0.4, 0.3, 0.2, 0.1, 0.3)
n_seg <- c(1, 2, 0, 8)
lcars_border(g, corners = 1:3, length_frac = len_frac, side_n_segments = n_seg)
```

<img src="man/figures/README-unnamed-chunk-2-1.png" width="100%" />

For more examples see the [introduction](articles/lcars.html) vignette.
