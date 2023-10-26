# STAT 545A Mini Data Analysis

### Description  
This repository contains the files and code authored by Renessa Gomes as submission for the **STAT 545A Mini Data Analysis** project. This submission was completed according to the guidelines and requirements for [**Milestone 1**](https://stat545.stat.ubc.ca/mini-project/mini-project-1/) and [**Milestone 2**](https://stat545.stat.ubc.ca/mini-project/mini-project-2/). 

The purpose of **Milestone 1** is to explore a dataset using `dplyr` to manipulate and visualize data. The analysis should investigate a clear research question and be presented in a reproducible format. The purpose of **Milestone 2** is to tidy data for an intended analysis using `tidyr`, model objects to data, read data and write data to specific output file formats. 

The dataset selected for this analysis was the `cancer_sample` dataset contained in the `datateachr` package.

### Files in the Repository  
This repository contains the following files:  
* `README.md` : introduction and guide to this repository 
* `milestone-1` : folder containing files related to Milestone 1
  * `mini-project-1.Rmd` : milestone 1 assignment guidelines and completed analysis  
  * `mini-project-1.md` : knit output file and most up-to-date version of `mini-project-1.Rmd`
  * `mini-project-1_files` : png files of graphs for GitHub view of `mini-project-1.md`
* `milestone-2` : folder containing files related to Milestone 2
  * `mini-project-2.Rmd` : milestone 2 assignment guidelines and completed analysis  
  * `mini-project-2.md` : knit output file and most up-to-date version of `mini-project-2.Rmd`
  * `mini-project-2_files` : png files of graphs for GitHub view of `mini-project-2.md`
* `output` : folder containing outputted files for Milestone 2 

### Running the Code  
The following packages are required to run the code in `mini-project-1-Rmd` and may need to be installed:  
* `datateachr` : contains the datasets for analysis  
* `tidyverse` : contains `dplyr` for data wrangling and `ggplot2` for data visualization  
* `ggpubr` : an extension of `ggplot2` that enables multi-plot layouts for data visualization

The following packages are required to run the code in `mini-project-2-Rmd` and may need to be installed:  
* `datateachr` : contains the datasets for analysis  
* `tidyverse` : contains `dplyr` for data wrangling and `ggplot2` for data visualization  
* `ggpubr` : an extension of `ggplot2` that enables multi-plot layouts for data visualization
* `rstatix` : contains `identify_outliers()` function to identify outliers
* `here` : contains `here()` function to use relative paths to/from this project for reproducible file reading/writing
