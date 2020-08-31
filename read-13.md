-    matplotlib is probably the single most used Python package for 2D-graphics. It provides both a very quick way to visualize data from Python and publication-quality figures in many formats. We are going to explore matplotlib in interactive mode covering most common cases.

    IPython and the pylab mode
    IPython is an enhanced interactive Python shell that has lots of interesting features including named inputs and outputs, access to shell commands, improved debugging and much more. When we start it with the command line argument -pylab (--pylab since IPython version 0.12), it allows interactive matplotlib sessions that have Matlab/Mathematica-like functionality.

    pyplot
    pyplot provides a convenient interface to the matplotlib object-oriented plotting library. It is modeled closely after Matlab(TM). Therefore, the majority of plotting commands in pyplot have Matlab(TM) analogs with similar arguments. Important commands are explained with interactive examples.

    Simple plot
    In this section, we want to draw the cosine and sine functions on the same plot. Starting from the default settings, we'll enrich the figure step by step to make it nicer.

    The first step is to get the data for the sine and cosine functions:

    import numpy as np

    X = np.linspace(-np.pi, np.pi, 256, endpoint=True)
    C, S = np.cos(X), np.sin(X)
    X is now a NumPy array with 256 values ranging from -π to +π (included). C is the cosine (256 values) and S is the sine (256 values).

    To run the example, you can download each of the examples and run it using:

    $ python exercice_1.py
    You can get source for each step by clicking on the corresponding figure.

    Using defaults
    Documentation

    plot tutorial
    plot() command
    figures/exercice_1.png
    Matplotlib comes with a set of default settings that allow customizing all kinds of properties. You can control the defaults of almost every property in matplotlib: figure size and dpi, line width, color and style, axes, axis and grid properties, text and font properties and so on. While matplotlib defaults are rather good in most cases, you may want to modify some properties for specific cases.

    Instantiating defaults
    Documentation

    Customizing matplotlib
    figures/exercice_2.png
    In the script below, we've instantiated (and commented) all the figure settings that influence the appearance of the plot. The settings have been explicitly set to their default values, but now you can interactively play with the values to explore their affect (see Line properties and Line styles below).

    Changing colors and line widths
    Documentation

    Controlling line properties
    Line API
    figures/exercice_3.png
    As a first step, we want to have the cosine in blue and the sine in red and a slightly thicker line for both of them. We'll also slightly alter the figure size to make it more horizontal.

    ...
    plt.figure(figsize=(10,6), dpi=80)
    plt.plot(X, C, color="blue", linewidth=2.5, linestyle="-")
    plt.plot(X, S, color="red",  linewidth=2.5, linestyle="-")
    ...
    Setting limits
    Documentation

    xlim() command
    ylim() command
    figures/exercice_4.png
    Current limits of the figure are a bit too tight and we want to make some space in order to clearly see all data points.

    ...
    plt.xlim(X.min()*1.1, X.max()*1.1)
    plt.ylim(C.min()*1.1, C.max()*1.1)
    ...
    Setting ticks
    Documentation

    xticks() command
    yticks() command
    Tick container
    Tick locating and formatting
    figures/exercice_5.png
    Current ticks are not ideal because they do not show the interesting values (+/-π,+/-π/2) for sine and cosine. We'll change them such that they show only these values.

    ...
    plt.xticks( [-np.pi, -np.pi/2, 0, np.pi/2, np.pi])
    plt.yticks([-1, 0, +1])
    ...
    Setting tick labels
    Documentation

    Working with text
    xticks() command
    yticks() command
    set_xticklabels()
    set_yticklabels()
    figures/exercice_6.png
    Ticks are now properly placed but their label is not very explicit. We could guess that 3.142 is π but it would be better to make it explicit. When we set tick values, we can also provide a corresponding label in the second argument list. Note that we'll use latex to allow for nice rendering of the label.

    ...
    plt.xticks([-np.pi, -np.pi/2, 0, np.pi/2, np.pi],
        [r'$-\pi$', r'$-\pi/2$', r'$0$', r'$+\pi/2$', r'$+\pi$'])

    plt.yticks([-1, 0, +1],
        [r'$-1$', r'$0$', r'$+1$'])
    ...
    Moving spines
    Documentation

    Spines
    Axis container
    Transformations tutorial
    figures/exercice_7.png
    Spines are the lines connecting the axis tick marks and noting the boundaries of the data area. They can be placed at arbitrary positions and until now, they were on the border of the axis. We'll change that since we want to have them in the middle. Since there are four of them (top/bottom/left/right), we'll discard the top and right by setting their color to none and we'll move the bottom and left ones to coordinate 0 in data space coordinates.

    ...
    ax = plt.gca()