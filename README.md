# Sentiment-Analysis-on-Twitter.com
INTRODUCTION
In this study case, we are going to analyze what people are posting on Twitter regarding to a
new released (since Nov 3, 2017) mobile phone iPhone X to help the company Apple Inc to find
out how its customers react with iPhone X so far – positive or negative.
Social media is not just a platform where people chat with each other, but also it serves vast
purposes. It is a medium through which people can express their interests, share their views or
their displeasures, compliment companies for good and poor services, etc.
Twitter, published in 2006, is one of the most popular social media platforms. The service
rapidly gained worldwide popularity. In 2012, more than 100 million users posted 340 million
tweets a day, and the service handled an average of 1.6 billion search queries per day. In 2013,
it was one of the ten most-visited websites and has been described as "the SMS of the Internet".
As of 2016, Twitter had more than 319 million monthly active users. Twitter allows users to
post multimedia content in a short-form message known as "tweets". People usually express
their emotions and sentiments about a brand, a product/service, news or an event in these
tweets. Tweets were originally restricted to 140 characters, but on Nov 7, 2017, this limit was
doubled for all languages except Japanese, Korean, and Chinese.
By text mining these tweets, we can find the terms that are most commonly used in the tweets
and how it affects the related business reputation. We can analyze each term in the tweet and
find out which other terms are strongly related to. By doing so, we can estimate what
function/content the public likes (positive factors) or dislikes (negative factors) with a specific
product, which may help the company to adjust promotion, function or even business strategy.
Using Sentiment Analysis, we can build models on the existing tweets and be able to predict the
new tweets as good or bad. Product developers can use this analysis to improve the quality of
the products (e.g. iPhones in this case study) to meet the expectations of the general customers
and to generate maximum revenue.

CHALLENGES
The first challenge is to understand and analyze slangs in the tweets. People use a lot of slangs
which are not proper English words but are used in informal conversations. And these slangs
are changing and growing. A lot of researches have introduced methods to develop slang
dictionaries to understand their meanings. In this case study, we will not focus on this part; we
will use the standard dictionaries and packages available in Python for Sentiment Analysis.
The next problem is how to automatically collect a data corpus for Sentiment Analysis and
Opinion Mining.
And then, various hashtags for the same topic on Twitter are observable. This would make it
challenging to separate all tweets on the subject. But in this case study, we will only restrict to
single hashtag #iPhoneX.
A lot of tweets do not contain a hashtag. Those tweets may be also highly relevant to the
targeted product but missed to analyze due to the lack of hashtags.
This study also does not consider the content of pictures, videos, links and other social media
reports which could have generated additional insights.
The last and the biggest problem in Sentiment Analysis is decoding sarcasm. Since Sentiment
Analysis works on the semantics of words, it becomes difficult to decode if the tweet contains
sarcasm. Sentiment Analysis traditionally focuses on classifying tweets into positive, neutral and
negative categories. But an intelligent and flexible opinion mining system should develop a
deeper analysis of affective knowledge and detecting richer emotions. An ontology driven
approach was researched to extract rich emotional semantics of tagged texts, by combining
available computational and sentiment lexicons with ontology of emotional categories. And
there was another similar approach to detect the emotions in tweets: taxonomy of emotions
can drive the selection of hashtags for the automatic search of tweets with a prevalent
sentiment. Such tweets can be used in the training phase of an automatic classifier. But these
methods are still not really accurate to sentiment analyze sarcasm. Including sarcasm, there are
some other typical problems of Sentiment Analysis such as irony, implication, lack of
information, quotes of songs/poems, idiomatic expressions, abbreviated forms, etc. In this case
study, we will not go that deeper to decode such forms.
SENTIMENT ANALYSIS IN PYTHON
As SAS is not the best software for Sentiment Analysis, we choose to use Python NLTK (Natural
Language Toolkit), which is a suite of libraries and programs for symbolic and statistical natural 

