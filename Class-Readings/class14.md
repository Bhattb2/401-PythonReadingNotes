# Data Visualization

## MatplotLib

[Matplotlib User Guide](https://matplotlib.org/users/index.html)

Matplotlib is a common library for displaying 2d graphics in Python

It is customizable, you can set all sorts of things, like dpi, line width, color, axis, grid properties, text, ticks, etc.

You can make animations by handling the frames. There are some really excellent examples, and tutorials online, so look them up and follow along.

There are also lots of projects that you can build from, for example you can use a basemap, and then render any number of interesting data on top of the map, like geo coordinates of flights, or the given example from the tutorial was to show earthquakes. Really, if you can access geographic data, you can render it.


## Simple plot

In this section, we want to draw the cosine and sine functions on the same plot. Starting from the default settings, we'll enrich the figure step by step to make it nicer.

The first step is to get the data for the sine and cosine functions:

    import numpy as np

    X = np.linspace(-np.pi, np.pi, 256, endpoint=True)
    C, S = np.cos(X), np.sin(X)

X is now a NumPy array with 256 values ranging from -π to +π (included).

C is the cosine (256 values) and S is the sine (256 values).

To run the example, you can download each of the examples and run it using:

    $ python exercice_1.py


## What is Bokeh?
### BOKEH
Bokeh is an interactive visualization library that targets modern web browsers for presentation. It is good for:

Interactive visualization in modern browsers
Standalone HTML documents, or server-backed apps
Expressive and versatile graphics
Large, dynamic or streaming data
Easy usage from python (or Scala, or R, or...)


Bokeh is an interactive visualization library for modern web browsers. It provides elegant, concise construction of versatile graphics, and affords high-performance interactivity over large or streaming datasets. Bokeh can help anyone who would like to quickly and easily make interactive plots, dashboards, and data applications.

    # Standard imports 

    from bokeh.io import output_notebook, show
    output_notebook()
    


    # Plot a complex chart with intearctive hover in a few lines of code

    from bokeh.models import ColumnDataSource, HoverTool
    from bokeh.plotting import figure
    from bokeh.sampledata.autompg import autompg_clean as df
    from bokeh.transform import factor_cmap

    df.cyl = df.cyl.astype(str)
    df.yr = df.yr.astype(str)

    group = df.groupby(by=['cyl', 'mfr'])
    source = ColumnDataSource(group)

    p = figure(plot_width=800, plot_height=300, title="Mean MPG by # Cylinders and Manufacturer",
            x_range=group, toolbar_location=None, tools="")

    p.xgrid.grid_line_color = None
    p.xaxis.axis_label = "Manufacturer grouped by # Cylinders"
    p.xaxis.major_label_orientation = 1.2

    index_cmap = factor_cmap('cyl_mfr', palette=['#2b83ba', '#abdda4', '#ffffbf', '#fdae61', '#d7191c'], 
                            factors=sorted(df.cyl.unique()), end=1)

    p.vbar(x='cyl_mfr', top='mpg_mean', width=1, source=source,
        line_color="white", fill_color=index_cmap, 
        hover_line_color="darkgrey", hover_fill_color=index_cmap)

    p.add_tools(HoverTool(tooltips=[("MPG", "@mpg_mean"), ("Cyl, Mfr", "@cyl_mfr")]))

    show(p)


## Bookmark/Skim
[Seaborn Tutorial](https://seaborn.pydata.org/tutorial.html)

[Bokeh Tutorial](https://mybinder.org/v2/gh/bokeh/bokeh-notebooks/master?filepath=tutorial%2F00%20-%20Introduction%20and%20Setup.ipynb)

## Additional Resources

[Seaborn Cheat Sheet](https://s3.amazonaws.com/assets.datacamp.com/blog_assets/Python_Seaborn_Cheat_Sheet.pdf)


[Matplotlib Tutorial](https://github.com/rougier/matplotlib-tutorial)

[Customizing Matplotlib](https://matplotlib.org/tutorials/introductory/customizing.html)

[Animation](https://matplotlib.org/api/animation_api.html)

[Seaborn tutorial](https://github.com/rougier/matplotlib-tutorial)
