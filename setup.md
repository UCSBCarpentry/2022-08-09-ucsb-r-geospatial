# Overview

- You will need to download the data we use in the workshop, and have an 
up-to-date browser. 
- If you are attending this workshop remotely, please 
also install/update the Zoom video conferencing application.  
-For this 
workshop, we have [a cloud instance of RStudio](https://carpentryworkshop.lsit.ucsb.edu/) 
that comes with 
all the necessary packages. You will not need to install 
anything for the workshop.
-If you would like to go through the workshop with 
your local RStudio instead, you may follow the below instructions, make sure
to follow the instructions for setting up GDAL and the Spatial Extensions below.

## Data (Required)

You can download all of the data used in this workshop by clicking
[this download link](https://ndownloader.figshare.com/articles/2009586/versions/10). The file is 218.2 MB.

Clicking the download link will automatically download all of the files to your default download directory as a single compressed
(`.zip`) file. To expand this file, double click the folder icon in your file navigator application (for Macs, this is the Finder
application).

For a full description of the data used in this workshop see the [data page](https://github.com/datacarpentry/geospatial-workshop/blob/gh-pages/data).

## Zoom Install and Update
{% include install_instructions/videoconferencing.html %}

### Software

** You should already have **
| Software | Install | Manual | Available for | Description |
| -------- | ------------ | ------ | ------------- | ----------- |
| [R](https://www.r-project.org) | [Link](https://cloud.r-project.org) | [Link](https://cloud.r-project.org) | Linux, MacOS, Windows | Software environment for statistical and scientific computing |
| [RStudio](https://www.rstudio.com) | [Link](https://www.rstudio.com/products/rstudio/download/#download) | | Linux, MacOS, Windows | GUI for R |

Please update your base R to at least 4.1.1!

We provide quick instructions below for installing the various software 
needed for this workshop. At points, they assume familiarity with the 
command line and with installation in general. As there are different 
operating systems and many different versions of operating systems and 
environments, these may not work on your computer. If an installation 
doesn't work for you, please use our [LSIT Cloud RStudio](https://carpentryworkshop.lsit.ucsb.edu/)


### GDAL and the Spatial Extensions

The installation of the geospatial libraries GDAL, GEOS, and PROJ.4 
varies significantly based on operating system. These are all 
dependencies for `sf`, the `R` package that we will be using for spatial 
data operations throughout this workshop.

Mac users beware!

> ## Windows
>
>To install the geospatial libraries, install the latest version [RTools](https://cran.r-project.org/bin/windows/Rtools/)
>
{: .solution}

> ## macOS - Install with Packages (Beginner)
>
> If you have installed software such as QGIS or GRASS, you may
> already have most of these dependancies taken care of.
>
> You may or may not need to install various underlying components
> of GDAL. You can get everytin in one package by installin 
> the latest version of [Kyng Chaos's pre-built 
> package for GDAL Complete](http://www.kyngchaos.com/software/frameworks). Be aware that several other libraries are also installed, 
> including the UnixImageIO, SQLite3, and `NumPy`.  Please install all 
> items in the package.
>
> After downloading the package in the link above, you will need to 
> double-click the cardbord box icon to complete the installation. 
> Depending on your security settings, you may get a warning message 
> about "unidentified developers", but you may continue with the 
> installation. Please [contact 
> us](mailto:library-collaboratory@ucsb.edu) or attend the workshop 
> install party if you need help enabling the installation.
>
{: .solution}

> ## macOS - Install with Homebrew (Advanced)
>
> Alternatively, participants who are comfortable with the command line can install the geospatial libraries individually using [homebrew](https://brew.sh).
> We do not have the expertise to provide assistance on your installation using this method.
>
>~~~
>$ brew tap osgeo/osgeo4mac && brew tap --repair
>$ brew install proj
>$ brew install geos
>$ brew install gdal2
>~~~
>{: .language-bash}
>
{: .solution}

> ## Linux
>
> Steps for installing the geospatial libraries will vary based on which form of Linux you are using. These instructions are adapted from the [`sf` package's `README`](https://github.com/r-spatial/sf).
>
> For **Ubuntu**:
>
>~~~
>$ sudo add-apt-repository ppa:ubuntugis
>$ sudo apt-get update
>$ sudo apt-get install libgdal-dev libgeos-dev libproj-dev
>~~~
>{: .language-bash}
>
> For **Fedora**:
>
>~~~
>$ sudo dnf install gdal-devel proj-devel proj-epsg proj-nad geos-devel
>~~~
>{: .language-bash}
>
> For **Arch**:
>
>~~~
>$ pacman -S gdal proj geos
>~~~
>{: .language-bash}
>
> For **Debian**: The [rocker geospatial](https://github.com/rocker-org/geospatial) Dockerfiles may be helpful. Ubuntu Dockerfiles are found [here](https://github.com/r-spatial/sf/tree/master/inst/docker). These may be helpful to get an idea of the commands needed to install the necessary dependencies.
>
{: .solution}

### UDUNITS

Linux users will have to install UDUNITS separately. Like the geospatial libraries discussed above, this is a dependency for the `R` package `sf`. Due to conflicts, it does not install properly on Linux machines when installed as part of the `sf` installation process. It is therefore necessary to install it using the command line ahead of time.

> ## Linux
>
> Steps for installing the geospatial will vary based on which form of Linux you are using. These instructions are adapted from the [`sf` package's `README`](https://github.com/r-spatial/sf).
>
> For **Ubuntu**:
>
>~~~
>$ sudo apt-get install libudunits2-dev
>~~~
>{: .language-bash}
>
> For **Fedora**:
>
>~~~
>$ sudo dnf install udunits2-devel
>~~~
>{: .language-bash}
>
> For **Arch**:
>
>~~~
>$ pacaur/yaourt/whatever -S udunits
>~~~
>{: .language-bash}
>
> For **Debian**:
>
>~~~
>$ sudo apt-get install -y libudunits2-dev
>~~~
>{: .language-bash}
>
{: .solution}


### R

Participants who do not already have `R` installed should download and install it.

> ## Windows
>
>To install `R`, Windows users should select "Download R for Windows" from RStudio and CRAN's [cloud download page](https://cloud.r-project.org), which will automatically detect a CRAN mirror for you to use. Select the `base` subdirectory after choosing the Windows download page. A `.exe` executable file containing the necessary components of base R can be downloaded by clicking on "Download R 3.x.x for Windows".
>
{: .solution}

> ## macOS
>
>To install `R`, macOS users should select "Download R for (Mac) OS X" from RStudio and CRAN's [cloud download page](https://cloud.r-project.org), which will automatically detect a CRAN mirror for you to use. A `.pkg` file containing the necessary components of base R can be downloaded by clicking on the first available link (this will be the most recent), which will read `R-3.x.x.pkg`.
>
{: .solution}

> ## Linux
>
>To install `R`, Linux users should select "Download R for Linux" from RStudio and CRAN's [cloud download page](https://cloud.r-project.org), which will automatically detect a CRAN mirror for you to use. Instructions for a number of different Linux operating systems are available.
>
{: .solution}

### RStudio

RStudio is a GUI for using `R` that is available for Windows, macOS, and various Linux operating systems. It can be downloaded [here](https://www.rstudio.com/products/rstudio/download/). You will need the **free** Desktop version for your computer. *In order to address issues with `ggplot2`, learners and instructors should run a recent version of RStudio (v1.2 or greater).*

### R Packages

The following `R` packages are used in the various geospatial lessons.

* [`dplyr`](https://cran.r-project.org/package=dplyr)
* [`ggplot2`](https://cran.r-project.org/package=ggplot2)
* [`raster`](https://cran.r-project.org/package=raster)
* [`rgdal`](https://cran.r-project.org/package=rgdal)
* [`rasterVis`](https://cran.r-project.org/package=rasterVis)
* [`remotes`](https://cran.r-project.org/package=remotes)
* [`sf`](https://cran.r-project.org/package=sf)

To install these packages in RStudio, do the following:  
1\. Open RStudio by double-clicking the RStudio application icon. You should see
something like this:

![RStudio layout](/fig/01-rstudio.png)


2\. Type the following into the console and hit enter.

~~~
install.packages(c("dplyr", "ggplot2", "raster", "rgdal", "rasterVis", "sf"))
~~~
{: .language-r}

You should see a status message starting with:

~~~
trying URL 'https://cran.rstudio.com/bin/macosx/el-capitan/contrib/3.5/dplyr_0.7.6.tgz'
Content type 'application/x-gzip' length 5686536 bytes (5.4 MB)
==================================================
downloaded 5.4 MB

trying URL 'https://cran.rstudio.com/bin/macosx/el-capitan/contrib/3.5/ggplot2_3.0.0.tgz'
Content type 'application/x-gzip' length 3577658 bytes (3.4 MB)
==================================================
downloaded 3.4 MB
~~~
{: .output}

When the installation is complete, you will see a status message like:

~~~
The downloaded binary packages are in
/var/folders/7g/r8_n81y534z0vy5hxc6dx1t00000gn/T//RtmpJECKXM/downloaded_packages
~~~
{: .output}

You are now ready for the workshop!

<p>
  We maintain a list of common issues that occur during installation as a reference for instructors
  that may be useful on the
  <a href = "{{site.swc_github}}/workshop-template/wiki/Configuration-Problems-and-Solutions">Configuration Problems and Solutions wiki page</a>.
</p>
