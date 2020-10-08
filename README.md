
<!-- README.md is generated from README.Rmd. Please edit that file -->

## Overview

The R package NearRepeat uses the Knox test for space-time clustering to
quantify the spatio-temporal association between events. In criminology,
this test has been used to identify people and locations that are at
disproportionate risk of victimization. Of interest is often not only
the ‘same repeat’ victims (people or locations that after a first crime
event, are targeted again within a short period thereafter), but also
the ‘near repeat’ victims: **nearby** people or locations that are
victimized within a short period after the first crime. For more
information, see for example the [JDI Analysis
Brief](http://www.ucl.ac.uk/jdibrief/analysis/repeat_victimisation).

Note that in parallel with the development of the code here, Toby Davies
has developed an alternative implementation in Python, which can be
found [here](https://github.com/tobydavies/NearRepeat). We have
collaborated on some of the accompanying materials and reviewed each
other’s code, and as far as we are aware the two implementations should
give identical results.

Several other options exist but have drawbacks:

  - [Prof. Jerry Ratcliffe’s](http://www.jratcliffe.net/software/) /
    [Temple
    University’s](http://www.cla.temple.edu/center-for-security-and-crime-science/projects/#near-repeat-calculator)
    Near Repeat calculator only works on Windows (and needs admin rights
    to execute and write files). It seems this software mislabels the
    rows and columns of its output files, which may lead to erroneous
    conclusions.

  - the free [JDI Near Repeat
    Toolkit](http://www.ucl.ac.uk/jill-dando-institute/research/research-groups/geo-crime/near_repeat_toolkit)
    also only works on Windows. However it is not actively supported and
    does not run on Windows 10.

  - the R package
    [surveillance](https://cran.r-project.org/package=surveillance) has
    implemented the `knox()` function, but this only works for a single
    spatial distance and temporal distance, whereas the current package
    also works with multiple bands of spatial and temporal distances, as
    well as same repeat analysis.

## Version

The most recent version of the package is:

> Steenbeek, W. (2018). *Near Repeat*. R package version 0.1.1. URL:
> <https://github.com/wsteenbeek/NearRepeat>

## Installation

You can install the package from this [GitHub
repository](https://github.com/wsteenbeek/NearRepeat). You first need to
install the [remotes](https://CRAN.R-project.org/package=remotes)
package.

``` r
install.packages("remotes")
```

Then install the `NearRepeat` package using the `install_github`
function in the [remotes](https://CRAN.R-project.org/package=remotes)
package.

``` r
remotes::install_github("wsteenbeek/NearRepeat")
```

Note that if you also want to view the vignettes directly within R, the
command should read:

``` r
remotes::install_github("wsteenbeek/NearRepeat", build_vignettes = TRUE)
```

After a few moments you should see “creating vignettes …” and at that
point you have to wait a few minutes. Because of the wait time and
because you may need additional packages to build vignettes, the default
`install_github()` call does not build vignettes. Alternatively, the
vignettes can also be viewed directly online (see section ‘Vignettes’).

Package `NearRepeat` needs packages `future.apply` and `ggplot2` to
function correctly. If these are not installed already, following the
steps above should install these dependencies as well. If this doesn’t
happen, it’s best to run `install.packages(c("future.apply",
"ggplot2"))` and try the steps above again.

## Example

The package currently has one main function, also called `NearRepeat()`.
See the helpfile to see examples of the function in action:

``` r
library(NearRepeat)
?NearRepeat
```

## Vignettes

Vignettes are a long-form guide to an R package. Read these to get a
relatively easy introduction to the package and its various options. You
can view the available vignettes using:

``` r
browseVignettes("NearRepeat")
```

To directly read the vignettes rather than going through
`browseVignettes("NearRepeat")` you can use:

``` r
vignette("NearRepeat", package = "NearRepeat")
vignette("NearRepeat_breaks", package = "NearRepeat")
vignette("NRC", package = "NearRepeat")
vignette("prepare_data", package = "NearRepeat")
```

Finally, the vignettes can be viewed directly, without installing the
package, using the following links:

  - [NearRepeat: introduction to the
    package](http://htmlpreview.github.io/?https://github.com/wsteenbeek/NearRepeat/blob/master/doc/NearRepeat.html)
  - [NearRepeat\_breaks: a detailed description of how bandwidths can be
    specified](http://htmlpreview.github.io/?https://github.com/wsteenbeek/NearRepeat/blob/master/doc/NearRepeat_breaks.html)
  - [NRC: a comparison to the Near Repeat
    Calculator](http://htmlpreview.github.io/?https://github.com/wsteenbeek/NearRepeat/blob/master/doc/NRC.html)
  - [prepare\_data: how data was downloaded and prepped for the examples
    in the
    vignettes](http://htmlpreview.github.io/?https://github.com/wsteenbeek/NearRepeat/blob/master/doc/prepare_data.html)

## License

This package is free software; you can redistribute it and/or modify it
under the terms of the GNU General Public License, version 3, as
published by the Free Software Foundation.

This program is distributed in the hope that it will be useful, but
without any warranty; without even the implied warranty of
merchantability or fitness for a particular purpose. See the GNU General
Public License for more details.

A copy of the GNU General Public License, version 3, is available at
<https://www.r-project.org/Licenses/GPL-3>
