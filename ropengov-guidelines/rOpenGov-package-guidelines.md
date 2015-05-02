We have very few specific recommendations for rOpenGov packages beyond the standard R package development advice. New contributors, please read carefully. 


Package Maintainer Responsibilities
------------------------------------------------

The authors mentioned in the package DESCRIPTION file are asked to:

 * Connect with the community via ropengov-forum email list, IRC, Google+, and other [community forums](http://ropengov.github.io/contribute)
 * Response to feedback from users via the mailing list or Github issues
 * Update the software and documentation as needed  


We also recommend the related package guidelines:

  * [Writing R Extensions manual](http://cran.r-project.org/doc/manuals/R-exts.html)
  * [Bioconductor guidelines](http://bioconductor.org/developers/package-guidelines/)
  * [JTLeek instructions for R packages](https://github.com/jtleek/rpackages)
  * [rOpenSci guidelines](https://github.com/ropensci/rOpenSci/wiki/_pages)
  * [Advanced R programming](http://adv-r.had.co.nz/) site


Using Github branches
--------------------------

Each R package is organized into its own repository. You are welcome to host the package under the [rOpenGov Github organization](http://github.com/ropengov) or elsewhere in Github. In the latter case just let us know the repository address ot be added on the [project list](http://ropengov.github.io/projects/) Locate the R package in the [repository root directory](https://github.com/rOpenGov/sorvi) (not in a subdirectory). The repository and package name must be identical. Below, we use the [sorvi](https://github.com/rOpenGov/sorvi) package as an example.  

**Development version** Reserve the master branch for a fully tested version: validate your package with R build and check before submitting material to the master branch of the package repository. For instance with the sorvi
package, we always run [this script](https://github.com/rOpenGov/sorvi/blob/master/inst/extras/build.cran.sh)
before pushing changes to the master branch. With a small delay, the build report of your package will be publicly visible also in the [Travis site](https://travis-ci.org/rOpenGov/sorvi) if you have set up the travis scripts (see below).  

**Release version** Release version of the package should go to [CRAN](http://cran.r-project.org/submit.html). 

The public can send [issues and bug reports]((https://github.com/ropengov/sorvi/issues)), [pull requests](https://github.com/louhos/sorvi/) etc. through Github. 



Related material in .Rbuildignore
-----------------

Related material that is not to be included in the package can be located in the [/inst/](https://github.com/rOpenGov/sorvi/tree/master/inst/extras) folder of the package and excluded from package build with the [.Rbuildignore](https://github.com/rOpenGov/sorvi/blob/master/.Rbuildignore) file in the root directory. Use a .Rbuildignore file to exclude unnecessary files such as .DS_Store, .project, cache, log files, etc. from the package build. 



Automated build reports (Travis)
--------------------------

Automated build reports for the package are generated with [Travis](https://travis-ci.org/rOpenGov/sorvi): just add the [.travis.yml](https://github.com/rOpenGov/sorvi/blob/master/.travis.yml) script in your package root and notify us so we can add it on the list. You can then check the build report for your package at https://travis-ci.org/rOpenGov/yourpackagename

You can also add the latest package build status in your package [README](https://github.com/rOpenGov/sorvi/blob/master/README.md).


rOpenGov TaskViews
-------------------------

Specify one or more ropengov task-view categories in your DESCRIPTION file. When the package base grows, we will need a way to automatically categorize the packages by their themes, as in CRAN and Bioconductor. Instructions to be added.


Network traffic statistics
----------------------------

Follow the package traffic statistics at your github site. See for instance the traffic analysis for [sorvi](https://github.com/rOpenGov/sorvi/graphs/rtaffic).
