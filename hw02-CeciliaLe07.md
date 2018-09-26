Explore Gapminder and use dplyr
================

<!-- Loading the packages we will need -->
Smell test the data
===================

We can use the command `str()` to answer the following questions:

``` r
str(gapminder)
```

    ## Classes 'tbl_df', 'tbl' and 'data.frame':    1704 obs. of  6 variables:
    ##  $ country  : Factor w/ 142 levels "Afghanistan",..: 1 1 1 1 1 1 1 1 1 1 ...
    ##  $ continent: Factor w/ 5 levels "Africa","Americas",..: 3 3 3 3 3 3 3 3 3 3 ...
    ##  $ year     : int  1952 1957 1962 1967 1972 1977 1982 1987 1992 1997 ...
    ##  $ lifeExp  : num  28.8 30.3 32 34 36.1 ...
    ##  $ pop      : int  8425333 9240934 10267083 11537966 13079460 14880372 12881816 13867957 16317921 22227415 ...
    ##  $ gdpPercap: num  779 821 853 836 740 ...

-   Is it a data.frame, a matrix, a vector, a list?
    -   Gapminder is a special kind of **data.frame** called tibble
-   What is its class?
    -   Gapminder has the following classes: **tbl\_df**, **tbl** and **data.frame**
-   How many variables/columns?
    -   It has **6 variables**
-   How many rows/observations?
    -   It has **1704 observations**
-   Can you get these facts about “extent” or “size” in more than one way?
    -   **yes**, there are different commands like `class`, `atributtes`, `nrow` and `ncol`. For example:

``` r
#This command returns the classes of object gapminder
class(gapminder)
```

    ## [1] "tbl_df"     "tbl"        "data.frame"

The command `attributes` returns the column's names, classes and row names of gapminder

``` r
#These are the name of columns
attributes(gapminder)$names
```

    ## [1] "country"   "continent" "year"      "lifeExp"   "pop"       "gdpPercap"

``` r
#These are the classes
attributes(gapminder)$class
```

    ## [1] "tbl_df"     "tbl"        "data.frame"

``` r
#These firts six row names of gapminder
head(attributes(gapminder)$row.names)
```

    ## [1] 1 2 3 4 5 6

``` r
#This command returns the number of rows of the data frame
nrow(gapminder)
```

    ## [1] 1704

``` r
#This command returns the number of columns of the data frame
ncol(gapminder)    
```

    ## [1] 6

-   What data type is each variable?

Type of each variable is expresed on the following table:

| Variable  | Type    |
|-----------|---------|
| country   | Factor  |
| continent | Factor  |
| year      | Integer |
| lifeExp   | Numeric |
| pop       | Integer |
| dgpPercap | Numeric |

Explore individual variables
============================

Pick at least one categorical variable and at least one quantitative variable to explore.

-   What are possible values (or range, whichever is appropriate) of each variable?
-   What values are typical? What’s the spread? What’s the distribution? Etc., tailored to the variable at hand.
-   Feel free to use summary stats, tables, figures. We’re NOT expecting high production value (yet).

### Continent

Let's explore the variable *continent* which is a categorical variable, so in order to know its levels and corresponding counts we can produce a barplot:

![](hw02-CeciliaLe07_files/figure-markdown_github/unnamed-chunk-7-1.png)

This graph allows us to know this variable has 5 leves: Africa, Americas, Asia, Europe and Oceania. Africa is the category with the maximum number of observations, which is equal to 624; Oceania is the continent with the minimum number of observations, which is equal to 24.

### Country

Regarding the **country** variable, we can visualize the number of observations of each country by the following table:

