# NYT Collaborative Cooking with NLP

Contributors: Shirley Li, Anila Yadavalli, Nida Obatake, and Enkhzaya Enkhtaivan.
Project as part of the May 2021 Data Science Boot Camp hosted by The Erdos Institute. 

## Project

We love finding recipes online for cooking and baking. Often the recipe comments section has invaluable information for the home cook who isn't using commercial grade test kitchens and equipment. For example, for making [Simple Crusty Bread]([url](https://cooking.nytimes.com/recipes/1018203-simple-crusty-bread)), you can make do without fancy equipment: "if you don't have a pizza stone, just use parchment paper and put your oven on the convection setting." 

We started with an ambitious question: how can we find and collate the most useful comments on recipes? The comments section is usually sorted by date (oldest or newest comments) or by likes (which is also biased by date; older comments who get likes will be more likely to float to the top and get more likes). Could we use NLP techniques to identify the most common topics and advice?

We trimmed our project idea down to a simpler exploratory form:
1. We scraped the New York Times "Salted Tahini Chocolate Chip Cookies" recipe comments.
2. We performed sentiment analysis and topic modelling to determine the best tips for recipes. 

## Sentiment Analysis
We built multiple sentiment analyzers and contrasted their results against our hand-coded data for the Salted Tahini Cookie recipe: the basic NLTK Vader sentiment analyzer, a logistic regression model trained on food.com data set (embedded with a doc2vec embedding trained on generic wikipedia text samples), and two recurrent neural networks (RNNs) using food.com training data sets and an additional word2vec embedding. 

## Topic Analysis
We present preliminary results of n-gram topic modelling to predict useful recipe tips from user-generated comments on the Salted Tahini Cookies recipe.
