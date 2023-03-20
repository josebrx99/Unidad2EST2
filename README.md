<!-- README.md is generated from README.Rmd. Please edit that file -->

# Unidad2EST2

<!-- badges: start -->
<!-- badges: end -->

Tutoriales de sobre conceptos basicos Unidad 2 del curso "Metodos estadisticos y simulacion", los pasos a seguir para acceder a estos son:

## 1) Instalacion

Desde R Studio instalar el paquete:

``` r
library(devtools)
devtools::install_github("josebrx99/Unidad2EST2", force = TRUE, upgrade = TRUE)
```

## 2) Abrir tutoriales

Este paquete cuenta con los siguientes tutoriales:

**Conceptos: conceptos basicos de estadistica**
``` r
library(Unidad2EST2)
learnr::run_tutorial(name = "Conceptos", package = "Unidad2EST2")
```

**ACP: analisis de componentes principales**
``` r
library(Unidad2EST2)
learnr::run_tutorial(name = "ACP", package = "Unidad2EST2")
```








