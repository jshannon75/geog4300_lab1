Lab 1: Your responses
================

Your name: Jerry Shannon

In the spaces below, insert your code and/or explanation as notes. Look for the angle brackets-{like these}-for where a response is needed.

When you are done, click on the arrow next to "knit" and choose "Knit to HTML

Load the data and the tidyverse package in the code chunk below

``` r
daymet_cty_2005_2015 <- read_csv("https://github.com/jshannon75/geog4300/raw/master/labs/lab1_%20descriptive_stats/Daymet_Cty_Summary_2005_2015.csv")
```

    ## Parsed with column specification:
    ## cols(
    ##   gisjn_cty = col_character(),
    ##   year = col_integer(),
    ##   month = col_character(),
    ##   dayl = col_double(),
    ##   srad = col_double(),
    ##   tmax = col_double(),
    ##   tmin = col_double(),
    ##   vap_pres = col_double(),
    ##   prcp = col_integer(),
    ##   CTY_NAME = col_character(),
    ##   State = col_character(),
    ##   Region = col_character(),
    ##   Division = col_character(),
    ##   Lon = col_double(),
    ##   Lat = col_double()
    ## )

**Question 1 (4 points):** Provide an example of nominal, ordinal, interval, and ratio data within this dataset. Explain why each fits in the level of measurement you chose in a sentence or two . If you cannot find an example for one of these four data types (no nominal variables, for example), given an example of climate data that would fit this type.\*

{Your response goes here}

**Question 2 task (4 points):** Let's make a very basic climate change model. Create a new variable (tmax\_new), that adds two degrees Celsius to the existing maximum temperature for each county. Calculate the mean and standard deviation for the original maximum temperature variable and a new one two degrees higher, grouping these by each census region as shown above. How do these compare? Explain any similarities or differences you find.\*

``` r
#Calculate the mean and sd here
```

{Your explanation of the results}

**Question 3 task (4 points):** Adapting the script above, create a data frame that shows the mean, median, standard deviation, CV, and IQR for the ***prcp*** variable. Based on these data, are these data skewed or roughly normal in distribution? Which measures of central tendency and dispersion should you use as a result?\*

``` r
#Code for creating and displaying the data frame
```

{Your explanation of the results}

***Question 4 task (3 points):** Explain the code you used to calculate statistics for question 3 in plain English. What is happening in each function?*

{Your explanation of the code}

***Question 4 (3 points):** Adapt the above command to create a new data frame, changing “July” to a month of your choosing and using tmin (rather than tmax) as your variable of interest. You should also be sure to keep the region and year variables for use in question 5. You'll need two commands--one to create the data frame and another to "call" it, just like you see above.*

**Question 5 task (3 points):** Create a box plot similar to the one above for the **tmin** variable. Identify two notable patterns evident in this plot.

``` r
#Code for creating the box plot
```

**Question 6 task (2 points):** Adapt the above command to create a new data frame, changing "Mar" to a month of your choosing and using **tmin** (rather than tmax) as your variable of interest. You'll need two commands--one to create the data frame and another to "call" it, just like you see above.\*

``` r
#Code for creating the new data frame for a single month
```

\***Question 7 task (3 points):** Create a line plot similar to the one above for the **tmin** variable in the month you have chosen.

``` r
#Code for creating the line plot
```

***Question 8 task (3 points):** Create a density plot similar to the one above for the **tmin** variable in the month you have chosen.*

``` r
#Code for creating the density plot
```

***Question 9 task (4 points):** Explain in your own words what the line and density plots you created tell us about the data. How are they different from one another? In what ways, if any, do they tell similar stories?*

{Your response goes here}
