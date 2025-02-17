
## Package overview

Functions to find a short and accurate decision rule in disjunctive
normal form using the Exhaustive Procedure for LOgic-Rule Extraction
(EXPLORE) algorithm. The application performs and exhaustive search on
all Boolean Normal Form decision rules.

## Package installation

You can install the latest version of EXPLORE like so:

``` r
install.packages("remotes")
remotes::install_github("mi-erasmusmc/EXPLORE")
```

Additional instructions: to be added.

## Example usage using iris dataset

``` r
library(Explore)
library(farff)
```

Load data:

``` r
data <- farff::readARFF(system.file("examples/iris.arff", package = "Explore"))
output_path <- file.path(getwd(), "output//")
```

Fit model with defaults and/or input parameters:

``` r
model <- Explore::trainExplore(output_path = output_path, 
                               file_name = "iris", 
                               train_data = data, 
                               ClassFeature = "'class'", 
                               PositiveClass = '"Iris-versicolor"')
```

Predict:

``` r
prediction <- Explore::predictExplore(model, test_data = data)
```

Additional documentation includes: - Vignette code examples in
combination with PLP: [to be
added](~/Documents/Git/Explore/vignettes/EXPLORE_withPLP.Rmd) - Package
manual: [to be added](~/Documents/Git/Explore/vignettes/Explore_1.0.pdf)

## Development status

EXPLORE is under active development.

## Publication

Rijnbeek, P.R., Kors, J.A. Finding a short and accurate decision rule in
disjunctive normal form by exhaustive search. Machine Learning 80, 33–62
(2010). <https://doi.org/10.1007/s10994-010-5168-9>
