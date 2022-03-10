# Project 3: Web APIs & NLP
---


## Executive Summary 

The objective is to pick two subreddits from Reddit and train a machine learning models to classify posts into the correct subreddit.

I have identified r/aliens and r/conspiracytheories as two subreddits of choice as they share some similarities, but are also different in a few ways.One of the goals would be to balance the credibility of aliens' existence with conspiracy theories revolving around aliens.


#### Conspiracy theories around aliens

Conspiracy theory is the belief that some covert but influential organization is responsible for an unexplained event. Some examples of conspiracy theories are 

Humans have been looking for extraterrestrial existence for the longest time with multiple reports on strange sightings and even setting up programs or facilities to look into these UFO sightings. For Example: Area 51 in Nevada and Project BLUE BOOK.

Some examples of conspiracy theories regarding aliens are:

1) Various governments and politicians globally, in particular the Government of the United States, are suppressing evidence that unidentified flying objects are controlled by a non-human intelligence or built using alien technology.


Conspiracy theory 

---

## Approach 

#### 1) Data Gathering 

Using Pushshift's reddit API, I was able to collect close to 10,000 posts from both subreddits. Afterwhich, the data went through cleaning and preprocessing before modelling. 


#### 2) Data Cleaning and EDA, Preprocessing

Here are the following steps taken to clean and manipulate the data

1) Check for duplicate posts

2) Replace selftext null values with NA

3) Check for overlap postings between two sub reddits 

4) Merged title and selftext column to form merged column 

5) Apply lowercase to merged column 

6) remove stopwords, add additional stopwords to stopwords list

7) remove links 

8) convert emojis to words

9) Stemming 

10) Count Vectorize words to single words or bigrams 

#### 3) Modelling process 
First, check the baseline score.

Then, I did the modelling process with three models on default parameters to find the accuracy score - Logisitic Regression, Naive Bayes, Random Forest Classifer.

Afterwhich, I have decided to tune the hyperparameters for both countvectorizer and tf-idf vectorizer for logistic regression, Naive Bayes and Random Forest Classifer to improve the accuracy score and f1 score for logistic regression. This time, looking at the f1 score with the two metrics recall and precision.

After hypertuning the parameters, the best performing model was the Logistic Regression model with TF-IDF vectorizer.
It had the highest f1-score amongst other models. but the model was still overfitted with the training  set performing better than the test set with an f1 score of 0.865 and an sccuracy score of 0.864


#### Evaluation 

Next, to improve my score, I will have to improve some of my preprocessing and spend more time on hypertuning the random forest classifier. Looking more closely towards the parameters to determine which parameters to use. More time can also be spent exploring adding more stop_words to my list, testing with various methods of stemming and other classification models( e.g. SVM). 

A quick observation in the models that I have created was that all the models that I have created were overfitted where the training set performed much better than the testing set. To improve next, I can look up on methods in which I can address the overfitted problem. 



