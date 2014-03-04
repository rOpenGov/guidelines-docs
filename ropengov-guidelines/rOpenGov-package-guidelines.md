This page summarizes the recommendations for rOpenGov R packages. To keep it simple, we have very few specific requirements for rOpenGov packages. New contributors, please read carefully. 

By following these guidelines, the rOpenGov contributors can benefit from automated package build reports, online tutorial pages, and standardized package usage instructions. The guidelines are aimed to promote high-quality, well documented, and interoperable software. 


Package Maintainer Responsibilities
------------------------------------------------

Acceptance of packages into rOpenGov brings with it ongoing responsibility for package maintenance. The authors mentioned in the package DESCRIPTION file are requested to:

 * Subscribe to the ropengov-forum mailing list. In addition, we recommend connecting with the community via IRC, Google+, and other [community forums](http://ropengov.github.io/contribute)
 * Response to feedback from users via the mailing list or Github issues
 * Update the software and documentation as needed  


We recommend following the related package guidelines:

  * [Writing R Extensions manual](http://cran.r-project.org/doc/manuals/R-exts.html)
  * [Bioconductor guidelines](http://bioconductor.org/developers/package-guidelines/)
  * [rOpenSci guidelines](https://github.com/ropensci/rOpenSci/wiki/_pages)
  * [Advanced R programming](http://adv-r.had.co.nz/) site


Using Github branches
--------------------------

Each R package is organized into its own repository under the [rOpenGov Github organization](http://github.com/ropengov). Locate the R package in the [repository root directory](https://github.com/rOpenGov/sorvi) (not in a subdirectory). The repository and package name must be identical. An easy way to get started is to copy an existing package and use it as a template. Below, we use the [sorvi](https://github.com/rOpenGov/sorvi) package as an example.  

**Development version** Reserve the master branch for a fully tested version: validate your
package with R build and check before submitting material to the
master branch of the package repository. For instance with the sorvi
package, we always run [this
script](https://github.com/rOpenGov/sorvi/blob/master/inst/extras/build.cran.sh)
before pushing changes to the master branch. With a small delay, the
build report of your package will be publicly visible also in the
[Travis site](https://travis-ci.org/rOpenGov/sorvi) if you have set up
the travis scripts (see below).  

**Release version** The authors are recommended to submit a release version of the package to [CRAN](http://cran.r-project.org/submit.html). After CRAN release, add URL.CRAN field to your DESCRIPTION file to ensure the CRAN link will be added to the automatically generated [project table](http://ropengov.github.io/projects/) at the rOpenGov site.



Package development workflow
-----------------------------------

We will add more on the rOpenGov package development workflow later. Overall, we follow the [rOpenSci guidelines](https://github.com/ropensci/rOpenSci/wiki/rOpenSci-Workflow-Document) but applied to the rOpenGov site.  

The public can send [issues and bug reports]((https://github.com/ropengov/sorvi/issues)), [pull requests](https://github.com/louhos/sorvi/) etc. through Github. 



Automated build reports (Travis)
--------------------------

You can generate automated build reports for the package with [Travis](https://travis-ci.org/rOpenGov/sorvi):  add the [.travis.yml](https://github.com/rOpenGov/sorvi/blob/master/.travis.yml) script in your package root, and we will take of the rest. You can then check the build report for your package at https://travis-ci.org/rOpenGov/<yourpackagename>

You can also automatically add the latest package build status in your package [README](https://github.com/rOpenGov/sorvi/blob/master/README.md).


Documentation
-------------------

Include working examples in the documentation. These work also as a poor man's unit test.

1. Function man pages: preferably by [Roxygen](http://adv-r.had.co.nz/Documenting-functions.html). Include examples in all man pages.
1. Package documentation and examples (vignette). Use Rmarkdown and add the vignette to [/vignettes/<mypackagename>_tutorial.Rmd](https://github.com/rOpenGov/sorvi/blob/master/vignettes/sorvi_tutorial.Rmd); then the rOpenGov scripts will automatically generate an online tutorial for your package and link it to [rOpenGov website](http://ropengov.github.io/projects/) 



Network traffic statistics
----------------------------

Follow the package traffic statistics at your github site. See for instance the traffic analysis for [sorvi](https://github.com/rOpenGov/sorvi/graphs/traffic). We are planning to collect the statistics for all packages in one place soon.


License
-------------------------

Use an open license, preferably a [standard open license](http://wiki.fhcrc.org/bioc/opensource.org). The "License:" field in the DESCRIPTION file should name the license using one of R's standard specifications as in the Writing R Extensions manual. Be specific about the license version (e.g., GPL-2). You can look at examples from other rOpenGov packages.

Include only code that can be redistributed according to the package license. Be aware of the licensing agreements for packages you are depending on in your package. 

rOpenGov TaskViews
-------------------------

Specify one or more ropengov task-view categories in your DESCRIPTION
file. When the package base grows, we will need a way to automatically
categorize the packages by their themes, as in CRAN and
Bioconductor. Instructions to be added.


Package formatting
---------------

1. Follow an R style guide, or use formatR
1. Cite relevant methods and packages throughout package documentation
1. Avoid duplicating functionality available in other packages.
1. Use INCLUDE instead of DEPENDS for packages that provide functions purely for internal use 


Related material
-----------------

Related material that is not to be included in the package can be located in the [/inst/](https://github.com/rOpenGov/sorvi/tree/master/inst/extras) folder of the package and excluded from package build with the [.Rbuildignore](https://github.com/rOpenGov/sorvi/blob/master/.Rbuildignore) file in the root directory.  

Use a .Rbuildignore file to exclude unnecessary files such as .DS_Store, .project, .svn, cache file, log files, etc. from the package build. 