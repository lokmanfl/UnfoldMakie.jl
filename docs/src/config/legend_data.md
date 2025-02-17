# [Legend Data](@id config_legend)

The legend data of the configuration consists of config options for the legend. 

## Line Plots and Butterfly Plots
For line plots the `legend!` function of the `AlgebraOfGraphics` module is used ([documentation](http://juliaplots.org/AlgebraOfGraphics.jl/stable/API/functions/#AlgebraOfGraphics.legend!)).

The `Legend` will be used automatically, when `AlgebraOfGraphics` is able to draw it. 
For this the `color` data will be used and has to be either non-numerical or `funcall(...;setExtraValues=(categoricalColor=true,)` needs to be set `true`.

## Parallel Coordinates Plots
In a parallel coordinate plot the `Legend` function of the `Makie` module is used ([documentation](https://makie.juliaplots.org/v0.17.13/examples/blocks/legend/index.html)).

The Legend will only be used when `funcall(...;setLayoutValues=(showLegend=true,)` is `true` and `funcall(...;setLayoutValues=(useColorbar=false,)` is `false`

## Legend data default options

- orientation = `:vertical`
- tellwidth = `true`
- tellheight = `true`
