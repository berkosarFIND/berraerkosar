
<!-- README.md is generated from README.Rmd. Please edit that file -->

# berraerkosar

<!-- badges: start -->

[![R-CMD-check](https://github.com/berkosarFIND/berraerkosar/workflows/R-CMD-check/badge.svg)](https://github.com/berkosarFIND/berraerkosar/actions)
<!-- badges: end -->

The goal of berraerkosar is to calculate the body mass index and to list
the datasets that are present in different sheets of an excel file.

## Installation

You can install the development version of berraerkosar like so:

``` r
remotes::install_local(path = 'berraerkosar_0.0.0.9000.tar.gz')
```

## Example

This example shows how to calculate a body mass index using the bmi
function.

This following examples show how to use the BMI function.

``` r
library(dplyr)
#> 
#> Attaching package: 'dplyr'
#> The following objects are masked from 'package:stats':
#> 
#>     filter, lag
#> The following objects are masked from 'package:base':
#> 
#>     intersect, setdiff, setequal, union
library(berraerkosar)

#Calculating a single BMI
bmi(mass = 80, height = 1.80) # Should give 24.7
#> [1] 24.7

#To insert BMI column on a data frame
data("data_weight")
data_weight %>%
  mutate(bmi = bmi(mass = mass, height = height))
#>                     name height   mass  bmi
#> 1         Luke Skywalker   1,72   77,0  0.1
#> 2                  C-3PO   1,67   75,0  0.1
#> 3                  R2-D2   0,96   32,0  0.5
#> 4            Darth Vader   2,02  136,0  0.0
#> 5            Leia Organa   1,50   49,0  0.2
#> 6              Owen Lars   1,78  120,0  0.0
#> 7     Beru Whitesun lars   1,65   75,0  0.1
#> 8                  R5-D4   0,97   32,0  0.4
#> 9      Biggs Darklighter   1,83   84,0  0.0
#> 10        Obi-Wan Kenobi   1,82   77,0  0.0
#> 11      Anakin Skywalker   1,88   84,0  0.0
#> 12        Wilhuff Tarkin   1,80   <NA>   NA
#> 13             Chewbacca   2,28  112,0  0.0
#> 14              Han Solo   1,80   80,0  0.0
#> 15                Greedo   1,73   74,0  0.1
#> 16 Jabba Desilijic Tiure   1,75 1358,0  0.0
#> 17        Wedge Antilles   1,70   77,0  0.1
#> 18      Jek Tono Porkins   1,80  110,0  0.0
#> 19                  Yoda   0,66   17,0 11.0
#> 20             Palpatine   1,70   75,0  0.1
#> 21             Boba Fett   1,83   78,2  0.0
#> 22                 IG-88   2,00  140,0  0.0
#> 23                 Bossk   1,90  113,0  0.0
#> 24      Lando Calrissian   1,77   79,0  0.1
#> 25                 Lobot   1,75   79,0  0.1
#> 26                Ackbar   1,80   83,0  0.1
#> 27            Mon Mothma   1,50   <NA>   NA
#> 28          Arvel Crynyd   <NA>   <NA>   NA
#> 29 Wicket Systri Warrick   0,88   20,0  1.3
#> 30             Nien Nunb   1,60   68,0  0.2
#> 31          Qui-Gon Jinn   1,93   89,0  0.0
#> 32           Nute Gunray   1,91   90,0  0.0
#> 33         Finis Valorum   1,70   <NA>   NA
#> 34         Jar Jar Binks   1,96   66,0  0.0
#> 35          Roos Tarpals   2,24   82,0  0.0
#> 36            Rugor Nass   2,06   <NA>   NA
#> 37              Ric Olie   1,83   <NA>   NA
#> 38                 Watto   1,37   <NA>   NA
#> 39               Sebulba   1,12   40,0  0.3
#> 40         Quarsh Panaka   1,83   <NA>   NA
#> 41        Shmi Skywalker   1,63   <NA>   NA
#> 42            Darth Maul   1,75   80,0  0.1
#> 43           Bib Fortuna   1,80   <NA>   NA
#> 44           Ayla Secura   1,78   55,0  0.0
#> 45              Dud Bolt   0,94   45,0  0.9
#> 46               Gasgano   1,22   <NA>   NA
#> 47        Ben Quadinaros   1,63   65,0  0.1
#> 48            Mace Windu   1,88   84,0  0.0
#> 49          Ki-Adi-Mundi   1,98   82,0  0.0
#> 50             Kit Fisto   1,96   87,0  0.0
#> 51             Eeth Koth   1,71   <NA>   NA
#> 52            Adi Gallia   1,84   50,0  0.0
#> 53           Saesee Tiin   1,88   <NA>   NA
#> 54           Yarael Poof   2,64   <NA>   NA
#> 55              Plo Koon   1,88   80,0  0.0
#> 56            Mas Amedda   1,96   <NA>   NA
#> 57          Gregar Typho   1,85   85,0  0.0
#> 58                 Corde   1,57   <NA>   NA
#> 59           Cliegg Lars   1,83   <NA>   NA
#> 60     Poggle the Lesser   1,83   80,0  0.0
#> 61       Luminara Unduli   1,70   56,2  0.1
#> 62         Barriss Offee   1,66   50,0  0.1
#> 63                 Dorme   1,65   <NA>   NA
#> 64                 Dooku   1,93   80,0  0.0
#> 65   Bail Prestor Organa   1,91   <NA>   NA
#> 66            Jango Fett   1,83   79,0  0.0
#> 67            Zam Wesell   1,68   55,0  0.1
#> 68       Dexter Jettster   1,98  102,0  0.0
#> 69               Lama Su   2,29   88,0  0.0
#> 70               Taun We   2,13   <NA>   NA
#> 71            Jocasta Nu   1,67   <NA>   NA
#> 72         Ratts Tyerell   0,79   15,0  2.2
#> 73                R4-P17   0,96   <NA>   NA
#> 74            Wat Tambor   1,93   48,0  0.0
#> 75              San Hill   1,91   <NA>   NA
#> 76              Shaak Ti   1,78   57,0  0.0
#> 77              Grievous   2,16  159,0  0.0
#> 78               Tarfful   2,34  136,0  0.0
#> 79       Raymus Antilles   1,88   79,0  0.0
#> 80             Sly Moore   1,78   48,0  0.0
#> 81            Tion Medon   2,06   80,0  0.0
#> 82                  Finn   <NA>   <NA>   NA
#> 83                   Rey   <NA>   <NA>   NA
#> 84           Poe Dameron   <NA>   <NA>   NA
#> 85                   BB8   <NA>   <NA>   NA
#> 86        Captain Phasma   <NA>   <NA>   NA
#> 87         Padme Amidala   1,65   45,0  0.1
```
