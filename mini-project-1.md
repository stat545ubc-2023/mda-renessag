Mini Data-Analysis Deliverable 1
================

# Welcome to your (maybe) first-ever data analysis project!

And hopefully the first of many. Let’s get started:

1.  Install the [`datateachr`](https://github.com/UBC-MDS/datateachr)
    package by typing the following into your **R terminal**:

<!-- -->

    install.packages("devtools")
    devtools::install_github("UBC-MDS/datateachr")

2.  Load the packages below.

``` r
library(datateachr)
library(tidyverse)
```

    ## ── Attaching core tidyverse packages ──────────────────────── tidyverse 2.0.0 ──
    ## ✔ dplyr     1.1.3     ✔ readr     2.1.4
    ## ✔ forcats   1.0.0     ✔ stringr   1.5.0
    ## ✔ ggplot2   3.4.3     ✔ tibble    3.2.1
    ## ✔ lubridate 1.9.2     ✔ tidyr     1.3.0
    ## ✔ purrr     1.0.2     
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()
    ## ℹ Use the conflicted package (<http://conflicted.r-lib.org/>) to force all conflicts to become errors

``` r
library(ggpubr) #graphing multiple ggplot2 plots in the same figure
```

3.  Make a repository in the <https://github.com/stat545ubc-2023>
    Organization. You can do this by following the steps found on canvas
    in the entry called [MDA: Create a
    repository](https://canvas.ubc.ca/courses/126199/pages/mda-create-a-repository).
    One completed, your repository should automatically be listed as
    part of the stat545ubc-2023 Organization.

# Instructions

## For Both Milestones

- Each milestone has explicit tasks. Tasks that are more challenging
  will often be allocated more points.

- Each milestone will be also graded for reproducibility, cleanliness,
  and coherence of the overall Github submission.

- While the two milestones will be submitted as independent
  deliverables, the analysis itself is a continuum - think of it as two
  chapters to a story. Each chapter, or in this case, portion of your
  analysis, should be easily followed through by someone unfamiliar with
  the content.
  [Here](https://swcarpentry.github.io/r-novice-inflammation/06-best-practices-R/)
  is a good resource for what constitutes “good code”. Learning good
  coding practices early in your career will save you hassle later on!

- The milestones will be equally weighted.

## For Milestone 1

**To complete this milestone**, edit [this very `.Rmd`
file](https://raw.githubusercontent.com/UBC-STAT/stat545.stat.ubc.ca/master/content/mini-project/mini-project-1.Rmd)
directly. Fill in the sections that are tagged with
`<!--- start your work below --->`.

**To submit this milestone**, make sure to knit this `.Rmd` file to an
`.md` file by changing the YAML output settings from
`output: html_document` to `output: github_document`. Commit and push
all of your work to the mini-analysis GitHub repository you made
earlier, and tag a release on GitHub. Then, submit a link to your tagged
release on canvas.

**Points**: This milestone is worth 36 points: 30 for your analysis, and
6 for overall reproducibility, cleanliness, and coherence of the Github
submission.

# Learning Objectives

By the end of this milestone, you should:

- Become familiar with your dataset of choosing
- Select 4 questions that you would like to answer with your data
- Generate a reproducible and clear report using R Markdown
- Become familiar with manipulating and summarizing your data in tibbles
  using `dplyr`, with a research question in mind.

# Task 1: Choose your favorite dataset

The `datateachr` package by Hayley Boyce and Jordan Bourak currently
composed of 7 semi-tidy datasets for educational purposes. Here is a
brief description of each dataset:

- *apt_buildings*: Acquired courtesy of The City of Toronto’s Open Data
  Portal. It currently has 3455 rows and 37 columns.

- *building_permits*: Acquired courtesy of The City of Vancouver’s Open
  Data Portal. It currently has 20680 rows and 14 columns.

- *cancer_sample*: Acquired courtesy of UCI Machine Learning Repository.
  It currently has 569 rows and 32 columns.

- *flow_sample*: Acquired courtesy of The Government of Canada’s
  Historical Hydrometric Database. It currently has 218 rows and 7
  columns.

- *parking_meters*: Acquired courtesy of The City of Vancouver’s Open
  Data Portal. It currently has 10032 rows and 22 columns.

- *steam_games*: Acquired courtesy of Kaggle. It currently has 40833
  rows and 21 columns.

- *vancouver_trees*: Acquired courtesy of The City of Vancouver’s Open
  Data Portal. It currently has 146611 rows and 20 columns.

**Things to keep in mind**

- We hope that this project will serve as practice for carrying our your
  own *independent* data analysis. Remember to comment your code, be
  explicit about what you are doing, and write notes in this markdown
  document when you feel that context is required. As you advance in the
  project, prompts and hints to do this will be diminished - it’ll be up
  to you!

- Before choosing a dataset, you should always keep in mind **your
  goal**, or in other ways, *what you wish to achieve with this data*.
  This mini data-analysis project focuses on *data wrangling*,
  *tidying*, and *visualization*. In short, it’s a way for you to get
  your feet wet with exploring data on your own.

And that is exactly the first thing that you will do!

1.1 **(1 point)** Out of the 7 datasets available in the `datateachr`
package, choose **4** that appeal to you based on their description.
Write your choices below:

**Note**: We encourage you to use the ones in the `datateachr` package,
but if you have a dataset that you’d really like to use, you can include
it here. But, please check with a member of the teaching team to see
whether the dataset is of appropriate complexity. Also, include a
**brief** description of the dataset here to help the teaching team
understand your data.

<!-------------------------- Start your work below ---------------------------->

## Selected data sets to explore

1.  **cancer_sample**  
2.  **vancouver_trees**  
3.  **steam_games**  
4.  **parking_meters**

<!----------------------------------------------------------------------------->

1.2 **(6 points)** One way to narrowing down your selection is to
*explore* the datasets. Use your knowledge of dplyr to find out at least
*3* attributes about each of these datasets (an attribute is something
such as number of rows, variables, class type…). The goal here is to
have an idea of *what the data looks like*.

*Hint:* This is one of those times when you should think about the
cleanliness of your analysis. I added a single code chunk for you below,
but do you want to use more than one? Would you like to write more
comments outside of the code chunk?

<!-------------------------- Start your work below ---------------------------->

## Exploring dimensions of each dataset

The **cancer_sample** dataset has 569 rows and 32 columns.

``` r
#summarizing dimensions and variables of cancer_sample
glimpse(cancer_sample)
```

    ## Rows: 569
    ## Columns: 32
    ## $ ID                      <dbl> 842302, 842517, 84300903, 84348301, 84358402, …
    ## $ diagnosis               <chr> "M", "M", "M", "M", "M", "M", "M", "M", "M", "…
    ## $ radius_mean             <dbl> 17.990, 20.570, 19.690, 11.420, 20.290, 12.450…
    ## $ texture_mean            <dbl> 10.38, 17.77, 21.25, 20.38, 14.34, 15.70, 19.9…
    ## $ perimeter_mean          <dbl> 122.80, 132.90, 130.00, 77.58, 135.10, 82.57, …
    ## $ area_mean               <dbl> 1001.0, 1326.0, 1203.0, 386.1, 1297.0, 477.1, …
    ## $ smoothness_mean         <dbl> 0.11840, 0.08474, 0.10960, 0.14250, 0.10030, 0…
    ## $ compactness_mean        <dbl> 0.27760, 0.07864, 0.15990, 0.28390, 0.13280, 0…
    ## $ concavity_mean          <dbl> 0.30010, 0.08690, 0.19740, 0.24140, 0.19800, 0…
    ## $ concave_points_mean     <dbl> 0.14710, 0.07017, 0.12790, 0.10520, 0.10430, 0…
    ## $ symmetry_mean           <dbl> 0.2419, 0.1812, 0.2069, 0.2597, 0.1809, 0.2087…
    ## $ fractal_dimension_mean  <dbl> 0.07871, 0.05667, 0.05999, 0.09744, 0.05883, 0…
    ## $ radius_se               <dbl> 1.0950, 0.5435, 0.7456, 0.4956, 0.7572, 0.3345…
    ## $ texture_se              <dbl> 0.9053, 0.7339, 0.7869, 1.1560, 0.7813, 0.8902…
    ## $ perimeter_se            <dbl> 8.589, 3.398, 4.585, 3.445, 5.438, 2.217, 3.18…
    ## $ area_se                 <dbl> 153.40, 74.08, 94.03, 27.23, 94.44, 27.19, 53.…
    ## $ smoothness_se           <dbl> 0.006399, 0.005225, 0.006150, 0.009110, 0.0114…
    ## $ compactness_se          <dbl> 0.049040, 0.013080, 0.040060, 0.074580, 0.0246…
    ## $ concavity_se            <dbl> 0.05373, 0.01860, 0.03832, 0.05661, 0.05688, 0…
    ## $ concave_points_se       <dbl> 0.015870, 0.013400, 0.020580, 0.018670, 0.0188…
    ## $ symmetry_se             <dbl> 0.03003, 0.01389, 0.02250, 0.05963, 0.01756, 0…
    ## $ fractal_dimension_se    <dbl> 0.006193, 0.003532, 0.004571, 0.009208, 0.0051…
    ## $ radius_worst            <dbl> 25.38, 24.99, 23.57, 14.91, 22.54, 15.47, 22.8…
    ## $ texture_worst           <dbl> 17.33, 23.41, 25.53, 26.50, 16.67, 23.75, 27.6…
    ## $ perimeter_worst         <dbl> 184.60, 158.80, 152.50, 98.87, 152.20, 103.40,…
    ## $ area_worst              <dbl> 2019.0, 1956.0, 1709.0, 567.7, 1575.0, 741.6, …
    ## $ smoothness_worst        <dbl> 0.1622, 0.1238, 0.1444, 0.2098, 0.1374, 0.1791…
    ## $ compactness_worst       <dbl> 0.6656, 0.1866, 0.4245, 0.8663, 0.2050, 0.5249…
    ## $ concavity_worst         <dbl> 0.71190, 0.24160, 0.45040, 0.68690, 0.40000, 0…
    ## $ concave_points_worst    <dbl> 0.26540, 0.18600, 0.24300, 0.25750, 0.16250, 0…
    ## $ symmetry_worst          <dbl> 0.4601, 0.2750, 0.3613, 0.6638, 0.2364, 0.3985…
    ## $ fractal_dimension_worst <dbl> 0.11890, 0.08902, 0.08758, 0.17300, 0.07678, 0…

The **vancouver_trees** dataset has 146,611 rows and 20 columns.

``` r
#summarizing dimensions and variables of vancouver_trees
glimpse(vancouver_trees)
```

    ## Rows: 146,611
    ## Columns: 20
    ## $ tree_id            <dbl> 149556, 149563, 149579, 149590, 149604, 149616, 149…
    ## $ civic_number       <dbl> 494, 450, 4994, 858, 5032, 585, 4909, 4925, 4969, 7…
    ## $ std_street         <chr> "W 58TH AV", "W 58TH AV", "WINDSOR ST", "E 39TH AV"…
    ## $ genus_name         <chr> "ULMUS", "ZELKOVA", "STYRAX", "FRAXINUS", "ACER", "…
    ## $ species_name       <chr> "AMERICANA", "SERRATA", "JAPONICA", "AMERICANA", "C…
    ## $ cultivar_name      <chr> "BRANDON", NA, NA, "AUTUMN APPLAUSE", NA, "CHANTICL…
    ## $ common_name        <chr> "BRANDON ELM", "JAPANESE ZELKOVA", "JAPANESE SNOWBE…
    ## $ assigned           <chr> "N", "N", "N", "Y", "N", "N", "N", "N", "N", "N", "…
    ## $ root_barrier       <chr> "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "…
    ## $ plant_area         <chr> "N", "N", "4", "4", "4", "B", "6", "6", "3", "3", "…
    ## $ on_street_block    <dbl> 400, 400, 4900, 800, 5000, 500, 4900, 4900, 4900, 7…
    ## $ on_street          <chr> "W 58TH AV", "W 58TH AV", "WINDSOR ST", "E 39TH AV"…
    ## $ neighbourhood_name <chr> "MARPOLE", "MARPOLE", "KENSINGTON-CEDAR COTTAGE", "…
    ## $ street_side_name   <chr> "EVEN", "EVEN", "EVEN", "EVEN", "EVEN", "ODD", "ODD…
    ## $ height_range_id    <dbl> 2, 4, 3, 4, 2, 2, 3, 3, 2, 2, 2, 5, 3, 2, 2, 2, 2, …
    ## $ diameter           <dbl> 10.00, 10.00, 4.00, 18.00, 9.00, 5.00, 15.00, 14.00…
    ## $ curb               <chr> "N", "N", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "…
    ## $ date_planted       <date> 1999-01-13, 1996-05-31, 1993-11-22, 1996-04-29, 19…
    ## $ longitude          <dbl> -123.1161, -123.1147, -123.0846, -123.0870, -123.08…
    ## $ latitude           <dbl> 49.21776, 49.21776, 49.23938, 49.23469, 49.23894, 4…

The **steam_games** dataset has 40,833 rows and 21 columns.

``` r
#summarizing dimensions and variables of steam_games
glimpse(steam_games)
```

    ## Rows: 40,833
    ## Columns: 21
    ## $ id                       <dbl> 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14…
    ## $ url                      <chr> "https://store.steampowered.com/app/379720/DO…
    ## $ types                    <chr> "app", "app", "app", "app", "app", "bundle", …
    ## $ name                     <chr> "DOOM", "PLAYERUNKNOWN'S BATTLEGROUNDS", "BAT…
    ## $ desc_snippet             <chr> "Now includes all three premium DLC packs (Un…
    ## $ recent_reviews           <chr> "Very Positive,(554),- 89% of the 554 user re…
    ## $ all_reviews              <chr> "Very Positive,(42,550),- 92% of the 42,550 u…
    ## $ release_date             <chr> "May 12, 2016", "Dec 21, 2017", "Apr 24, 2018…
    ## $ developer                <chr> "id Software", "PUBG Corporation", "Harebrain…
    ## $ publisher                <chr> "Bethesda Softworks,Bethesda Softworks", "PUB…
    ## $ popular_tags             <chr> "FPS,Gore,Action,Demons,Shooter,First-Person,…
    ## $ game_details             <chr> "Single-player,Multi-player,Co-op,Steam Achie…
    ## $ languages                <chr> "English,French,Italian,German,Spanish - Spai…
    ## $ achievements             <dbl> 54, 37, 128, NA, NA, NA, 51, 55, 34, 43, 72, …
    ## $ genre                    <chr> "Action", "Action,Adventure,Massively Multipl…
    ## $ game_description         <chr> "About This Game Developed by id software, th…
    ## $ mature_content           <chr> NA, "Mature Content Description  The develope…
    ## $ minimum_requirements     <chr> "Minimum:,OS:,Windows 7/8.1/10 (64-bit versio…
    ## $ recommended_requirements <chr> "Recommended:,OS:,Windows 7/8.1/10 (64-bit ve…
    ## $ original_price           <dbl> 19.99, 29.99, 39.99, 44.99, 0.00, NA, 59.99, …
    ## $ discount_price           <dbl> 14.99, NA, NA, NA, NA, 35.18, 70.42, 17.58, N…

The **parking_meters** dataset has 10,032 rows and 22 columns.

``` r
#summarizing dimensions and variables of parking_meters
glimpse(parking_meters)
```

    ## Rows: 10,032
    ## Columns: 22
    ## $ meter_head     <chr> "Twin", "Pay Station", "Twin", "Single", "Twin", "Twin"…
    ## $ r_mf_9a_6p     <chr> "$2.00", "$1.00", "$1.00", "$1.00", "$2.00", "$2.00", "…
    ## $ r_mf_6p_10     <chr> "$4.00", "$1.00", "$1.00", "$1.00", "$1.00", "$1.00", "…
    ## $ r_sa_9a_6p     <chr> "$2.00", "$1.00", "$1.00", "$1.00", "$2.00", "$2.00", "…
    ## $ r_sa_6p_10     <chr> "$4.00", "$1.00", "$1.00", "$1.00", "$1.00", "$1.00", "…
    ## $ r_su_9a_6p     <chr> "$2.00", "$1.00", "$1.00", "$1.00", "$2.00", "$2.00", "…
    ## $ r_su_6p_10     <chr> "$4.00", "$1.00", "$1.00", "$1.00", "$1.00", "$1.00", "…
    ## $ rate_misc      <chr> NA, "$ .50", NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA…
    ## $ time_in_effect <chr> "METER IN EFFECT: 9:00 AM TO 10:00 PM", "METER IN EFFEC…
    ## $ t_mf_9a_6p     <chr> "2 Hr", "10 Hrs", "2 Hr", "2 Hr", "2 Hr", "3 Hr", "2 Hr…
    ## $ t_mf_6p_10     <chr> "4 Hr", "10 Hrs", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr…
    ## $ t_sa_9a_6p     <chr> "2 Hr", "10 Hrs", "2 Hr", "2 Hr", "2 Hr", "3 Hr", "2 Hr…
    ## $ t_sa_6p_10     <chr> "4 Hr", "10 Hrs", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr…
    ## $ t_su_9a_6p     <chr> "2 Hr", "10 Hrs", "2 Hr", "2 Hr", "2 Hr", "3 Hr", "2 Hr…
    ## $ t_su_6p_10     <chr> "4 Hr", "10 Hrs", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr…
    ## $ time_misc      <chr> NA, "No Time Limit", NA, NA, NA, NA, NA, NA, NA, NA, NA…
    ## $ credit_card    <chr> "No", "Yes", "No", "No", "No", "No", "No", "No", "No", …
    ## $ pay_phone      <chr> "66890", "59916", "57042", "57159", "51104", "60868", "…
    ## $ longitude      <dbl> -123.1289, -123.0982, -123.1013, -123.1862, -123.1278, …
    ## $ latitude       <dbl> 49.28690, 49.27215, 49.25468, 49.26341, 49.26354, 49.27…
    ## $ geo_local_area <chr> "West End", "Strathcona", "Riley Park", "West Point Gre…
    ## $ meter_id       <chr> "670805", "471405", "C80145", "D03704", "301023", "5913…

## Determining the class of each dataset

The **cancer_sample** dataset is a subclass of a tibble data frame.

``` r
#determining class of cancer_sample
class(cancer_sample)
```

    ## [1] "spec_tbl_df" "tbl_df"      "tbl"         "data.frame"

The **vancouver_trees** dataset is classed as a tibble.

``` r
#determining class of vancouver_trees
class(vancouver_trees)
```

    ## [1] "tbl_df"     "tbl"        "data.frame"

The **steam_games** dataset is a subclass of a tibble data frame.

``` r
#determining class of steam_games
class(steam_games)
```

    ## [1] "spec_tbl_df" "tbl_df"      "tbl"         "data.frame"

The **parking_meters** dataset is classed as a tibble.

``` r
#determining class
class(parking_meters)
```

    ## [1] "tbl_df"     "tbl"        "data.frame"

## Exploring variables of each dataset

The **cancer_sample** dataset consists almost entirely of numerical data
with one column of character objects. There is no missing data in this
data set.

``` r
#defining class of each variable in cancer_sample
summary(cancer_sample)
```

    ##        ID             diagnosis          radius_mean      texture_mean  
    ##  Min.   :     8670   Length:569         Min.   : 6.981   Min.   : 9.71  
    ##  1st Qu.:   869218   Class :character   1st Qu.:11.700   1st Qu.:16.17  
    ##  Median :   906024   Mode  :character   Median :13.370   Median :18.84  
    ##  Mean   : 30371831                      Mean   :14.127   Mean   :19.29  
    ##  3rd Qu.:  8813129                      3rd Qu.:15.780   3rd Qu.:21.80  
    ##  Max.   :911320502                      Max.   :28.110   Max.   :39.28  
    ##  perimeter_mean     area_mean      smoothness_mean   compactness_mean 
    ##  Min.   : 43.79   Min.   : 143.5   Min.   :0.05263   Min.   :0.01938  
    ##  1st Qu.: 75.17   1st Qu.: 420.3   1st Qu.:0.08637   1st Qu.:0.06492  
    ##  Median : 86.24   Median : 551.1   Median :0.09587   Median :0.09263  
    ##  Mean   : 91.97   Mean   : 654.9   Mean   :0.09636   Mean   :0.10434  
    ##  3rd Qu.:104.10   3rd Qu.: 782.7   3rd Qu.:0.10530   3rd Qu.:0.13040  
    ##  Max.   :188.50   Max.   :2501.0   Max.   :0.16340   Max.   :0.34540  
    ##  concavity_mean    concave_points_mean symmetry_mean    fractal_dimension_mean
    ##  Min.   :0.00000   Min.   :0.00000     Min.   :0.1060   Min.   :0.04996       
    ##  1st Qu.:0.02956   1st Qu.:0.02031     1st Qu.:0.1619   1st Qu.:0.05770       
    ##  Median :0.06154   Median :0.03350     Median :0.1792   Median :0.06154       
    ##  Mean   :0.08880   Mean   :0.04892     Mean   :0.1812   Mean   :0.06280       
    ##  3rd Qu.:0.13070   3rd Qu.:0.07400     3rd Qu.:0.1957   3rd Qu.:0.06612       
    ##  Max.   :0.42680   Max.   :0.20120     Max.   :0.3040   Max.   :0.09744       
    ##    radius_se        texture_se      perimeter_se       area_se       
    ##  Min.   :0.1115   Min.   :0.3602   Min.   : 0.757   Min.   :  6.802  
    ##  1st Qu.:0.2324   1st Qu.:0.8339   1st Qu.: 1.606   1st Qu.: 17.850  
    ##  Median :0.3242   Median :1.1080   Median : 2.287   Median : 24.530  
    ##  Mean   :0.4052   Mean   :1.2169   Mean   : 2.866   Mean   : 40.337  
    ##  3rd Qu.:0.4789   3rd Qu.:1.4740   3rd Qu.: 3.357   3rd Qu.: 45.190  
    ##  Max.   :2.8730   Max.   :4.8850   Max.   :21.980   Max.   :542.200  
    ##  smoothness_se      compactness_se      concavity_se     concave_points_se 
    ##  Min.   :0.001713   Min.   :0.002252   Min.   :0.00000   Min.   :0.000000  
    ##  1st Qu.:0.005169   1st Qu.:0.013080   1st Qu.:0.01509   1st Qu.:0.007638  
    ##  Median :0.006380   Median :0.020450   Median :0.02589   Median :0.010930  
    ##  Mean   :0.007041   Mean   :0.025478   Mean   :0.03189   Mean   :0.011796  
    ##  3rd Qu.:0.008146   3rd Qu.:0.032450   3rd Qu.:0.04205   3rd Qu.:0.014710  
    ##  Max.   :0.031130   Max.   :0.135400   Max.   :0.39600   Max.   :0.052790  
    ##   symmetry_se       fractal_dimension_se  radius_worst   texture_worst  
    ##  Min.   :0.007882   Min.   :0.0008948    Min.   : 7.93   Min.   :12.02  
    ##  1st Qu.:0.015160   1st Qu.:0.0022480    1st Qu.:13.01   1st Qu.:21.08  
    ##  Median :0.018730   Median :0.0031870    Median :14.97   Median :25.41  
    ##  Mean   :0.020542   Mean   :0.0037949    Mean   :16.27   Mean   :25.68  
    ##  3rd Qu.:0.023480   3rd Qu.:0.0045580    3rd Qu.:18.79   3rd Qu.:29.72  
    ##  Max.   :0.078950   Max.   :0.0298400    Max.   :36.04   Max.   :49.54  
    ##  perimeter_worst    area_worst     smoothness_worst  compactness_worst
    ##  Min.   : 50.41   Min.   : 185.2   Min.   :0.07117   Min.   :0.02729  
    ##  1st Qu.: 84.11   1st Qu.: 515.3   1st Qu.:0.11660   1st Qu.:0.14720  
    ##  Median : 97.66   Median : 686.5   Median :0.13130   Median :0.21190  
    ##  Mean   :107.26   Mean   : 880.6   Mean   :0.13237   Mean   :0.25427  
    ##  3rd Qu.:125.40   3rd Qu.:1084.0   3rd Qu.:0.14600   3rd Qu.:0.33910  
    ##  Max.   :251.20   Max.   :4254.0   Max.   :0.22260   Max.   :1.05800  
    ##  concavity_worst  concave_points_worst symmetry_worst   fractal_dimension_worst
    ##  Min.   :0.0000   Min.   :0.00000      Min.   :0.1565   Min.   :0.05504        
    ##  1st Qu.:0.1145   1st Qu.:0.06493      1st Qu.:0.2504   1st Qu.:0.07146        
    ##  Median :0.2267   Median :0.09993      Median :0.2822   Median :0.08004        
    ##  Mean   :0.2722   Mean   :0.11461      Mean   :0.2901   Mean   :0.08395        
    ##  3rd Qu.:0.3829   3rd Qu.:0.16140      3rd Qu.:0.3179   3rd Qu.:0.09208        
    ##  Max.   :1.2520   Max.   :0.29100      Max.   :0.6638   Max.   :0.20750

``` r
#previewing cancer_sample
head(cancer_sample)
```

    ## # A tibble: 6 × 32
    ##         ID diagnosis radius_mean texture_mean perimeter_mean area_mean
    ##      <dbl> <chr>           <dbl>        <dbl>          <dbl>     <dbl>
    ## 1   842302 M                18.0         10.4          123.      1001 
    ## 2   842517 M                20.6         17.8          133.      1326 
    ## 3 84300903 M                19.7         21.2          130       1203 
    ## 4 84348301 M                11.4         20.4           77.6      386.
    ## 5 84358402 M                20.3         14.3          135.      1297 
    ## 6   843786 M                12.4         15.7           82.6      477.
    ## # ℹ 26 more variables: smoothness_mean <dbl>, compactness_mean <dbl>,
    ## #   concavity_mean <dbl>, concave_points_mean <dbl>, symmetry_mean <dbl>,
    ## #   fractal_dimension_mean <dbl>, radius_se <dbl>, texture_se <dbl>,
    ## #   perimeter_se <dbl>, area_se <dbl>, smoothness_se <dbl>,
    ## #   compactness_se <dbl>, concavity_se <dbl>, concave_points_se <dbl>,
    ## #   symmetry_se <dbl>, fractal_dimension_se <dbl>, radius_worst <dbl>,
    ## #   texture_worst <dbl>, perimeter_worst <dbl>, area_worst <dbl>, …

The **vancouver_trees** dataset is equal parts between character objects
and numerical data. There also appears to be a lot of missing data in
the `date_planted`, `longitude` and `latitude` columns, based on the
`summary()` output.

``` r
#defining class of each variable in vancouver_trees
summary(vancouver_trees)
```

    ##     tree_id        civic_number    std_street         genus_name       
    ##  Min.   :    12   Min.   :    0   Length:146611      Length:146611     
    ##  1st Qu.: 65464   1st Qu.: 1306   Class :character   Class :character  
    ##  Median :134903   Median : 2604   Mode  :character   Mode  :character  
    ##  Mean   :131892   Mean   : 2937                                        
    ##  3rd Qu.:194450   3rd Qu.: 4005                                        
    ##  Max.   :266203   Max.   :17888                                        
    ##                                                                        
    ##  species_name       cultivar_name      common_name          assigned        
    ##  Length:146611      Length:146611      Length:146611      Length:146611     
    ##  Class :character   Class :character   Class :character   Class :character  
    ##  Mode  :character   Mode  :character   Mode  :character   Mode  :character  
    ##                                                                             
    ##                                                                             
    ##                                                                             
    ##                                                                             
    ##  root_barrier        plant_area        on_street_block  on_street        
    ##  Length:146611      Length:146611      Min.   :   0    Length:146611     
    ##  Class :character   Class :character   1st Qu.:1300    Class :character  
    ##  Mode  :character   Mode  :character   Median :2600    Mode  :character  
    ##                                        Mean   :2909                      
    ##                                        3rd Qu.:4000                      
    ##                                        Max.   :9900                      
    ##                                                                          
    ##  neighbourhood_name street_side_name   height_range_id     diameter     
    ##  Length:146611      Length:146611      Min.   : 0.000   Min.   :  0.00  
    ##  Class :character   Class :character   1st Qu.: 1.000   1st Qu.:  3.50  
    ##  Mode  :character   Mode  :character   Median : 2.000   Median :  9.00  
    ##                                        Mean   : 2.627   Mean   : 11.49  
    ##                                        3rd Qu.: 4.000   3rd Qu.: 16.50  
    ##                                        Max.   :10.000   Max.   :435.00  
    ##                                                                         
    ##      curb            date_planted          longitude         latitude    
    ##  Length:146611      Min.   :1989-10-27   Min.   :-123.2   Min.   :49.20  
    ##  Class :character   1st Qu.:1998-02-23   1st Qu.:-123.1   1st Qu.:49.23  
    ##  Mode  :character   Median :2004-01-28   Median :-123.1   Median :49.25  
    ##                     Mean   :2004-04-07   Mean   :-123.1   Mean   :49.25  
    ##                     3rd Qu.:2010-03-02   3rd Qu.:-123.1   3rd Qu.:49.26  
    ##                     Max.   :2019-07-03   Max.   :-123.0   Max.   :49.29  
    ##                     NA's   :76548        NA's   :22771    NA's   :22771

``` r
#previewing vancouver_trees
head(vancouver_trees)
```

    ## # A tibble: 6 × 20
    ##   tree_id civic_number std_street genus_name species_name cultivar_name  
    ##     <dbl>        <dbl> <chr>      <chr>      <chr>        <chr>          
    ## 1  149556          494 W 58TH AV  ULMUS      AMERICANA    BRANDON        
    ## 2  149563          450 W 58TH AV  ZELKOVA    SERRATA      <NA>           
    ## 3  149579         4994 WINDSOR ST STYRAX     JAPONICA     <NA>           
    ## 4  149590          858 E 39TH AV  FRAXINUS   AMERICANA    AUTUMN APPLAUSE
    ## 5  149604         5032 WINDSOR ST ACER       CAMPESTRE    <NA>           
    ## 6  149616          585 W 61ST AV  PYRUS      CALLERYANA   CHANTICLEER    
    ## # ℹ 14 more variables: common_name <chr>, assigned <chr>, root_barrier <chr>,
    ## #   plant_area <chr>, on_street_block <dbl>, on_street <chr>,
    ## #   neighbourhood_name <chr>, street_side_name <chr>, height_range_id <dbl>,
    ## #   diameter <dbl>, curb <chr>, date_planted <date>, longitude <dbl>,
    ## #   latitude <dbl>

The **steam_games** dataset consists mostly of character objects and 4
columns of numerical data but seems difficult to parse through due to
the length of some character entries. Additionally, there are several
entries missing from `achievement`, `original_price` and
`discount_price`.

``` r
#defining class of each variable in steam_games
summary(steam_games)
```

    ##        id            url               types               name          
    ##  Min.   :    1   Length:40833       Length:40833       Length:40833      
    ##  1st Qu.:10209   Class :character   Class :character   Class :character  
    ##  Median :20417   Mode  :character   Mode  :character   Mode  :character  
    ##  Mean   :20417                                                           
    ##  3rd Qu.:30625                                                           
    ##  Max.   :40833                                                           
    ##                                                                          
    ##  desc_snippet       recent_reviews     all_reviews        release_date      
    ##  Length:40833       Length:40833       Length:40833       Length:40833      
    ##  Class :character   Class :character   Class :character   Class :character  
    ##  Mode  :character   Mode  :character   Mode  :character   Mode  :character  
    ##                                                                             
    ##                                                                             
    ##                                                                             
    ##                                                                             
    ##   developer          publisher         popular_tags       game_details      
    ##  Length:40833       Length:40833       Length:40833       Length:40833      
    ##  Class :character   Class :character   Class :character   Class :character  
    ##  Mode  :character   Mode  :character   Mode  :character   Mode  :character  
    ##                                                                             
    ##                                                                             
    ##                                                                             
    ##                                                                             
    ##   languages          achievements        genre           game_description  
    ##  Length:40833       Min.   :   1.00   Length:40833       Length:40833      
    ##  Class :character   1st Qu.:  12.00   Class :character   Class :character  
    ##  Mode  :character   Median :  21.00   Mode  :character   Mode  :character  
    ##                     Mean   :  77.24                                        
    ##                     3rd Qu.:  38.00                                        
    ##                     Max.   :9821.00                                        
    ##                     NA's   :28639                                          
    ##  mature_content     minimum_requirements recommended_requirements
    ##  Length:40833       Length:40833         Length:40833            
    ##  Class :character   Class :character     Class :character        
    ##  Mode  :character   Mode  :character     Mode  :character        
    ##                                                                  
    ##                                                                  
    ##                                                                  
    ##                                                                  
    ##  original_price     discount_price  
    ##  Min.   :     0.0   Min.   :  0.00  
    ##  1st Qu.:     2.0   1st Qu.:  8.78  
    ##  Median :     5.0   Median : 19.98  
    ##  Mean   :    53.1   Mean   : 46.82  
    ##  3rd Qu.:    10.0   3rd Qu.: 43.92  
    ##  Max.   :730640.0   Max.   :962.60  
    ##  NA's   :5353       NA's   :26290

``` r
#previewing steam_games
head(steam_games)
```

    ## # A tibble: 6 × 21
    ##      id url     types name  desc_snippet recent_reviews all_reviews release_date
    ##   <dbl> <chr>   <chr> <chr> <chr>        <chr>          <chr>       <chr>       
    ## 1     1 https:… app   DOOM  Now include… Very Positive… Very Posit… May 12, 2016
    ## 2     2 https:… app   PLAY… PLAYERUNKNO… Mixed,(6,214)… Mixed,(836… Dec 21, 2017
    ## 3     3 https:… app   BATT… Take comman… Mixed,(166),-… Mostly Pos… Apr 24, 2018
    ## 4     4 https:… app   DayZ  The post-so… Mixed,(932),-… Mixed,(167… Dec 13, 2018
    ## 5     5 https:… app   EVE … EVE Online … Mixed,(287),-… Mostly Pos… May 6, 2003 
    ## 6     6 https:… bund… Gran… Grand Theft… NaN            NaN         NaN         
    ## # ℹ 13 more variables: developer <chr>, publisher <chr>, popular_tags <chr>,
    ## #   game_details <chr>, languages <chr>, achievements <dbl>, genre <chr>,
    ## #   game_description <chr>, mature_content <chr>, minimum_requirements <chr>,
    ## #   recommended_requirements <chr>, original_price <dbl>, discount_price <dbl>

The **parking_meters** dataset only contains 2 columns of numerical
data. While most of the data looks numerical in nature, most columns
also include units and are defined in the character class.

``` r
#exploring classes of each variable
summary(parking_meters)
```

    ##   meter_head         r_mf_9a_6p         r_mf_6p_10         r_sa_9a_6p       
    ##  Length:10032       Length:10032       Length:10032       Length:10032      
    ##  Class :character   Class :character   Class :character   Class :character  
    ##  Mode  :character   Mode  :character   Mode  :character   Mode  :character  
    ##                                                                             
    ##                                                                             
    ##                                                                             
    ##   r_sa_6p_10         r_su_9a_6p         r_su_6p_10         rate_misc        
    ##  Length:10032       Length:10032       Length:10032       Length:10032      
    ##  Class :character   Class :character   Class :character   Class :character  
    ##  Mode  :character   Mode  :character   Mode  :character   Mode  :character  
    ##                                                                             
    ##                                                                             
    ##                                                                             
    ##  time_in_effect      t_mf_9a_6p         t_mf_6p_10         t_sa_9a_6p       
    ##  Length:10032       Length:10032       Length:10032       Length:10032      
    ##  Class :character   Class :character   Class :character   Class :character  
    ##  Mode  :character   Mode  :character   Mode  :character   Mode  :character  
    ##                                                                             
    ##                                                                             
    ##                                                                             
    ##   t_sa_6p_10         t_su_9a_6p         t_su_6p_10         time_misc        
    ##  Length:10032       Length:10032       Length:10032       Length:10032      
    ##  Class :character   Class :character   Class :character   Class :character  
    ##  Mode  :character   Mode  :character   Mode  :character   Mode  :character  
    ##                                                                             
    ##                                                                             
    ##                                                                             
    ##  credit_card         pay_phone           longitude         latitude    
    ##  Length:10032       Length:10032       Min.   :-123.2   Min.   :49.21  
    ##  Class :character   Class :character   1st Qu.:-123.1   1st Qu.:49.26  
    ##  Mode  :character   Mode  :character   Median :-123.1   Median :49.27  
    ##                                        Mean   :-123.1   Mean   :49.27  
    ##                                        3rd Qu.:-123.1   3rd Qu.:49.28  
    ##                                        Max.   :-123.0   Max.   :49.29  
    ##  geo_local_area       meter_id        
    ##  Length:10032       Length:10032      
    ##  Class :character   Class :character  
    ##  Mode  :character   Mode  :character  
    ##                                       
    ##                                       
    ## 

``` r
#previewing parking_meters
head(parking_meters)
```

    ## # A tibble: 6 × 22
    ##   meter_head  r_mf_9a_6p r_mf_6p_10 r_sa_9a_6p r_sa_6p_10 r_su_9a_6p r_su_6p_10
    ##   <chr>       <chr>      <chr>      <chr>      <chr>      <chr>      <chr>     
    ## 1 Twin        $2.00      $4.00      $2.00      $4.00      $2.00      $4.00     
    ## 2 Pay Station $1.00      $1.00      $1.00      $1.00      $1.00      $1.00     
    ## 3 Twin        $1.00      $1.00      $1.00      $1.00      $1.00      $1.00     
    ## 4 Single      $1.00      $1.00      $1.00      $1.00      $1.00      $1.00     
    ## 5 Twin        $2.00      $1.00      $2.00      $1.00      $2.00      $1.00     
    ## 6 Twin        $2.00      $1.00      $2.00      $1.00      $2.00      $1.00     
    ## # ℹ 15 more variables: rate_misc <chr>, time_in_effect <chr>, t_mf_9a_6p <chr>,
    ## #   t_mf_6p_10 <chr>, t_sa_9a_6p <chr>, t_sa_6p_10 <chr>, t_su_9a_6p <chr>,
    ## #   t_su_6p_10 <chr>, time_misc <chr>, credit_card <chr>, pay_phone <chr>,
    ## #   longitude <dbl>, latitude <dbl>, geo_local_area <chr>, meter_id <chr>

<!----------------------------------------------------------------------------->

1.3 **(1 point)** Now that you’ve explored the 4 datasets that you were
initially most interested in, let’s narrow it down to 1. What lead you
to choose this one? Briefly explain your choice below.

<!-------------------------- Start your work below ---------------------------->

## Final Dataset Selection

The dataset I am choosing to analyze is “**cancer_sample**”. Based on my
preliminary exploration of the dataset dimensions, class and
organization, I believe this dataset will be the most straightforward to
wrangle and interpret. The other datasets I considered comprised of (1)
mostly discrete, categorical data, (2) lengthy, qualitative entries or
(3) incomplete entries. These attributes may make relationships between
variables harder to parse.

<!----------------------------------------------------------------------------->

1.4 **(2 points)** Time for a final decision! Going back to the
beginning, it’s important to have an *end goal* in mind. For example, if
I had chosen the `titanic` dataset for my project, I might’ve wanted to
explore the relationship between survival and other variables. Try to
think of 1 research question that you would want to answer with your
dataset. Note it down below.

<!-------------------------- Start your work below ---------------------------->

## Research Question

Is there a relationship between the **diagnosis** (malignant vs. benign)
and **physical attributes of the sample** e.g. radius, texture,
perimeter, area, smoothness, compactness, concavity, symmetry, fractal
dimensionality?

<!----------------------------------------------------------------------------->

# Important note

Read Tasks 2 and 3 *fully* before starting to complete either of them.
Probably also a good point to grab a coffee to get ready for the fun
part!

This project is semi-guided, but meant to be *independent*. For this
reason, you will complete tasks 2 and 3 below (under the **START HERE**
mark) as if you were writing your own exploratory data analysis report,
and this guidance never existed! Feel free to add a brief introduction
section to your project, format the document with markdown syntax as you
deem appropriate, and structure the analysis as you deem appropriate. If
you feel lost, you can find a sample data analysis
[here](https://www.kaggle.com/headsortails/tidy-titarnic) to have a
better idea. However, bear in mind that it is **just an example** and
you will not be required to have that level of complexity in your
project.

# Task 2: Exploring your dataset

If we rewind and go back to the learning objectives, you’ll see that by
the end of this deliverable, you should have formulated *4* research
questions about your data that you may want to answer during your
project. However, it may be handy to do some more exploration on your
dataset of choice before creating these questions - by looking at the
data, you may get more ideas. **Before you start this task, read all
instructions carefully until you reach START HERE under Task 3**.

2.1 **(12 points)** Complete *4 out of the following 8 exercises* to
dive deeper into your data. All datasets are different and therefore,
not all of these tasks may make sense for your data - which is why you
should only answer *4*.

Make sure that you’re using dplyr and ggplot2 rather than base R for
this task. Outside of this project, you may find that you prefer using
base R functions for certain tasks, and that’s just fine! But part of
this project is for you to practice the tools we learned in class, which
is dplyr and ggplot2.

1.  Plot the distribution of a numeric variable.
2.  Create a new variable based on other variables in your data (only if
    it makes sense)
3.  Investigate how many missing values there are per variable. Can you
    find a way to plot this?
4.  Explore the relationship between 2 variables in a plot.
5.  Filter observations in your data according to your own criteria.
    Think of what you’d like to explore - again, if this was the
    `titanic` dataset, I may want to narrow my search down to passengers
    born in a particular year…
6.  Use a boxplot to look at the frequency of different observations
    within a single variable. You can do this for more than one variable
    if you wish!
7.  Make a new tibble with a subset of your data, with variables and
    observations that you are interested in exploring.
8.  Use a density plot to explore any of your variables (that are
    suitable for this type of plot).

2.2 **(4 points)** For each of the 4 exercises that you complete,
provide a *brief explanation* of why you chose that exercise in relation
to your data (in other words, why does it make sense to do that?), and
sufficient comments for a reader to understand your reasoning and code.

<!-------------------------- Start your work below ---------------------------->

## Exercise 4

*Explore the relationship between 2 variables in a plot.*

#### Purpose

To explore the data, I decided to plot the distribution of each variable
and group by diagnosis. This visually can summarize which attributes may
differ between benign vs. malignant samples.

``` r
#Storing dot plot of radius_mean vs diagnosis
radius_plot <- ggplot(data = cancer_sample,
                      aes(x = diagnosis, 
                          y = radius_mean)) + 
  geom_jitter(aes(colour = diagnosis),
              width = 0.2, 
              alpha = 0.2,
              size = 0.75) +
  labs(x = "Diagnosis", y = "Radius") +
  theme(legend.position = "none")

#Storing dot plot of texture_mean vs diagnosis
texture_plot <- ggplot(data = cancer_sample,
                      aes(x = diagnosis, 
                          y = texture_mean)) + 
  geom_jitter(aes(colour = diagnosis),
              width = 0.2, 
              alpha = 0.2,
              size = 0.75) + 
    labs(x = "Diagnosis", y = "Texture") +
    theme(legend.position = "none")

#Storing dot plot of perimeter_mean vs diagnosis
perimeter_plot <- ggplot(data = cancer_sample,
                      aes(x = diagnosis, 
                          y = perimeter_mean)) + 
  geom_jitter(aes(colour = diagnosis),
              width = 0.2, 
              alpha = 0.2,
              size = 0.75) +
  labs(x = "Diagnosis", y = "Perimeter") +
  theme(legend.position = "none")

#Storing dot plot of area_mean vs diagnosis
area_plot <- ggplot(data = cancer_sample,
                      aes(x = diagnosis, 
                          y = area_mean)) + 
  geom_jitter(aes(colour = diagnosis),
              width = 0.2, 
              alpha = 0.2, 
              size = 0.75) +
  labs(x = "Diagnosis", y = "Area") +
  theme(legend.position = "none")

#Storing dot plot of smoothness_mean vs diagnosis
smoothness_plot <- ggplot(data = cancer_sample,
                      aes(x = diagnosis, 
                          y = smoothness_mean)) + 
  geom_jitter(aes(colour = diagnosis),
              width = 0.2, 
              alpha = 0.2, 
              size = 0.75) +
  labs(x = "Diagnosis", y = "Smoothness") +
  theme(legend.position = "none")

#Storing dot plot of compactness_mean vs diagnosis
compactness_plot <- ggplot(data = cancer_sample,
                      aes(x = diagnosis, 
                          y = compactness_mean)) + 
  geom_jitter(aes(colour = diagnosis),
              width = 0.2, 
              alpha = 0.2,
              size = 0.75) +
  labs(x = "Diagnosis", y = "Compactness") +
  theme(legend.position = "none")

#Storing dot plot of concavity_mean vs diagnosis
concavity_plot <- ggplot(data = cancer_sample,
                      aes(x = diagnosis, 
                          y = concavity_mean)) + 
  geom_jitter(aes(colour = diagnosis),
              width = 0.2, 
              alpha = 0.2, 
              size = 0.75) +
  labs(x = "Diagnosis", y = "Concavity") +
  theme(legend.position = "none")

#Storing dot plot of concave_points_mean vs diagnosis
concave_points_plot <- ggplot(data = cancer_sample,
                      aes(x = diagnosis, 
                          y = concave_points_mean)) + 
  geom_jitter(aes(colour = diagnosis),
              width = 0.2, 
              alpha = 0.2, 
              size = 0.75) +
  labs(x = "Diagnosis", y = "Concave Points") +
  theme(legend.position = "none")

#Storing dot plot of symmetry_mean vs diagnosis
symmetry_plot <- ggplot(data = cancer_sample,
                      aes(x = diagnosis, 
                          y = symmetry_mean)) + 
  geom_jitter(aes(colour = diagnosis),
              width = 0.2, 
              alpha = 0.2, 
              size = 0.75) +
  labs(x = "Diagnosis", y = "Symmetry") +
  theme(legend.position = "none")

#Storing dot plot of fractal_dimension_mean vs diagnosis
fractal_dim_plot <- ggplot(data = cancer_sample,
                      aes(x = diagnosis,
                          y = fractal_dimension_mean)) +
  geom_jitter(aes(colour = diagnosis),
              width = 0.2,
              alpha = 0.2, 
              size = 0.75) +
  labs(x = "Diagnosis", y = "Fractal Dimension") +
  theme(legend.position = "none")

#Arranging the stored dot plots into an array 
ggarrange(radius_plot, texture_plot, perimeter_plot, area_plot, #plots in first row
         smoothness_plot, compactness_plot, concavity_plot, concave_points_plot, #plots in second row
         symmetry_plot, fractal_dim_plot) #plots in third row
```

![](mini-project-1_files/figure-gfm/unnamed-chunk-18-1.png)<!-- -->

#### Conclusion

At a glance, `radius_mean`, `texture_mean`, `perimeter_mean` and
`area_mean` exhibit the strongest differential between diagnoses, with
higher values in malignant samples. Other variables such as
`compactness_mean`, `concavity_mean` and `concave_points_mean`
illustrate a similar relationship with diagnosis, however exhibit larger
spread of data.

## Exercise 2

*Create a new variable based on other variables in your data.*

#### Purpose

Due to the spread of data, some variables are harder to discern if there
is a clear difference based on diagnosis. For this reason, I created a
new tibble that summarizes the **average** numerical value of **each
variable**, grouped by diagnosis.

``` r
#Create new tibble summarizing means of each variable
cancer_sample %>%
  group_by(diagnosis) %>%
  summarize(avg_radius = mean(radius_mean),
            avg_texture = mean(texture_mean),
            avg_perimeter = mean(perimeter_mean),
            avg_area = mean(area_mean), 
            avg_smoothness = mean(smoothness_mean), 
            avg_compactness = mean(compactness_mean), 
            avg_concavity = mean(concavity_mean), 
            avg_concave_points = mean(concave_points_mean), 
            avg_symmetry = mean(symmetry_mean), 
            avg_fractal_dimension = mean(fractal_dimension_mean))
```

    ## # A tibble: 2 × 11
    ##   diagnosis avg_radius avg_texture avg_perimeter avg_area avg_smoothness
    ##   <chr>          <dbl>       <dbl>         <dbl>    <dbl>          <dbl>
    ## 1 B               12.1        17.9          78.1     463.         0.0925
    ## 2 M               17.5        21.6         115.      978.         0.103 
    ## # ℹ 5 more variables: avg_compactness <dbl>, avg_concavity <dbl>,
    ## #   avg_concave_points <dbl>, avg_symmetry <dbl>, avg_fractal_dimension <dbl>

#### Conclusion

The average value is higher for malignant samples in all variables
except `fractal_dimension_mean`.

## Exercise 6

*Use a boxplot to look at the frequency of different observations within
a single variable.*

#### Purpose

To visualize the above table better, I generated boxplot graphs to
summarize the difference of means based on diagnosis.

``` r
#Storing boxplot of radius_mean vs diagnosis
radius_plot <- ggplot(data = cancer_sample,
                      aes(radius_mean, diagnosis)) + 
  geom_boxplot(aes(group = diagnosis,
                   fill = diagnosis),
                   outlier.size = 0.5,
                   width = 0.5) +
  labs(x = "Radius", y = "Diagnosis") +
  theme(legend.position = "none")

#Storing boxplot of texture_mean vs diagnosis
texture_plot <- ggplot(data = cancer_sample,
                      aes(texture_mean, diagnosis)) + 
  geom_boxplot(aes(group = diagnosis,
                   fill = diagnosis),
                   outlier.size = 0.5,
                   width = 0.5) +
  labs(x = "Texture", y = "Diagnosis") +
  theme(legend.position = "none")

#Storing boxplot of perimeter_mean vs diagnosis
perimeter_plot <- ggplot(data = cancer_sample,
                      aes(perimeter_mean, diagnosis)) + 
  geom_boxplot(aes(group = diagnosis,
                   fill = diagnosis),
                   outlier.size = 0.5,
                   width = 0.5) +
  labs(x = "Perimeter", y = "Diagnosis") +
  theme(legend.position = "none")

#Storing boxplot of area_mean vs diagnosis
area_plot <- ggplot(data = cancer_sample,
                      aes(area_mean, diagnosis)) + 
  geom_boxplot(aes(group = diagnosis,
                   fill = diagnosis),
                   outlier.size = 0.5,
                   width = 0.5) +
  labs(x = "Area", y = "Diagnosis") +
  theme(legend.position = "none")

#Storing boxplot of smoothness_mean vs diagnosis
smoothness_plot <- ggplot(data = cancer_sample,
                      aes(smoothness_mean, diagnosis)) + 
  geom_boxplot(aes(group = diagnosis,
                   fill = diagnosis),
                   outlier.size = 0.5,
                   width = 0.5) +
  labs(x = "Smoothness", y = "Diagnosis") +
  theme(legend.position = "none")

#Storing boxplot of compactness_mean vs diagnosis
compactness_plot <- ggplot(data = cancer_sample,
                      aes(compactness_mean, diagnosis)) + 
  geom_boxplot(aes(group = diagnosis,
                   fill = diagnosis),
                   outlier.size = 0.5,
                   width = 0.5) +
  labs(x = "Compactness", y = "Diagnosis") +
  theme(legend.position = "none")

#Storing boxplot of concavity_mean vs diagnosis
concavity_plot <- ggplot(data = cancer_sample,
                      aes(concavity_mean, diagnosis)) + 
  geom_boxplot(aes(group = diagnosis,
                   fill = diagnosis),
                   outlier.size = 0.5,
                   width = 0.5) +
  labs(x = "Concavity", y = "Diagnosis") +
  theme(legend.position = "none")

#Storing boxplot of concave_points_mean vs diagnosis
concave_points_plot <- ggplot(data = cancer_sample,
                      aes(concave_points_mean, diagnosis)) + 
  geom_boxplot(aes(group = diagnosis,
                   fill = diagnosis),
                   outlier.size = 0.5,
                   width = 0.5) +
  labs(x = "Concave Points", y = "Diagnosis") +
  theme(legend.position = "none")

#Storing boxplot of symmetry_mean vs diagnosis
symmetry_plot <- ggplot(data = cancer_sample,
                      aes(symmetry_mean, diagnosis)) + 
  geom_boxplot(aes(group = diagnosis,
                   fill = diagnosis),
                   outlier.size = 0.5,
                   width = 0.5) +
  labs(x = "Symmetry", y = "Diagnosis") +
  theme(legend.position = "none")

#Storing boxplot of fractal_dimension_mean vs diagnosis
fractal_dim_plot <- ggplot(data = cancer_sample,
                      aes(fractal_dimension_mean, diagnosis)) + 
  geom_boxplot(aes(group = diagnosis,
                   fill = diagnosis),
                   outlier.size = 0.5,
                   width = 0.5) +
  labs(x = "Fractal Dimension", y = "Diagnosis") +
  theme(legend.position = "none")

#Arranging the stored boxplots into an array
ggarrange(radius_plot, texture_plot, perimeter_plot, #plots in first row 
          area_plot, smoothness_plot, compactness_plot, #plots in second row
          concavity_plot, concave_points_plot, symmetry_plot, #plots in third row
          fractal_dim_plot, #plots in fourth row
          common.legend = TRUE, legend = "bottom") 
```

![](mini-project-1_files/figure-gfm/unnamed-chunk-20-1.png)<!-- -->

#### Conclusion

The variables with the most discrete ranges of data are `radius_mean`,
`texture_mean`, `perimeter_mean`, `area_mean`, `compactness_mean`,
`concavity_mean` and `concave_points_mean`. The averages and bulk of
data are numerically similar between diagnoses for `smoothness_mean`,
`symmetry_mean` and `fractal_dimension_mean`.

## Exercise 8

*Use a density plot to explore any of your variables.*

#### Purpose

Additionally, I generated density plots to better represent the spread
of data. **Note** that while the dot plots generated above (Exercise 4)
also illustrates the spread of data, the overlapping of points obscures
the density of data points near the mean. The dot plot more clearly
conveys the value and quantity of outliers, while the density plot will
better illustrate the exact values the bulk of data lies within.

``` r
#Storing density plot of radius_mean for each diagnosis
radius_plot <- ggplot(data = cancer_sample,
                      aes(radius_mean)) + 
  geom_density(aes(group = diagnosis,
                   fill = diagnosis),
              alpha = 0.5) +
  labs(x = "Radius", y = "Density") +
  theme(legend.position = "none")

#Storing density plot of texture_mean for each diagnosis
texture_plot <- ggplot(data = cancer_sample,
                      aes(texture_mean)) + 
  geom_density(aes(group = diagnosis,
                   fill = diagnosis),
              alpha = 0.5) +
  labs(x = "Texture", y = "Density") +
  theme(legend.position = "none")

#Storing density plot of perimeter_mean for each diagnosis
perimeter_plot <- ggplot(data = cancer_sample,
                      aes(perimeter_mean)) + 
  geom_density(aes(group = diagnosis,
                   fill = diagnosis),
              alpha = 0.5) +
  labs(x = "Perimeter", y = "Density") +
  theme(legend.position = "none")

#Storing density plot of area_mean for each diagnosis
area_plot <- ggplot(data = cancer_sample,
                      aes(area_mean)) + 
  geom_density(aes(group = diagnosis,
                   fill = diagnosis),
              alpha = 0.5) +
  labs(x = "Area", y = "Density") +
  theme(legend.position = "none")

#Storing density plot of smoothness_mean for each diagnosis
smoothness_plot <- ggplot(data = cancer_sample,
                      aes(smoothness_mean)) + 
  geom_density(aes(group = diagnosis,
                   fill = diagnosis),
              alpha = 0.5) +
  labs(x = "Smoothness", y = "Density") +
  theme(legend.position = "none")

#Storing density plot of compactness_mean for each diagnosis
compactness_plot <- ggplot(data = cancer_sample,
                      aes(smoothness_mean)) + 
  geom_density(aes(group = diagnosis,
                   fill = diagnosis),
              alpha = 0.5) +
  labs(x = "Compactness", y = "Density") +
  theme(legend.position = "none")

#Storing density plot of concavity_mean for each diagnosis
concavity_plot <- ggplot(data = cancer_sample,
                      aes(concavity_mean)) + 
  geom_density(aes(group = diagnosis,
                   fill = diagnosis),
              alpha = 0.5) +
  labs(x = "Concavity", y = "Density") +
  theme(legend.position = "none")

#Storing density plot of concave_points_mean for each diagnosis
concave_points_plot <- ggplot(data = cancer_sample,
                      aes(concave_points_mean)) + 
  geom_density(aes(group = diagnosis,
                   fill = diagnosis),
              alpha = 0.5) +
  labs(x = "Concave Points", y = "Density") +
  theme(legend.position = "none")

#Storing density plot of symmetry_mean for each diagnosis
symmetry_plot <- ggplot(data = cancer_sample,
                      aes(symmetry_mean)) + 
  geom_density(aes(group = diagnosis,
                   fill = diagnosis),
              alpha = 0.5) +
  labs(x = "Symmetry", y = "Density") +
  theme(legend.position = "none")

#Storing density plot of fractal_dimension_mean for each diagnosis
fractal_dim_plot <- ggplot(data = cancer_sample,
                      aes(fractal_dimension_mean)) + 
  geom_density(aes(group = diagnosis,
                   fill = diagnosis),
               alpha = 0.5) +
  labs(x = "Fractal Dimension", y = "Density") +
   theme(legend.position = "none")

#Arranging the stored density plots into an array
ggarrange(radius_plot, texture_plot, perimeter_plot, #plots in first row
          area_plot, smoothness_plot, compactness_plot, #plots in second row
          concavity_plot, concave_points_plot, symmetry_plot, #plots in third row
          fractal_dim_plot, #plot in fourth row
          nrow = 4, ncol = 3,
          common.legend = TRUE, legend = "bottom")
```

![](mini-project-1_files/figure-gfm/unnamed-chunk-21-1.png)<!-- -->

#### Conclusion

Benign samples exhibit a relatively tight spread of data for all
variables, while malignant samples have a much larger range of data for
`radius_mean`, `perimeter_mean`, `area_mean`, `concavity_mean` and
`concave_points_mean`.

### Summary

- Computed averages in **Exercise 2** suggest that all variables but
  `fractal_dimension_mean` may have a relationship with the diagnosis,
  where higher values are associated with malignant samples.
- **Exercise 4** illustrated the spread of data and supported stronger
  correlations between high `radius_mean`, `texture_mean`,
  `perimeter_mean` and `area_mean` values with malignant diagnosis.
- When visualized as boxplots in **Exercise 6**, `radius_mean`,
  `texture_mean`, `perimeter_mean`, `area_mean`, `compactness_mean`,
  `concavity_mean` and `concave_points_mean` presented the most discrete
  data ranges between malignant and benign samples.
- Illustrating the spread of data in **Exercise 8** revealed very large
  spreads of data in malignant samples for `radius_mean`,
  `perimeter_mean`, `area_mean`, `concavity_mean` and
  `concave_points_mean`.
- With all four exercises considered, `texture_mean` and
  `compactness_mean` appear to correlate high values with malignancy
  within tighter spreads of data. However, `radius_mean`,
  `perimeter_mean`, `area_mean`, `concavity_mean` and
  `concave_points_mean` also correlate high values with malignancy and
  exhibit a smaller numerical range of overlap between diagnoses.

<!----------------------------------------------------------------------------->

# Task 3: Choose research questions

**(4 points)** So far, you have chosen a dataset and gotten familiar
with it through exploring the data. You have also brainstormed one
research question that interested you (Task 1.4). Now it’s time to pick
4 research questions that you would like to explore in Milestone 2!
Write the 4 questions and any additional comments below.

<!--- *****START HERE***** --->

## Further Research Questions

In Task 2, I investigated the relationship between the **physical
attributes** of cancer samples and **diagnosis**, within the dataset
`cancer_samples`. In Task 3, I would like to explore these relationships
further, evaluate their strength and determine the level of confidence
they can predict malignancy.

1.  Which physical attribute is the strongest indicator of diagnosis?  
2.  Is there a numerical range of this attribute that can define a
    benign vs. malignant tumor?  
3.  Do samples with large margins of error (SE value) still align with
    the above ranges of benign vs. malignant?  
4.  For discrete ranges of this attribute, what is the likelihood that
    the sample is benign vs. malignant?

<!----------------------------->

# Overall reproducibility/Cleanliness/Coherence Checklist

## Coherence (0.5 points)

The document should read sensibly from top to bottom, with no major
continuity errors. An example of a major continuity error is having a
data set listed for Task 3 that is not part of one of the data sets
listed in Task 1.

## Error-free code (3 points)

For full marks, all code in the document should run without error. 1
point deduction if most code runs without error, and 2 points deduction
if more than 50% of the code throws an error.

## Main README (1 point)

There should be a file named `README.md` at the top level of your
repository. Its contents should automatically appear when you visit the
repository on GitHub.

Minimum contents of the README file:

- In a sentence or two, explains what this repository is, so that
  future-you or someone else stumbling on your repository can be
  oriented to the repository.
- In a sentence or two (or more??), briefly explains how to engage with
  the repository. You can assume the person reading knows the material
  from STAT 545A. Basically, if a visitor to your repository wants to
  explore your project, what should they know?

Once you get in the habit of making README files, and seeing more README
files in other projects, you’ll wonder how you ever got by without them!
They are tremendously helpful.

## Output (1 point)

All output is readable, recent and relevant:

- All Rmd files have been `knit`ted to their output md files.
- All knitted md files are viewable without errors on Github. Examples
  of errors: Missing plots, “Sorry about that, but we can’t show files
  that are this big right now” messages, error messages from broken R
  code
- All of these output files are up-to-date – that is, they haven’t
  fallen behind after the source (Rmd) files have been updated.
- There should be no relic output files. For example, if you were
  knitting an Rmd to html, but then changed the output to be only a
  markdown file, then the html file is a relic and should be deleted.

(0.5 point deduction if any of the above criteria are not met. 1 point
deduction if most or all of the above criteria are not met.)

Our recommendation: right before submission, delete all output files,
and re-knit each milestone’s Rmd file, so that everything is up to date
and relevant. Then, after your final commit and push to Github, CHECK on
Github to make sure that everything looks the way you intended!

## Tagged release (0.5 points)

You’ve tagged a release for Milestone 1.

### Attribution

Thanks to Icíar Fernández Boyano for mostly putting this together, and
Vincenzo Coia for launching.
