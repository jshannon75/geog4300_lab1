Geog4/6300: Lab 1
================

## Loading data into R, data transformation, and summary statistics

**Due:** Monday, Sept. 18

**Value:** 30 points

**Overview:**

This lab is intended to assess your ability to use R to load data and to
generate basic descriptive statistics. You’ll be using monthly weather
data from the Daymet climate database (<http://daymet.ornl.gov>) for all
counties in the United States over a 10 year period (2005-2015). These
data are available on the Github repo for our course. The following
variables are provided:

  - gisjn\_cty: Code for joining to census data
  - year: Year of observation
  - month: Month of observation
  - dayl: Mean length of daylight (in seconds)
  - srad: Mean solar radiation per day
  - tmax: Mean maximum recorded temperature (Celsius)
  - tmin: Mean minimum recorded temperature (Celsius)
  - vap\_pres: Mean vapor pressure (indicative of humidity)
  - prcp: Total recorded prcpitation (mm)
  - cty\_name: Name of the county
  - state: state of the county
  - region: Census region (map:
    <https://www2.census.gov/geo/pdfs/maps-data/maps/reference/us_regdiv.pdf>)
  - division: Census division
  - lon: Longitude of the point
  - lat: Latitude of the point

These labs are meant to be done collaboratively, but your final
submission should demonstrate your own original thought (don’t just copy
your classmate’s work or turn in identical assignments). Your answers to
the lab questions should be typed in the provided RMarkdown template.
You’ll then “knit” this to an HTML document and upload it to your class
Github repo.

**Procedure:**

Load the tidyverse package and import the data:

``` r
library(tidyverse)
daymet_cty_2005_2015 <- read_csv("data/Daymet_Cty_Summary_2005_2015.csv")
```

    ## Parsed with column specification:
    ## cols(
    ##   gisjn_cty = col_character(),
    ##   year = col_double(),
    ##   month = col_character(),
    ##   dayl = col_double(),
    ##   srad = col_double(),
    ##   tmax = col_double(),
    ##   tmin = col_double(),
    ##   vap_pres = col_double(),
    ##   prcp = col_double(),
    ##   CTY_NAME = col_character(),
    ##   State = col_character(),
    ##   Region = col_character(),
    ##   Division = col_character(),
    ##   Lon = col_double(),
    ##   Lat = col_double()
    ## )

We can look at the first few rows of the dataset using the *head*
function. We also use *kable* to format this
nicely.

``` r
kable(head(daymet_cty_2005_2015))
```

| gisjn\_cty | year | month |     dayl |     srad |     tmax |       tmin | vap\_pres | prcp | CTY\_NAME | State   | Region       | Division                    |        Lon |    Lat |
| :--------- | ---: | :---- | -------: | -------: | -------: | ---------: | --------: | ---: | :-------- | :------ | :----------- | :-------------------------- | ---------: | -----: |
| G01001     | 2005 | Apr   | 46137.60 | 420.6933 | 23.13333 |  9.4666667 | 1210.6667 |  195 | Autauga   | Alabama | South Region | East South Central Division | \-86.64257 | 32.535 |
| G01001     | 2005 | Aug   | 47380.65 | 364.3871 | 31.58065 | 22.0322581 | 2649.0323 |  150 | Autauga   | Alabama | South Region | East South Central Division | \-86.64257 | 32.535 |
| G01001     | 2005 | Dec   | 35663.77 | 258.5806 | 13.33871 |  0.1774194 |  637.4194 |   69 | Autauga   | Alabama | South Region | East South Central Division | \-86.64257 | 32.535 |
| G01001     | 2005 | Feb   | 39028.11 | 297.2571 | 16.60714 |  5.4107143 |  935.7143 |  152 | Autauga   | Alabama | South Region | East South Central Division | \-86.64257 | 32.535 |
| G01001     | 2005 | Jan   | 36444.06 | 261.5742 | 15.75806 |  3.5483871 |  855.4839 |   75 | Autauga   | Alabama | South Region | East South Central Division | \-86.64257 | 32.535 |
| G01001     | 2005 | July  | 50045.13 | 350.2452 | 31.37097 | 22.0483871 | 2649.0323 |  284 | Autauga   | Alabama | South Region | East South Central Division | \-86.64257 | 32.535 |

***Question 1 (4 points):** After loading the file into R, pick TWO
variables and classify them as nominal, ordinal, interval, and ratio
data. Justify the classification you chose in a sentence or two for each
one.*

There are a lot of observations here, 413,820 to be exact. To get a
better grasp on it, we can use group\_by and summarise in the tidyverse
package, which we covered in class. This will allow us to identify the
mean value for each year by county across the study period.

***Question 2 (4 points):** Use group\_by and summarise to calculate the
mean minimum temperature and mean precipitation for each year by county,
also including State and Region as grouping variables. Your resulting
dataset should show the value of tmin for each county in each year. Use
the kable and head functions as shown above to call the resulting
table.*

***Question 3 (2 points):** What if we were only interested in the South
Region? Filter the data frame you created in question 2 to just include
counties in this region. Then use group\_by and summarise again to
calculate the mean minimum temperature by year for each state. For 1
point extra credit, use the round function to include only 1 decimal
point. Use kable and head to call the first few lines of the resulting
table*

***Question 4 (3 points):** To visualize the trends, we could use ggplot
to visualize change in mean temperature over time. Create a line plot
(geom\_line) showing the state means you calculated in question 3. Use
the color parameter to show separate colors for each state.*

***Question 5 (3 points):** If you wanted to look at these data as a
table, you’d need to have it in wide format. Use the spread function to
create a wide format version of the data frame you created in question
3. Then call the whole table using kable.*

***Question 6 (4 points):** Returning to the county table you created in
question 2, filter the data to only include 2015 as a year. Then use
ggplot to create a scatterplot (geom\_point) for the minimum temperature
and precipitation variables, coloring the points using the Region
variable.*
