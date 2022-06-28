# Unit 12: Natural Language Processing

![Stock Sentiment](Images/sentimental.jpeg)

## Background

In this assignment, I apply natural language processing to understand the sentiment in the recent news articles featuring Bitcoin and Ethereum. I apply fundamental NLP techniques to better understand the other factors involved with the coin prices such as common words and phrases and organizations and entities mentioned in the articles.

Objectives:

1. [Sentiment Analysis](#1---Sentiment-Analysis)
2. [Natural Language Processing](#2---Natural-Language-Processing)
3. [Named Entity Recognition](#3---Named-Entity-Recognition)

---

## Files

[My Solution](crypto_sentiment.ipynb)

---

## Installations

```
conda activate base
conda create -n nlpenv python=3.7 -y
conda activate nlpenv 
conda install -c anaconda nltk -y
yes | pip install wordcloud
yes | pip install newsapi-python==0.2.5
yes | pip install -U spacy
yes | python -m spacy download en_core_web_sm
yes | pip install alpaca-trade-api
yes | pip install python-dotenv
conda install -c conda-forge python-dotenv
sudo python -m nltk.downloader -d /usr/local/share/nltk_data all
pip install jupyterlab_sublime
```

### 1 - Sentiment Analysis

Using the [newsapi](https://newsapi.org/), I pull the latest news articles for Bitcoin and Ethereum and create a DataFrame of sentiment scores for each coin.

Using descriptive statistics, I address the following questions:

> Which coin had the highest mean positive score?
>
> Which coin had the highest negative score?
>
> Which coin had the highest positive score?



### 2 - Natural Language Processing

In this section, I use NLTK and Python to tokenize text, find n-gram counts, and create word clouds for both coins. 

#### Tokenize

1. Lowercase each word.
2. Remove punctuation.
3. Remove stop words.

#### N-grams

Next, I look at the ngrams and word frequency for each coin.

1. Use NLTK to produce the ngrams for N = 2.
2. List the top 10 words for each coin.

#### Word Clouds

Finally, I generate word clouds for each coin to summarize the news for each coin.

![btc-word-cloud.png](Images/btc-word-cloud.png)

![eth-word-cloud.png](Images/eth-word-cloud.png)


### 3 - Named Entity Recognition

In this section, I build a named entity recognition model for both coins and visualize the tags using SpaCy.

![btc-ner.png](Images/btc-ner.png)

![eth-ner.png](Images/eth-ner.png)

### Resources

[Vader Sentiment Analysis](http://www.nltk.org/howto/sentiment.html)

### Considerations

The free developer version of the News API limits the total daily requests, so repeated API calls during testing should be limited.