<table class="table table-striped" style>
<thead>
<tr>
<th style="text-align:left;">
Country
</th>
<th style="text-align:right;">
Observations
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left;">
Afghanistan
</td>
<td style="text-align:right;">
12
</td>
</tr>
<tr>
<td style="text-align:left;">
Albania
</td>
<td style="text-align:right;">
12
</td>
</tr>
<tr>
<td style="text-align:left;">
Algeria
</td>
<td style="text-align:right;">
12
</td>
</tr>
<tr>
<td style="text-align:left;">
Angola
</td>
<td style="text-align:right;">
12
</td>
</tr>
<tr>
<td style="text-align:left;">
Argentina
</td>
<td style="text-align:right;">
12
</td>
</tr>
<tr>
<td style="text-align:left;">
Australia
</td>
<td style="text-align:right;">
12
</td>
</tr>
<tr>
<td style="text-align:left;">
Austria
</td>
<td style="text-align:right;">
12
</td>
</tr>
<tr>
<td style="text-align:left;">
Bahrain
</td>
<td style="text-align:right;">
12
</td>
</tr>
<tr>
<td style="text-align:left;">
Bangladesh
</td>
<td style="text-align:right;">
12
</td>
</tr>
<tr>
<td style="text-align:left;">
Belgium
</td>
<td style="text-align:right;">
12
</td>
</tr>
<tr>
<td style="text-align:left;">
Benin
</td>
<td style="text-align:right;">
12
</td>
</tr>
<tr>
<td style="text-align:left;">
Bolivia
</td>
<td style="text-align:right;">
12
</td>
</tr>
<tr>
<td style="text-align:left;">
Bosnia and Herzegovina
</td>
<td style="text-align:right;">
12
</td>
</tr>
<tr>
<td style="text-align:left;">
Botswana
</td>
<td style="text-align:right;">
12
</td>
</tr>
<tr>
<td style="text-align:left;">
Brazil
</td>
<td style="text-align:right;">
12
</td>
</tr>
<tr>
<td style="text-align:left;">
Bulgaria
</td>
<td style="text-align:right;">
12
</td>
</tr>
<tr>
<td style="text-align:left;">
Burkina Faso
</td>
<td style="text-align:right;">
12
</td>
</tr>
<tr>
<td style="text-align:left;">
Burundi
</td>
<td style="text-align:right;">
12
</td>
</tr>
<tr>
<td style="text-align:left;">
Cambodia
</td>
<td style="text-align:right;">
12
</td>
</tr>
<tr>
<td style="text-align:left;">
Cameroon
</td>
<td style="text-align:right;">
12
</td>
</tr>
</tbody>
</table>
The data set contains data of **142** different countries from **year 1952 to 2007**, with data of every 5 years.

### Population

``` r
summary(gapminder$pop)
```

    ##      Min.   1st Qu.    Median      Mean   3rd Qu.      Max. 
    ## 6.001e+04 2.794e+06 7.024e+06 2.960e+07 1.959e+07 1.319e+09

During period from 1952 to 2007 the population's range for these countries was from 60,011, to 1,318,683,096.

``` r
ggplot(gapminder,aes(x=as.factor(year),y=pop)) +
       geom_boxplot(outlier.colour="purple",outlier.shape=1,outlier.size=1) + 
       ggtitle("Population's distribution by year") +
       xlab("Year") +
       ylab("Population")
```

![](hw02-CeciliaLe07_files/figure-markdown_github/unnamed-chunk-11-1.png)

The side-by-side boxplot of population by year shows that population tends to increase every year and also we can distinghis the same quantity of outliers across the years, and particularly three outliers. The average and the spread of population by year is summarized in the following table:

<table>
<thead>
<tr>
<th style="text-align:left;">
Year
</th>
<th style="text-align:right;">
Population's mean
</th>
<th style="text-align:right;">
Population's sd
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left;">
1952
</td>
<td style="text-align:right;">
16950402
</td>
<td style="text-align:right;">
58100863
</td>
</tr>
<tr>
<td style="text-align:left;">
1957
</td>
<td style="text-align:right;">
18763413
</td>
<td style="text-align:right;">
65504285
</td>
</tr>
<tr>
<td style="text-align:left;">
1962
</td>
<td style="text-align:right;">
20421007
</td>
<td style="text-align:right;">
69788650
</td>
</tr>
<tr>
<td style="text-align:left;">
1967
</td>
<td style="text-align:right;">
22658298
</td>
<td style="text-align:right;">
78375481
</td>
</tr>
<tr>
<td style="text-align:left;">
1972
</td>
<td style="text-align:right;">
25189980
</td>
<td style="text-align:right;">
88646817
</td>
</tr>
<tr>
<td style="text-align:left;">
1977
</td>
<td style="text-align:right;">
27676379
</td>
<td style="text-align:right;">
97481091
</td>
</tr>
<tr>
<td style="text-align:left;">
1982
</td>
<td style="text-align:right;">
30207302
</td>
<td style="text-align:right;">
105098650
</td>
</tr>
<tr>
<td style="text-align:left;">
1987
</td>
<td style="text-align:right;">
33038573
</td>
<td style="text-align:right;">
114756180
</td>
</tr>
<tr>
<td style="text-align:left;">
1992
</td>
<td style="text-align:right;">
35990917
</td>
<td style="text-align:right;">
124502589
</td>
</tr>
<tr>
<td style="text-align:left;">
1997
</td>
<td style="text-align:right;">
38839468
</td>
<td style="text-align:right;">
133417391
</td>
</tr>
<tr>
<td style="text-align:left;">
2002
</td>
<td style="text-align:right;">
41457589
</td>
<td style="text-align:right;">
140848283
</td>
</tr>
<tr>
<td style="text-align:left;">
2007
</td>
<td style="text-align:right;">
44021220
</td>
<td style="text-align:right;">
147621398
</td>
</tr>
</tbody>
</table>
Furthermore, during 2007 the top three of countries with biggest population is:

