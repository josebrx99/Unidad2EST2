<!-- README.md is generated from README.Rmd. Please edit that file -->

# Unidad2EST2

<!-- badges: start -->
<!-- badges: end -->

Tutorial de sobre conceptos basicos Unidad 2 del curso "Metodos estadisticos y simulacion"

## InstalaciC3n

Este paquete esta en su version de construccion, por lo tanto se encontrara alojado en GitHub durante su etapa de elaboracion.

``` r
library(devtools)
devtools::install_github("josebrx99/Unidad2EST2", force = TRUE, upgrade = TRUE)
```

## Tutoriales

Este paquete cuenta con los siguientes tutoriales: \\
* Conceptos: conceptos basicos de estadistica. \\
* ACP: analisis de componentes principales

``` r
library(Unidad2EST2)
learnr::run_tutorial(name = "Conceptos", package = "Unidad2EST2")
learnr::run_tutorial(name = "ACP", package = "Unidad2EST2")
```







