# NLP Sentiment Analysis

Natural Language Processing is a machine learning tool used to work with text data. NLP is a subfield of linguistics, computer science and artificial intelligence used for computers to interact with human language.  NLP is a significant part of machine learning projects. Some of the more common uses people see in everyday life include using Siri or Alexa, or movie and music recommendation systems. 

## Sentiment Analysis
![](https://github.com/peimani/NLP_Sentiment_Classification/blob/main/Images/Emojis.png)

Sentiment analysis is the process of detecting positive or negative sentiment in text.[^1] When you have unstructured data it is useful to categorize these using sentiment analysis. This type of analysis allows you to assign value to texts, sentences and/or headlines. For this project I thought it useful to take financial headlines from news organizations and see if I could reduce the headlines down to a binary product. This means assigning a number to a headline to distinguish it as a negative, positive, or neutral headline. This was done to be a basis of exploring further headlines and their relations to stock performance. Would it be possible to see how much headlines affect the price of a stock?

# Data & Text Cleaning

To begin this journey took a database of headlines from Kaggle [(DataSet)](https://www.kaggle.com/ankurzing/sentiment-analysis-for-financial-news?select=all-data.csv).    This was a dataset that consisted of two columns, 4837 headlines and a column which categorized them as neutral, negative, or positive.  The sentiment column was transformed to 0, 1, and 2 for positive, neutral, and negative respectively.  The headlines column consisted of text/headlines from various sources.  To clean this data I found it necessary to do things such as remove punctuation marks and symbols and marks associated with web pages.  Also, I found it useful to simplify words to their more simple form.  Words like 'clapping', 'claps', 'clapper', to 'clap', thereby allowing for the neural network to treat the words the same and make it easier to run the model.  This process, known as Lemmatization made the headlines almost seam nonsensical but it made better sense for the neural network model. I also used a 'stopwords' function to remove words that do not contain any unique information such as 'is', 'an', and 'the'.
![](https://github.com/peimani/NLP_Sentiment_Classification/blob/main/Images/DataGraph.png)

# Exploratory Data Analysis

To explore this dataset I made word clouds and to see which words were seen more. These word clouds were made from the negative and positive sentiment categories separately. While this did not look to show us many obvious differences between the categories, our neural network will be able to learn from these words. I also added a function to count how many words which I found helpful to tokenize the text for processing. 


# Neural Network Model

Before running the models a train test split of 80/20 was set up tokenized and transformed to a numpy array for the neural network to read.
The first I used was the Hidden Layer embedding model. I set the embedding dimensions to 32, which means we have 32 vectors. This model gave me an accuracy of 60.5% which is better than a coin flip but can be improved. Then we ran our own headlines to see what kind of results we could get. For the easier headlines it was able to categorize the positive and negative headline but not the neutral. For the Realistic or more difficult headlines it was only able to categorize the positive headline. 
Plotting the value loss, value accuracy, loss and accuracy we are able to track the epochs. It looks like the validation was not improving so the early stopping mechanism stopped the model. This may have prevented the validation loss from getting larger.


There will be further work to do on this to improve accuracy. Once the accuracy improves it would be nice to scrape headlines from the web and run it for sentiment classification.
I would also like to cross reference the sentiment classifications with stock prices to see if there is any positive correlation with the two variables. This may help in finding if headlines affect purchases and sell offs of the stocks that are talked about.

# Conclusion

This was an interesting challenge. It is fascinating that a computer model can read human language and be able to assign a sentiment to it. An example would be reading amazon reviews and classifying them for research purposes. While this model needs work to make it more accurate, it is possible to have the machine become more accurate in its reading. This artificial intelligence helps to connect man and machine even more naturally. As voice recognition software becomes more common so will the application of natural language processing. I look forward to seeing the possibilities.
Actionable Recommendations:
1. Sentiment Analysis allows for correlation analysis with stock prices and can also be used to see how customers feel about a product.
2. 


## Refrences:
[^1]: https://monkeylearn.com/sentiment-analysis/
