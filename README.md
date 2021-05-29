# collaborative-cooking-with-nlp

Project as part of the May 2021 Data Science Boot Camp hosted by The Erdos Institute. Contributors: Anila Yadavalli, Nida Obatake, Shirley Li, Enkhzaya Enkhtaivan.

Our goal is to perform sentiment analysis and topic modelling to determine the best tips for recipes. 

### Sentiment Analysis
We performed sentiment analysis on the New York Times "Salted Tahini Chocolate Chip Cookies" recipe comments. We built multiple sentiment analyzers and contrasted their results against our hand-coded data for the Salted Tahini Cookie recipe: the basic NLTK Vader sentiment analyzer, a logistic regression model trained on food.com data set (embedded with a doc2vec embedding trained on generic wikipedia text samples), and two recurrent neural networks (RNNs) using food.com training data sets and an additional word2vec embedding. 

### Topic Analysis
We present preliminary results of n-gram topic modelling to predict useful recipe tips from user-generated comments on the Salted Tahini Cookies recipe.
