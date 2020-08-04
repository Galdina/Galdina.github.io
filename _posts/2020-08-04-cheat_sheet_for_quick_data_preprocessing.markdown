---
layout: post
title:      "Cheat sheet for quick data preprocessing"
date:       2020-08-04 04:51:23 +0000
permalink:  cheat_sheet_for_quick_data_preprocessing
---

It happened! You are entering the Data Science field. In your dreams you create cool neural networks, write a voice assistant, beat financial marketing. But... One of the most important and time-consuming moments is processing data.  

For myself I created a cheat sheet to obtain data before the project.
[Data example](https://www.kaggle.com/dgomonov/new-york-city-airbnb-open-data?select=AB_NYC_2019.csv)

```
import pandas as pd #import pandas
import numpy as np  #import numpy
df = pd.read_csv("AB_NYC_2019.csv") #read dataset and put it into df
```
Look at the first 3 lines to understand what the values look like:
```
df.head(3)
```
![](https://hsto.org/webt/dv/ma/uo/dvmauozsaq1zbqj28cn_naznakk.png)

***Demonstrating Column Information:***
1. Display all columns with types
```
df.info()
```
![](https://hsto.org/webt/ma/5r/rp/ma5rrpw-album5kcvritb-vxzhq.png)
2. and some more information about numeric columns:
```
df.describe()
```
![](https://hsto.org/webt/mc/8x/p5/mc8xp5cwiqkogvnn7ra1-v8fq-o.png)

Here we check few questions about dataset and create plan for next step:
* Does the number of lines in each column correspond to the total number of lines?
* What is data type in each column?
* Can we see target columns?

***Let's check values:***
3. missing values in columns:
```
import seaborn as sns
sns.heatmap(df.isnull(),yticklabels=False,cbar=False,cmap='viridis')
```
![](https://hsto.org/webt/xp/aw/jt/xpawjttv_cfsyy-ummugnjl8n04.png)

4. do we have columns with only one value in all rows (they will not affect the result):

```
df = df[[c for c
        in list(df)
        if len(df[c].unique()) > 1]]
```

5. do we have duplicate values:
```
df.drop_duplicates(inplace=True)
```
6. work with empty values:![](https://pbs.twimg.com/media/EejQKwAUMAAwuv5?format=png&name=small)





