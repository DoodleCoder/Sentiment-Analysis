# Sentiment Analysis 
[Kaggle Challenge - Amazon Reviews](https://www.kaggle.com/PromptCloudHQ/amazon-reviews-unlocked-mobile-phones): A task 
to identify the polarity of mobile phone reviews posted on Amazon. 

## Objective
Comparison of custom trained **Gensim** embedding model to pre-trained word embedding models (**Google word2vec** and **Stanford GloVe**).

## System Architecture
![Image Description](https://lh6.googleusercontent.com/tRdFAh7qY7eieR8CaRbqHAWkrzK_tFkMldRJD6jvUTbuqaigkS0jE5YgCQSxotYzIO4QcLVqHuT9wQqFGo2y_mRzBtZ0ZukHnYzOROE10ZlzKukUvKqr5MtdANyMktuoECh2bBm-)

## Working Steps
### **Data Cleaning** 
Tokenization, followed by removing stopwords, special characters and abbreviations.
### **Feature Extraction** 
Using Common Bag of Words and tf-idf values to determine feature points. 
### **Building Model** 
Building 3 different models using Gensim, Word2Vec and GloVe respectively. Words represented as one-hot-vectors
are transformed to equivalent numeric vectors of dimension size 300. Similarity between words calculated by cosine of corresponding numeric 
vectors. This is represented as follows: 
![Image Description](https://lh6.googleusercontent.com/7O2VkSBdP18g3iJbpkjiyJ_n0CEk6LdDBnYqk363u8nLOR6QP1_GshT-7eXZw8AzV9qoUOMVO9ff9ccywUWlDy-ji1TMC57DuwQQb9gkeSD2M-6e2kEGzPKSYn0rCDCs3ox9rHC5)
### **Review Vectorization** 
Each processed review is replaced with the  mean of the word-vectors and is plotted in the 
word-vector space.
### **Prediction** 
The reviews are then categorized using RandomForestClassifier into good(1), neutral(0) and bad(-1). These were tested against the 
actual class values provided in the dataset.

## Results
![Image Description](http://gkataria.freevar.com/ChauthaKaam/results.png)
* Google Word2Vec : **80.35 %**
* Stanford GloVe : **80.03 %**
* Gensim Word2Vec : **83.26 %**
