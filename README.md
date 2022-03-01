# packagestats
Overloaded Library and Require Functions for Collecting Package Usage Statistics in R

## Installation

1. Pull the repository
2. Build the package: R CMD build packagestats
3. Edit a relevant .Rprofile file, either at the user or site level, to have the following two lines: 
        options(package.stats.enabled = TRUE)
        options(package.stats.method = "xalt")
4. Install the package. Make sure it is installed sitewide: R CMD INSTALL packagestats_0.0.5.0000.tar.gz
5. 
