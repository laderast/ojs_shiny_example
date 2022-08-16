
<!-- README.md is generated from README.Rmd. Please edit that file -->

# Some Quick Notes about Observable + Shiny

<!-- badges: start -->
<!-- badges: end -->

## Division of Labor

In a normal shiny application, `ui` and `server` handle the following:

### ui

-   Handles controls
-   Handles layout / displaying plots

### server

-   Reacts to changes in controls
-   Handles plotting

However, Observable in the OJS + Shiny combo has the following division
of labor:

### Quarto

-   Handles layout

### OJS

-   Handles controls (using `viewof`)
-   Handles plotting

### Shiny

-   Reacts to changes in controls

So as you can see, the division of labor is different in this combo.

## Some notes on a dev workflow

-   Plan your layout on paper (sidebars, main panels, tabs), and
    implement using Quarto
-   Build your Observable controls first using `viewof`
-   Debug the Reactive next (Observable controls will be in `input`
    object)
-   Connect the reactive to OJS using `ojs_define()`
-   Test the OJS plotting (Can also do this early with a non-reactive
    dataset)
