# NYT Collaborative Cooking with NLP

Contributors: Shirley Li, Anila Yadavalli, Nida Obatake, and Enkhzaya Enkhtaivan.

Project completed as part of the May 2021 Data Science Boot Camp hosted by The Erdos Institute. 

## Project

We love finding online recipes for cooking and baking. Often the recipe comments section has invaluable information for the home cook who isn't using commercial grade test kitchens and equipment. For example, for making [Simple Crusty Bread]([url](https://cooking.nytimes.com/recipes/1018203-simple-crusty-bread)), you can make do without fancy equipment: "if you don't have a pizza stone, just use parchment paper and put your oven on the convection setting." 

We started with an ambitious question: how can we find and collate the most useful comments on recipes? The comments section is usually sorted by date (oldest or newest comments) or by likes (which is also biased by date; older comments who get likes will be more likely to float to the top and get more likes). Could we use NLP techniques to identify the most common topics and advice?

We trimmed our project idea down to a simpler exploratory form:
1. We scraped the New York Times "[Salted Tahini Chocolate Chip Cookies]([url](https://cooking.nytimes.com/recipes/1018055-salted-tahini-chocolate-chip-cookies))" recipe comments.
2. We performed sentiment analysis and topic modelling to determine the best tips for recipes. 

## Data
We used the NYTAPI to scrape 355 comments from the "[Salted Tahini Chocolate Chip Cookies]([url](https://cooking.nytimes.com/recipes/1018055-salted-tahini-chocolate-chip-cookies))" recipe. The recipe comments section included the columns below and many more:
- 'commentID'
- 'status'
- 'userDisplayName'
- 'commentTitle'
- 'commentBody'
- 'recipe_id'
- 'recipe_name'

We kept the columns 'userDisplayName' and 'commentBody' and dropped the other columns. 

We also experimented with BeautifulSoup and requests to scrape the comments section from more recipes. But since we were all relatively new to coding and data science, we decided to limit the scope of our project to just one recipe. 

## Sentiment Analysis
After text preprocessing and cleanup, we created multiple sentiment analyzers for the unlabelled comments on the Salted Tahini Cookie Recipe:
- We built our own sentiment analyzer. We took each Salted Tahini Cookie Recipe comment and converted it into a word vector using gensim's doc2vec embedding (trained on generic wikipedia text samples). Then we took food.com recipe comments (with star ratings), converted these using gensim's doc2vec embedding, and trained a logistic regression on these food.com recipe comments. Then we applied this model to the Salted Tahini Cookie Recipe comments.
- We used the basic NLTK Vader sentiment analyzer to derive a compound sentiment score for each comment.
- We also built an RNN to classify sentiment. Again, we used food.com recipe comments as our training data set, and then we applied this model to the Salted Tahini Cookie Recipe comments. We hand labelled the sentiment on Salted Tahini Cookie Recipe comments to get the accuracy.

## Topic Analysis
We present preliminary results of n-gram topic modelling to predict useful recipe tips from user-generated comments on the Salted Tahini Cookies recipe. Below, see the most common trigrams and fourgrams in the comments.

![Untitled-1](https://github.com/neeedz/collaborative-cooking-with-nlp/assets/81717153/67d97d79-dd9f-418b-8585-654e5b0295fd)

![Untitled](https://github.com/neeedz/collaborative-cooking-with-nlp/assets/81717153/3a6957d8-6b2e-48b5-85d5-dcfa5d79559d)
