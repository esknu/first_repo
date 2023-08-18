---
title: "first_doc"
format: html
editor: visual
bibliography: my_bib.bib
keep-tex: true
keep-md: true
---



## Quarto

Quarto enables you to weave together content and executable code into a finished document.
To learn more about Quarto see <https://quarto.org>.

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
![First plot](first_doc_files/figure-html/fig-first_plot-1.png){#fig-first_plot width=672}
:::
:::


Mitt første plot er vist i @fig-first_plot
