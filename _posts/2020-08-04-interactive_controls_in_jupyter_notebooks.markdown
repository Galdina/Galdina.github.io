---
layout: post
title:      "Interactive Controls in Jupyter Notebooks"
date:       2020-08-04 07:52:15 +0000
permalink:  interactive_controls_in_jupyter_notebooks
---


In this blog I want to make quick interaction on how to use interactive widgets to enhance data exploration and analysis. Interactive controls give us the opportunity to change inputs without needing to rewrite or rerun code.

![](https://i.imgur.com/tT8kL1e.jpg)

To start using the library we need to install the **ipywidgets** extension. We install widgets into the learn-env kernel using this command: 
```
import sys
!{sys.executable} -m pip install ipywidgets
```
This library allows us to turn Jupyter Notebooks from static documents into interactive dashboards, perfect for exploring and visualizing data. Widgets have their own display repr which allows them to be displayed using IPython’s display framework.

**What we should remember while working with widget:**
* it is displayed inside the output area below the code cell 
* clearing cell output will also remove the widget

We just import library and start working with widgets:
```
import ipywidgets as widgets
```
After this step we can see full list of widgets  if run the following command:
```
print(dir(widgets))
```

The most useful widgets for me:

**Sliders**

It is a numeric widget, it is designed to display numeric values (integers and floats, both bounded and unbounded). For example we can create a integer slider whom interact with function to calculate square:


```
slider = widgets.IntSlider(value=5,
                              min=0,
                              max=10,
                              step=1,
                              description='Square:',
                              disabled=False,
                              continuous_update=False,
                              orientation='horizontal',
                              readout=True,
                              readout_format='d')

def square(number):
    return number*number

widgets.interact(square, number=slider);
```

![](https://i.imgur.com/hAhzTY2.png)

We can define the minimum and maximum values, the interval size (step), a description and an initial value.
If we want to use input on the next step then to read the value of a widget, we will query its value property. Similarly, we can set a widget’s value:
```
slider.value
```
This command shows us what the last value we pass into the widget.

**Text**

Widget can display a string value.

```
text = widgets.Text(    
    value='Hello World',
    placeholder='Type something',
    description='String:',
    disabled=False
)
display(text)
```
We can synchronise the values of two widgets by using the *jslink()* function.

```
slider = widgets.IntSlider()
text = widgets.IntText()

display(slider, text)
widgets.jslink((slider, 'value'), (text, 'value'))
```

![](https://i.imgur.com/1HStXsQ.png)
If we change value in one widget second changes automatically.

**Select**

This widget can be used to display single selection lists. You can specify the enumeration of selectable options by passing a list (options are either (label, value) pairs, or simply values for which the labels are derived by calling str).

```
cuisine = widgets.Select(
options=['indian', 'mexican', 'chinese', 'thai', 'italian', 'american', 'asian', 'middle-eastern', 'hawaiian', 'european','north-american'],
value='mexican',
description='Cuisine:',
disabled=False)

display(cuisine)
```

![](https://i.imgur.com/cYJPKfV.png)

 **Plots**

```
pi = math.pi
t = np.arange(0.0,1.0,0.001)

def pltcos(f):
    plt.plot(t,np.cos(2*pi*t*f))
    plt.axis([0, 1, -1, 1])
    plt.title('cos(2*pi*f*t)')
    plt.show()
    
interact(pltsin,f=(1,20,1))
```


I show a few widgets in action but we still have only scratched the surface here — we can build really complex and extensive GUIs using ipywidgets. I hope you all agree they deserve a place in any Data Scientist’s toolbox as they enhance our productivity and add a lot of value during data exploration.

My next step is to build your own custom widgets! For more info take a look [here](https://ipywidgets.readthedocs.io/en/stable/examples/Widget%20Custom.html).

P.S. For a full list of widgets you can check out the [documentation](https://ipywidgets.readthedocs.io/en/stable/examples/Widget%20List.html).



