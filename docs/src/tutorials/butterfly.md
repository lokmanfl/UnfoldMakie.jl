# [Butterfly Plot Visualization](@id bfp_vis)

Here we discuss butterfly plot visualization. 
Make sure you have looked into the [installation instructions](@ref install_instruct).

## Include used Modules
The following modules are necessary for following this tutorial:
```@example main
using UnfoldMakie
using Unfold
using DataFrames
using CairoMakie
using DataFramesMeta
```
Note that `DataFramesMeta` is also used here in order to be able to use `@subset` for testing (filtering).

## Data
In case you want to try with different data, look at the [Load Data](@ref test_data) section. 


We filter the data to make it more clearly represented:
```@example main
results_plot_butter = @subset(UnfoldMakie.example_data(),:coefname .== "A");
first(results_plot_butter,3)
```

## Plot Butterfly Plots

The following code will plot the default butterfly plot
```@example main
plot_butterfly(results_plot_butter)
```
At this point you can detail changes you want to make to the visualization through the plot config. These are detailed further below. 


## Column Mappings for Butterfly Plots

Since butterfly plots use a `DataFrame` as an input, the library needs to know the names of the columns used for plotting. You can set these mapping values by `plot_butterfly(...; setMappingValues=(:x=:time,))`, that is, providing a `NamedTuple` (note the trailling `,` in case you specify only a single property!)

For more information about mapping values look into the [Mapping Data](@ref config_mapping) section of the documentation.

While there are multiple default values, that are checked in that order if they exist in the `DataFrame`, a custom name might need to be choosen for:

### x
Default is `(:x, :time)`.

### y
Default is `(:y, :estimate, :yhat)`.

### topoPositions
Default is `(:pos, :positions, :position, :topoPositions, :x, :nothing)`

### topoLabels
Default is `(:labels, :label, :topoLabels, :sensor, :nothing)`

### topoChannels
Default is `(:channels, :channel, :topoChannel, :nothing)`

## Configurations for Butterfly Plots

Here we look into possible options for configuring the butterfly plot visualization using `(...;setExtraValues=(<name>=<value>,...)`.
This is the list of unique configuration (extraData):
- topoLegend (boolean)

### topoLegend (boolean)
Indicating whether the topo legend is displayed.
Default is `true`.


For more general options look into the `Plot Configuration` section of the documentation.


Since the configurations for line plots can be applied to butterfly plots as well.
[Here](@ref lp_vis) you can find the configurations for line plots, 

