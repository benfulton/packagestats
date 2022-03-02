# packagestats
Overloaded Library and Require Functions for Collecting Package Usage Statistics in R

## Installation

1. Pull the repository
2. Build the package: `R CMD build packagestats`
3. Edit a relevant .Rprofile file, either at the user or site level, to have the following two lines: 
```
        options(package.stats.enabled = TRUE)
        options(package.stats.method = "xalt")
```
4. Install the package. Make sure it is installed sitewide: `R CMD INSTALL packagestats_0.0.5.0000.tar.gz`
5. Modify the site profile to have the following lines:
```
        # Enable the package statistics
        options(package.stats.enabled = TRUE)

        # Set the logging method to use XALT
        options(package.stats.method = "xalt")

        # Set the XALT environment variable specifying the UUID of the R session
        options(package.stats.xalt_run_uuid_var = "XALT_RUN_UUID")

        # Set the directory path to the XALT installation being used
        options(package.stats.xalt_dir_var = "XALT_DIR")

        # Set the relative path to the XALT package logging utility
        options(package.stats.xalt_exec_path = "libexec/xalt_record_pkg")

        # Prevent logging of XALT warning messages
        options(package.stats.suppress.xalt.warnings = FALSE)

        # Add packagestats to the list of default packages
        p <- options("defaultPackages")
        defaultPackages <- p$defaultPackages
        defaultPackages <- c("packagestats", defaultPackages)
        options("defaultPackages" = defaultPackages)
```

The site profile is named `RProfile.site` and should be located in the lib64/R/etc/ subdirectory of the R directory.
