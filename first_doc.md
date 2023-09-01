---
title: "first_doc"
format: pdf
editor: visual
bibliography: [my_bib.bib, ds-h23.bib, my-ds23.bib]
keep-tex: true
keep-md: true
---


::: {.cell}

```{.r .cell-code}
library(tidyverse)
```
:::


## Quarto

Quarto enables you to weave together content and executable code into a finished document.
To learn more about Quarto see <https://quarto.org>.

@knuth1992

## Referanser

::: {#refs}
:::

## Running Code

When you click the **Render** button a document will be generated that includes both content and the output of embedded code.
You can embed code like this:


::: {.cell}

```{.r .cell-code}
1 + 1
```

::: {.cell-output .cell-output-stdout}
```
[1] 2
```
:::
:::


You can add options to executable code like this


::: {.cell}
::: {.cell-output .cell-output-stdout}
```
[1] 4
```
:::
:::


The `echo: false` option disables the printing of code (only output is displayed).


::: {.cell .fig-cap-location-margin}

````{.cell-code}
```{{r}}
#| label: fig-first_plot
#| fig-cap: 'First plot'
#| fig-cap-location: margin

plot(cars)
```
````

::: {.cell-output-display}
![First plot](first_doc_files/figure-pdf/fig-first_plot-1.pdf){#fig-first_plot fig-pos='H'}
:::
:::


Mitt første plot er vist i @fig-first_plot

## Litt klassisk R


::: {.cell}

```{.r .cell-code}
set.seed(666)

x <- rnorm(1000000)
x <- x[1:10]
q <- (x<0)
sum(q)
```

::: {.cell-output .cell-output-stdout}
```
[1] 6
```
:::
:::

::: {.cell}

```{.r .cell-code}
t1 <- Sys.time()
tail(x, n = 5)
```

::: {.cell-output .cell-output-stdout}
```
[1]  0.75839618 -1.30618526 -0.80251957 -1.79224083 -0.04203245
```
:::

```{.r .cell-code}
Sys.time() -t1
```

::: {.cell-output .cell-output-stdout}
```
Time difference of 0.0006699562 secs
```
:::

```{.r .cell-code}
length(x)
```

::: {.cell-output .cell-output-stdout}
```
[1] 10
```
:::

```{.r .cell-code}
x[(length(x) - 4): length(x)]
```

::: {.cell-output .cell-output-stdout}
```
[1]  0.75839618 -1.30618526 -0.80251957 -1.79224083 -0.04203245
```
:::
:::

::: {.cell}

```{.r .cell-code}
set.seed(666)

x <- rnorm(1000000)
q <- (x<0)
sum(q)
```

::: {.cell-output .cell-output-stdout}
```
[1] 500421
```
:::
:::

::: {.cell}

```{.r .cell-code}
temp <- c(11, 17, 22, 15, 15, 25)
weather <- c("Rainy", "Sunny", "Sunny", "Fair", "Fair", "Sunny")
names(temp) <- weather
temp[names(temp) == "Sunny"]
```

::: {.cell-output .cell-output-stdout}
```
Sunny Sunny Sunny 
   17    22    25 
```
:::

```{.r .cell-code}
sum(names(temp) == "Sunny")
```

::: {.cell-output .cell-output-stdout}
```
[1] 3
```
:::
:::

::: {.cell}

```{.r .cell-code}
# some codeing of sex, 1 female, 2 male
sex <- c(1, 2, 1, 2, 2, 1, 2)
# new labels, "F" for 1 and "M" for 2
sex_f <- factor(sex, labels = c("F", "M"))
table(sex_f)
```

::: {.cell-output .cell-output-stdout}
```
sex_f
F M 
3 4 
```
:::
:::

::: {.cell}

```{.r .cell-code}
(x <- 1:3)
```

::: {.cell-output .cell-output-stdout}
```
[1] 1 2 3
```
:::

```{.r .cell-code}
x[3] = 5.0
typeof(x)
```

::: {.cell-output .cell-output-stdout}
```
[1] "double"
```
:::
:::

::: {.cell}

```{.r .cell-code}
l <- list(x = 1:3, y = c("A", letters[4:13]), z = seq(from = 1.3, to = 2.7, by = 0.2))

typeof(l$x)
```

::: {.cell-output .cell-output-stdout}
```
[1] "integer"
```
:::

```{.r .cell-code}
is.vector(l$x)
```

::: {.cell-output .cell-output-stdout}
```
[1] TRUE
```
:::

```{.r .cell-code}
typeof(l$y)
```

::: {.cell-output .cell-output-stdout}
```
[1] "character"
```
:::
:::

::: {.cell}

```{.r .cell-code}
l <- list(
  x = 1:3, 
  y = c("A", letters[4:13]), 
  z = list(
    za = seq(from = 1.3, to = 2.7, by = 0.2), 
    zb = c(TRUE, FALSE), 
    zc = 5:9,
    zd = list(1, "F", 3.2)
    )
  )
```
:::

::: {.cell}

```{.r .cell-code}
df <- data.frame(x = 1:3, y = letters[1:3], z = LETTERS[1:3])
df1 <- data.frame(x = 1:3, y = letters[1:3], 
                 z = df)
df$q <- c(2.1, 0.4, 0.9)
df[,2]
```

::: {.cell-output .cell-output-stdout}
```
[1] "a" "b" "c"
```
:::

```{.r .cell-code}
length(df[,2])
```

::: {.cell-output .cell-output-stdout}
```
[1] 3
```
:::

```{.r .cell-code}
length(df[2,])
```

::: {.cell-output .cell-output-stdout}
```
[1] 4
```
:::

```{.r .cell-code}
str(df1)
```

::: {.cell-output .cell-output-stdout}
```
'data.frame':	3 obs. of  5 variables:
 $ x  : int  1 2 3
 $ y  : chr  "a" "b" "c"
 $ z.x: int  1 2 3
 $ z.y: chr  "a" "b" "c"
 $ z.z: chr  "A" "B" "C"
```
:::
:::

::: {.cell}

```{.r .cell-code}
df3 <- data.frame(x = 1:3, y = 4:6, z = 7:9)
mean(unlist(df3[3,]))
```

::: {.cell-output .cell-output-stdout}
```
[1] 6
```
:::
:::

::: {.cell}

```{.r .cell-code}
# define a matirc in R
X <- matrix(c(2, 2, -1, 5, 2, 6), nrow = 3, byrow = FALSE)
matrix(c(2, 2, -1, 5, 2, 6), nrow = 3, byrow = TRUE)
```

::: {.cell-output .cell-output-stdout}
```
     [,1] [,2]
[1,]    2    2
[2,]   -1    5
[3,]    2    6
```
:::
:::

::: {.cell}

```{.r .cell-code}
(cars_sub <- subset(cars, subset = cars$speed > 6 & cars$speed < 11))
```

::: {.cell-output .cell-output-stdout}
```
  speed dist
3     7    4
4     7   22
5     8   16
6     9   10
7    10   18
8    10   26
9    10   34
```
:::
:::

::: {.cell}

```{.r .cell-code}
lm1 <- lm(formula = dist ~ speed, data = cars)
summary(lm1)
```

::: {.cell-output .cell-output-stdout}
```

Call:
lm(formula = dist ~ speed, data = cars)

Residuals:
    Min      1Q  Median      3Q     Max 
-29.069  -9.525  -2.272   9.215  43.201 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept) -17.5791     6.7584  -2.601   0.0123 *  
speed         3.9324     0.4155   9.464 1.49e-12 ***
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 15.38 on 48 degrees of freedom
Multiple R-squared:  0.6511,	Adjusted R-squared:  0.6438 
F-statistic: 89.57 on 1 and 48 DF,  p-value: 1.49e-12
```
:::
:::

::: {.cell}

:::