language processing (NLP) for English written in the Python programming language. As required,
we restrict to collect only 200 tweets with single hashtag #iPhoneX. By sentiment analyzing
these tweets, we target to count positive/negative words to provide an overall sentiment of
each tweet.
First of all, to prepare the dataset for Sentiment Analysis, we extract 200 most recent tweets
about iPhone X from Twitter by looking for the hashtag #iPhoneX via tool Tweepy. Tweepy is an
easy-to-use Python library for accessing the Twitter API.
Next, we build a table of tweets.
Then we get below first 10 elements of this table.
Then we import Textblob to do sentiment analysis. Textblob is a Python library for processing
textual data. It provides a simple API for diving into common natural language processing (NLP)
tasks. We also import the re library from Python, which is used to work with regular expressions.
For this, we implement data cleaning to extract only useful text from each tweet and put it into
sentiment analysis to classify sentiment (positive, neutral or negative). The tweets are parsed
into a corpus for text analysis. We only consider the text portion of the tweet. So to prepare it
for further analysis, we clean the corpus by removing numbers, removing URLs & links,
removing stop words (e.g. the, for, this, I, me, you, a), removing non-English words,
tokenization &stemming words (through NLTK library, to create a frequency distribution of the
words), suffix-dropping algorithm, lemmatization algorithms, removing punctuations, stripping 

whitespace, etc. Then, we create a classifier to analyze the polarity of each tweet after cleaning
the text in it.
After then, we add an extra column to our data. This column contains the sentiment analysis
and we can plot the dataframe to see the update. As below screen capture shows, column “SA”
represents the computed sentiment analysis score for each tweet. Its value 1 means positive, 0
means neutral and -1 means negative.
Lastly, we segregate these tweets into positive, neutral and negative categories. To do so, we
count the number of positive, neutral and negative tweets and compute the percentages. As
below screen capture shows, we obtain following results of sentiment analysis: 45.5% of these
200 iPhone X related tweets are positive, 46.5% of them are neutral and only 8% of them are

X by Apple Inc so far. So iPhone X is a successful and popular product in recent mobile phone
field.
CONCLUSION
 By sentiment analyzing tweets from Twitter, we can find out what people like and dislike
with the existing product(s).
 It is difficult to survey customers who didn't buy our product. But via Sentiment Analysis, we
can search the web for opinions and reviews of this product and competing with other
similar products in the market.
 Via Sentiment Analysis, we can also find out what people expect from a product. Then the
developers can use these results to come up with new enhancements/products that can
satisfy and reach the expectations of the customers.
 This study case only collects most recent 200 tweets related to iPhone X. To make the
analysis result more accurate, more tweets and even more posts from other popular social
platforms such as Facebook, Instagram, Soup, Tumblr and YouTube should be considered to
analyze.
 In this case study, we just simply group the tweets into positive, neutral and negative
categories. For a deeper analysis, it can rank the attitude from scale 1 to 5 or even group
into more complex attitude types.
 A far greater extent especially like images and videos is also worthy to be invested and
further researched for sentiment analyzing.
 Insights and applications from Sentiment Analysis have been also useful in other areas, such
as politics/political science (e.g. to predict election outcomes or market trends from
sentiment), law/policy making, sociology and psychology.
 The power of social media will continue to be researched, more and newer applications and
methods will continue to be built to harness its power in a deeper manner.

REFERENCE
 Social Network Analysis: Methods and Applications by Stanley Wasserman, Katherine Faust
(1999)
 Twitter Introduction by Wikipedia
https://en.wikipedia.org/wiki/Twitter
 Sentiment analysis on Trump's tweets using Python, by Rodolfo Ferro
https://dev.to/rodolfoferro/sentiment-analysis-on-trumpss-tweets-using-python-
 Tapping Twitter Sentiments: A Complete Case-Study on 2015 Chennai Floods
https://www.analyticsvidhya.com/blog/2016/07/capstone-project/
 Sentiment analysis for Yelp review classification
https://medium.com/tensorist/classifying-yelp-reviews-using-nltk-and-scikit-learnc58e71e962d9
 Tutorial: Building a Text Classification System- TextBlob
https://textblob.readthedocs.io/en/dev/classifiers.html
 Natural Language Processing and Sentiment Analysis with Python
http://pythonforengineers.com/natural-language-processing-and-sentiment-analysis-withpython/
 Sentiment Analysis Intro, by Stanford University
https://web.stanford.edu/class/cs124/lec/sentiment.pdf
