# gcamreport

[![Project Status: Active – The project has reached a stable, usable state and is being actively developed.](https://www.repostatus.org/badges/latest/active.svg)](https://www.repostatus.org/#active)
[![docs](https://github.com/bc3LC/gcamreport/actions/workflows/docs.yaml/badge.svg?branch=gcam-v7.0)](https://github.com/bc3LC/gcamreport/actions/workflows/docs.yaml) [![pages-build-deployment](https://github.com/bc3LC/gcamreport/actions/workflows/pages/pages-build-deployment/badge.svg)](https://github.com/bc3LC/gcamreport/actions/workflows/pages/pages-build-deployment) [![test_coverage](https://github.com/bc3LC/gcamreport/actions/workflows/test_coverage.yml/badge.svg?branch=gcam-v7.0)](https://github.com/bc3LC/gcamreport/actions/workflows/test_coverage.yml) [![codecov](https://codecov.io/gh/bc3LC/gcamreport/branch/gcam-v7.0/graph/badge.svg?token=GHV4F7TGFG)](https://codecov.io/gh/bc3LC/gcamreport) [![docker](https://github.com/bc3LC/gcamreport/actions/workflows/docker_impl.yaml/badge.svg?branch=gcam-v7.0)](https://github.com/bc3LC/gcamreport/actions/workflows/docker_impl.yaml) [![build](https://github.com/bc3LC/gcamreport/actions/workflows/build.yaml/badge.svg?branch=gcam-v7.0)](https://github.com/bc3LC/gcamreport/actions/workflows/build.yaml)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.10960370.svg)](https://doi.org/10.5281/zenodo.10960370)
[![paper](https://github.com/bc3LC/gcamreport/actions/workflows/draft-pdf.yml/badge.svg?branch=gcam-v7.0)](https://github.com/bc3LC/gcamreport/blob/gcam-v7.0/paper/paper.pdf)
[![status](https://joss.theoj.org/papers/816fd8765945cd5f6fe6d8d1fefdde19/status.svg)](https://joss.theoj.org/papers/816fd8765945cd5f6fe6d8d1fefdde19)

<!-- ------------------------>

<!-- ------------------------>

## <a name="contents"></a>Contents

<!-- ------------------------>

<!-- ------------------------>

-   [Contents](#contents)

-   [Introduction](#introduction)

-   [Installation Guide](#installation-guide)

    -   [With R](#with-r)
    
        -   [Light mode installation](#with-R-light-mode-installation)
        
        -   [Full mode installation](#with-R-full-mode-installation)

    -   [With Docker](#with-docker)

-   [Getting Started](#get-started)

-   [Warnings and Error Messages](#bugs)

<!-- ------------------------>

<!-- ------------------------>

## <a name="introduction"></a>Introduction

<!-- ------------------------>

<!-- ------------------------>

[Back to Contents](#contents)

`gcamreport` is a tool that generates a consistent dataset from any scenario run by the Global Change Analysis Model ([GCAM](http://www.globalchange.umd.edu/gcam/)) that meets the reporting requirements of the Integrated Assessment Modeling Consortium ([IAMC](https://www.iamconsortium.org/)). In addition, `gcamreport` includes an interactive user widget that allows users to generate and download plots live, as well as download reduced versions of the formatted dataset in spreadsheet format.

<!-- ------------------------>

<!-- ------------------------>

## <a name="installation-guide"></a>Installation Guide

<!-- ------------------------>

<!-- ------------------------>

[Back to Contents](#contents)

There are multiple equivalent ways to install this package:

### <a name="with-R"></a>With R

There are two ways to install the `gcamreport` package through R. The [light mode installation](#with-R-light-mode-installation) requires only R as it installs the `gcamreport` package directly from the GitHub repository. It is suitable for general use of the package but not compatible with the user interface. The [full mode installation](#with-R-full-mode-installation) requires R, Rstudio and cloning the GitHub repository. It is suitable for general use of the package and allows you to launch the user interface. It is also the best option if you are actively developing or modifying the `gcamreport` package, as it allows you to modify the mappings and functions to create suitable versions for your GCAM model.

#### <a name="with-R-light-mode-installation"></a>Light mode installation

1.  Requirements

    -   R (to download, click [here](https://www.r-project.org/))





2.  Open R and install the `gcamreport` package:

``` r
install.packages('devtools')
devtools::install_github('bc3LC/gcamreport')
```

Now `gcamreport` package is fully loaded. Enjoy! :smile:

**Note**:boom:: If you want to install specific `gcamreport` versions, indicate the tag or branch name when running the installation command. For instance:

``` r
# to install the taged version "v6.0.1"
devtools::install_github('bc3LC/gcamreport@v6.0.1')

# to install the branch version "gcam-v6.0"
devtools::install_github('bc3LC/gcamreport@gcam-v6.0')
```

<br>

#### <a name="with-R-full-mode-installation"></a>Full mode installation

1.  Requirements

    -   R (to download, click [here](https://www.r-project.org/))

    -   Rstudio (to download, click [here](https://www.rstudio.com/))

    -   Git (to download, click [here](https://git-scm.com/downloads/))

2.  Open git bash in the folder where you want to clone the repository and clone it:

``` bash
git clone https://github.com/bc3LC/gcamreport.git
```

3.  Load the `gcamreport` package: Open the `gcamreport` folder you just cloned and double-click the `gcamreport.Rproj` file. RStudio should open the project. Load the library:

``` r
install.packages('devtools')
devtools::load_all()
```

Now `gcamreport` package is fully loaded. Enjoy! :smile:

**Note**:boom:: If you want to install specific `gcamreport` versions, indicate the tag or branch name when cloning the repository. For instance:

``` bash
# to clone the taged version "v6.0.1":
git clone --branch v6.0.1 --single-branch https://github.com/bc3LC/gcamreport.git

# to clone the branch version "gcam-v6.0":
git clone --branch gcam-v6.0 https://github.com/bc3LC/gcamreport.git
```


<br>

### <a name="with-Docker"></a>With Docker

This installation method allows you not to worry about the R libraries and dependencies. Docker provides you with an already updated environment suitable for running the `gcamreport` package.

1.  Requirements

    -   Docker Desktop (to download, click [here](https://docs.docker.com/get-docker/))

    -   Git (to download, click [here](https://git-scm.com/downloads))

2.  Open git bash in the folder where you want to clone the repository and clone it:

``` bash
git clone https://github.com/bc3LC/gcamreport.git
```

3.  Open Docker Desktop (double-click the icon on your computer) and leave it running in the background.

4.  Inside a terminal (bash or cmd) pull the docker image:

``` bash
docker pull claudiarodes/gcamreport_docker:gcam-v7.0-v2
```

**Note**:exclamation:: This step requires 13.5GB of free space in your computer.

5.  Run the Docker container using your full path to the `gcamreport` folder:

``` bash
docker run -v /path/to/gcamreport:/app -p 4000:3838 -it claudiarodes/gcamreport_docker:gcam-v7.0-v2
```

This should prompt an R console in your terminal.

6.  Install the `gcamreport` package in the new R console:

``` r
remotes::install_github("bc3LC/gcamreport") #you can skip all updates in case you are asked
library(gcamreport)
```

Now `gcamreport` package is fully loaded. Enjoy! :smile:


**Note**:exclamation:: To access local files, you should place them in the `gcamreport` folder, which is now considered the root of the R session. Inside the R session it is referred to as `/app`.

**Note**:exclamation:: To reuse the docker image, you can simply perform steps 3, 5, and 6, since the docker image is already on your computer.

**Note**:exclamation:: If you followed the [Docker installation](#with-Docker), to open the user interface (UI) once it has been launched, either go to the Docker Desktop and type the last port started, or type <http://localhost:4000> in your browser.

<img src="https://raw.githubusercontent.com/bc3LC/gcamreport/gcam-v7.0/vignettes/readme_fig/shiny_error1.png" title="Click the last started docker port" alt="UI error" width="60%" height="60%"/>


**Note**:boom:: If you want to install previous `gcamreport` versions, indicate the tag or branch name when cloning the repository (step 2). For instance:

``` bash
# to clone the taged version "v6.0.1":
git clone --branch v6.0.1 --single-branch https://github.com/bc3LC/gcamreport.git

# to clone the branch version "gcam-v6.0":
git clone --branch gcam-v6.0 https://github.com/bc3LC/gcamreport.git
```

<br>

<!-- ------------------------>

<!-- ------------------------>

## <a name="get-started"></a>Getting Started

<!-- ------------------------>

<!-- ------------------------>

[Back to Contents](#contents)

The `gcamreport` package consists of a set of functions divided into two different blocks:

- Dataset generation: It creates or loads an existing project and automatically saves the generated dataset that meets the reporting requirements of the [IAMC](https://www.iamconsortium.org/). Main function: `generate_report()`. For more information, see this [tutorial](https://bc3lc.github.io/gcamreport/articles/Dataset_Generation_Tutorial.html) or type `??generate_report` in your R console. If you get any warning or error messages, you might want to look at the [Warnings and Error Messages](#bugs) section.

- Interactive user block: it launches an interactive widget that displays the dataset in tabular form, with the ability to filter, reorder and download live. It also displays plots and allows them to be downloaded, aggregated by variables, regions and scenarios. Main function: `launch_gcamreport_ui()`. For more information see this [tutorial](https://bc3lc.github.io/gcamreport/articles/Interactive_UI_Tutorial.html) or type `??launch_gcamreport_ui` in your R console. If you get any warning or error messages, it might be useful to have a look at the [Warnings and Error Messages](#bugs) section.


The package also includes some default input files (.Rda) that are read by the different functions. These can be changed by the user as detailed in [this tutorial](https://bc3lc.github.io/gcamreport/articles/Modify_Mapping_Template_Tutorial.html).

<br>

<!-- ------------------------>

<!-- ------------------------>

## <a name="bugs"></a>Warnings and Error Messages

<!-- ------------------------>

<!-- ------------------------>

[Back to Contents](#contents)

Some typical and already-known errors that can be easily solved! :bulb:

:computer: Error on "run("path/to/your/data/myData.dat")"

In your R console, you might see this error:

      > generate_report("path/to/your/data/myData.dat")
      [1] "Loading project..."
      [1] "Loading data, performing checks, and saving output..."
      [1] "ag_demand_clean"
      Error in rgcam::getQuery(prj, "demand balances by crop commodity") :
        getQuery: Query demand balances by crop commodity is not in any scenarios in the data set.

<details>

<summary>**Possible solution**</summary>

This problem is due to a wrong path specification. Thus, make sure that you specified correctly the path. In addition:

-   In case you are using `gcamreport` package following the [R installation](#with-r), try to copy the whole path to your data, for instance `C:\Users\username\Documents\path\to\your\data\myData.dat` if you are using a Windows distribution.

-   In case you are using `gcamreport` package following the [Docker installation](#with-docker):

    a)  make sure that your data is inside the `gcamreport` folder.

    b)  make sure that you type correctly the path to your `gcamreport` folder when running the docker image (5th step in the [Docker section](#with-docker))

    c)  make sure that you are pointing correctly to your data. For example, if in the `gcamreport` folder you have a folder called `amazingData` with your dataset `myData.dat`, you should refer to it as

``` r
  # option 1: full path
  generate_report("/app/amazingData/myData.dat")
  
  # option 2: partial path
  generate_report("amazingData/myData.dat")
```

</details>

<br>

:computer: Wired message when launching the UI when using the Docker installation.

After using the functions `generate_report()` or `launch_gcamreport_ui()` to launch the UI, you might get this message:

      Listening on http://0.0.0.0:3838
      /usr/bin/xdg-open: 882: www-browser: not found
      /usr/bin/xdg-open: 882: links2: not found
      /usr/bin/xdg-open: 882: elinks: not found
      /usr/bin/xdg-open: 882: links: not found
      /usr/bin/xdg-open: 882: lynx: not found
      /usr/bin/xdg-open: 882: w3m: not found
      xdg-open: no method available for opening 'http://127.0.0.1:3838' 

<details>

<summary>**Possible solution**</summary>

This is not an error! You simply need to either go to your Docker Desktop program and click the last started port

<img src="https://raw.githubusercontent.com/bc3LC/gcamreport/gcam-v7.0/vignettes/readme_fig/shiny_error1.png" title="Click the last started docker port" alt="UI error" width="50%" height="50%"/>

or open this url <http://localhost:4000> in your favourite browser.

</details>

<br>

:computer: Error when using the UI through Docker installation.

When oppening your *localhost*, you might see this error:

<img src="https://raw.githubusercontent.com/bc3LC/gcamreport/gcam-v7.0/vignettes/readme_fig/shiny_error2.png" title="UI error" alt="UI error" width="40%" height="40%"/>

<details>

<summary>**Possible solution**</summary>

Your UI is not running. Try to either use the `generate_report()` function or the `launch_gcamreport_ui()`.

</details>

<br>

:computer: Error related to *system* when using the Docker installation.

Once the R console is opened, you might see this message after introducing any command:

      System has not been booted with systemd as init system (PID 1). Can't operate.
      Failed to connect to bus: Host is down
      Warning message:
      In system("timedatectl", intern = TRUE) :
         running command 'timedatectl' had status 1 

<details>

<summary>**Possible solution**</summary>

Simply type `Ctrl+C` and run your command again.

</details>

<br>

**Note**::boom: For other errors, please check the troubleshooting sections of the [`generate_report` function](https://bc3lc.github.io/gcamreport/articles/Dataset_Generation_Tutorial.html#troubleshooting-for-the-generate_report-function) or the [user interface widget](https://bc3lc.github.io/gcamreport/articles/Interactive_UI_Tutorial.html#troubleshooting-when-launching-the-ui). If your error is not listed, please open an [Issue](https://github.com/bc3LC/gcamreport/issues) on the GitHub page with all the information to reproduce the crash.