``` r
max_2007 <- data_2007 %>% 
            filter(pop >= sort(pop,decreasing=TRUE)[3])

max_2007
```

    ## # A tibble: 3 x 3
    ##   country              pop  year
    ##   <fct>              <int> <int>
    ## 1 China         1318683096  2007
    ## 2 India         1110396331  2007
    ## 3 United States  301139947  2007

During 2007 the top three of countries with samllest population is:

``` r
min_2007 <- data_2007 %>% 
            filter(pop <= sort(pop,decreasing=FALSE)[3])
min_2007
```

    ## # A tibble: 3 x 3
    ##   country                  pop  year
    ##   <fct>                  <int> <int>
    ## 1 Djibouti              496374  2007
    ## 2 Iceland               301931  2007
    ## 3 Sao Tome and Principe 199579  2007

We can appreciate that population distributions of the countries with the biggest population are different:

``` r
gapminder %>% 
  filter(country=="China" | country=="India" | country=="United States") %>% 
    ggplot(aes(country,pop)) +
           geom_violin(fill="#4C2C69",col="#42253B",alpha=0.5) +
           geom_jitter(col="#E3C854")
```

![](hw02-CeciliaLe07_files/figure-markdown_github/unnamed-chunk-16-1.png)

We can appreciate that population distributions of the countries with the smallest population are different too:

``` r
gapminder %>% 
  filter(country=="Djibouti" | country=="Iceland" | country=="Sao Tome and Principe") %>% 
    ggplot(aes(country,pop)) +
    geom_violin(fill="#00A6FB",col="#003554",alpha=0.35) +
    geom_jitter(col="#003554")
```

![](hw02-CeciliaLe07_files/figure-markdown_github/unnamed-chunk-17-1.png)

### Life expectancy and gdpPerCapita

In order to observe the relation described by the life expectancy and gdp Per Capita, the next plot can be drawn

``` r
gapminder %>% 
  filter(year==2007|year==2002|year==1997) %>% 
  ggplot(aes(lifeExp,gdpPercap,color=continent)) +
       geom_point(alpha=0.5)+
       facet_grid( ~ year) +
       xlab("Life Expectancy") +
       ylab("GDP Per Capita")
```

![](hw02-CeciliaLe07_files/figure-markdown_github/unnamed-chunk-18-1.png)

We can observe as the life expectancy increases, the GDP Per Capita increases too, not in a linear way, so we can just say that these variables have a **positive** relation. The color of points indicates the most of low GDP Per Capita and low life expectacy countries, correspond to Africa.

Now, we can see the mean of life expectancy for the last year (2007) by continent:

``` r
gapminder %>% 
  select(lifeExp,year,continent) %>% 
  filter(year==2007) %>% 
  group_by(continent) %>%
  summarize(Mean = mean(lifeExp)) %>% 
  kable()
```

<table>
<thead>
<tr>
<th style="text-align:left;">
continent
</th>
<th style="text-align:right;">
Mean
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left;">
Africa
</td>
<td style="text-align:right;">
54.80604
</td>
</tr>
<tr>
<td style="text-align:left;">
Americas
</td>
<td style="text-align:right;">
73.60812
</td>
</tr>
<tr>
<td style="text-align:left;">
Asia
</td>
<td style="text-align:right;">
70.72848
</td>
</tr>
<tr>
<td style="text-align:left;">
Europe
</td>
<td style="text-align:right;">
77.64860
</td>
</tr>
<tr>
<td style="text-align:left;">
Oceania
</td>
<td style="text-align:right;">
80.71950
</td>
</tr>
</tbody>
</table>
Therefore, we can expect to see the same ranking about gdp Per Capita

``` r
gapminder %>% 
  select(gdpPercap,year,continent) %>% 
  filter(year==2007) %>% 
  group_by(continent) %>%
  summarize(Mean = mean(gdpPercap)) %>% 
  kable()
```

<table>
<thead>
<tr>
<th style="text-align:left;">
continent
</th>
<th style="text-align:right;">
Mean
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left;">
Africa
</td>
<td style="text-align:right;">
3089.033
</td>
</tr>
<tr>
<td style="text-align:left;">
Americas
</td>
<td style="text-align:right;">
11003.032
</td>
</tr>
<tr>
<td style="text-align:left;">
Asia
</td>
<td style="text-align:right;">
12473.027
</td>
</tr>
<tr>
<td style="text-align:left;">
Europe
</td>
<td style="text-align:right;">
25054.482
</td>
</tr>
<tr>
<td style="text-align:left;">
Oceania
</td>
<td style="text-align:right;">
29810.188
</td>
</tr>
</tbody>
</table>
