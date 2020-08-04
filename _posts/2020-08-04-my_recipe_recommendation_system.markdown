---
layout: post
title:      "My recipe recommendation system"
date:       2020-08-04 08:26:02 +0000
permalink:  my_recipe_recommendation_system
---


**Why recommendation system?**

Nowadays, recommender systems are used to personalise your experience on the web, telling you what to buy, where to eat or even who you should be friends with. Also they help people find out what they want or discover something new. I stock up with food stuff.
People’s tastes vary but generally follow patterns. People tend to like things that are similar to other things they like, and they tend to have similar taste as other people they are close with. Recommender systems try to capture these patterns to help predict what else you might like. E-commerce, social media, video and online news platforms have been actively deploying their own recommender systems to help their customers to choose products more efficiently, which serves as a win-win strategy.

**Introduction, Motivation and Problem Definition**

What should I eat? This is a common problem, which many people face daily. Even if they prefer to eat home cooked healthy meals many feel they have no option but to turn to restaurants or fast food due to lack of ideas or time .
In order to solve this problem, we can gather data from user input and compare it to recipes listed on food.com. From this we can create an algorithm to provide meal recipe recommendations to the user.

The parameters we will be working with are:
* the amount of time the recipe takes to prepare
* the cuisine desired by the user
* the ingredients available on hand
* the amount of nutrition

With this data we can build a recommender system in which the user inputs the amount of time they have available and the desired cuisine from any world region they desire. Based on these inputs we will generate a short list of recipes that fit their preferences.

**Data for project**

I work with a dataset from site [food.com](https://www.food.com/), which presents more than 150,000 recipes from more than 10 world cuisine, all these recipes use almost 8,000 unique ingredients. They also include various attributes of the recipe such as the name, the time it takes to cook, the calorie level, the technique to execute it, the number of steps and even some tags.

The data pre-processing step include primarile converting attributes such as recipe name, tags or list of ingredients into exploitable data. 

**Create model**

I create a model using KNN and TfidfVectorizer. In order to solve this problem, I can gather data from user input and compare it to recipes listed on food.com. From this we can create an algorithm to provide meal recipe recommendations to the user. 

![](https://i.imgur.com/CbAGe5P.png)

Based on these inputs model generate a short list of recipes that fit their preferences. In ideal situation users tells the recommender program what ingredients they have on hand and it given the best meal recipes. My recommendation system can give only 75% of accuracy.

