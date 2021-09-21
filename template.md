Simple document
================
Anyu Zhu
2021-09-16

I’m an R Markdown document\!

# Section 1

Here’s a **code chunk** that samples from a *normal distribution*:

``` r
samp = rnorm(100)
length(samp)
```

    ## [1] 100

# Section 2

I can take the mean of the sample, too\! The mean is -0.0405269.

# Section 3

new code chunk: option + command + i

``` r
library(tidyverse)
## ── Attaching packages ─────────────────────────────────────── tidyverse 1.3.1 ──
## ✓ ggplot2 3.3.3     ✓ purrr   0.3.4
## ✓ tibble  3.1.0     ✓ dplyr   1.0.5
## ✓ tidyr   1.1.3     ✓ stringr 1.4.0
## ✓ readr   1.4.0     ✓ forcats 0.5.1
## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
## x dplyr::filter() masks stats::filter()
## x dplyr::lag()    masks stats::lag()
set.seed(1)
plot_df = tibble(
  x = rnorm(1000, sd = 0.5),
  y = 1 + 2 * x + rnorm(1000),
  y_quad = 1 + 2 * x^2 + rnorm(1000)
)
ggplot(plot_df, aes(x = x)) + geom_histogram(col = 'red')
## `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.
```

![](template_files/figure-gfm/unnamed-chunk-2-1.png)<!-- -->

``` r
df = tibble(
  sample_1 = rnorm(500, mean = 1),
  filter_1 = sample_1 > 0,
  filter_2 = abs(sample_1)
)
ggplot(df, aes(x = filter_2)) + geom_histogram(col = 'red')
```

    ## `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.

![](template_files/figure-gfm/assessment%201-1.png)<!-- -->

``` r
median_sample_1 = median(pull(df,sample_1)) # pull(data frame, column)
```

The median is 1.0858369
