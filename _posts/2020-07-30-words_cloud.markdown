---
layout: post
title:      "Words Cloud"
date:       2020-07-30 14:31:22 +0000
permalink:  words_cloud
---


**What is WordCloud?**
Many times you might have seen a cloud filled with lots of words in different sizes, which represent the frequency or the importance of each word. This is called Tag Cloud or WordCloud. 

**Prerequisites**
If you want to create a world cloud in your  notebook, you will need to install some packages below:
* numpy
* matplotlib
* PIL
* wordcloud

**How to import the necessary module**
```
from wordcloud import WordCloud, ImageColorGenerator
import matplotlib.pyplot as plt
from PIL import Image
import numpy as np
```
Where we see two new items:
1. WordCloud — base class to generate the word-cloud image
2. ImageColorGenerator — base class to recolor the words in the word-cloud image

**Don't forget to find a text**
We’ll need a few sentences of text as input for the word cloud. 
```
text = ""
with open('example.txt', encoding='utf-8') as f:
    text = ''.join(f.readlines())
```

**Create and initialize a WordCloud object**

`wc = WordCloud()`

Once you’ve created a WordCloud object, you can call the built-in generate function to generate a word cloud. We’ll pass in the text variable as an input to the function.

`wc.generate(text)`

Or you can display it in Jupyter Notebook via the functions in Matplotlib.
```
plt.imshow(wc, interpolation='bilinear')
plt.axis("off")
plt.show()
```
And you should see something like this:

![](https://miro.medium.com/max/698/1*GRK15jG2HXfNhF_iWC_Mbw.png)
