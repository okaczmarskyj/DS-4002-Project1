## tweets.csv from https://www.kaggle.com/datasets/benhamner/clinton-trump-tweets
#### This dataset is too large to upload to GitHub

### Obtaining the Dataset Process
This dataset was downloaded from Kaggle, originally with 28 columns. Each row of the dataset represents one tweet and each column provides information about the tweet such as who posted it, when it was posted, how many favorites it received, and more. These are tweets posted by Hillary Clinton and Donald Trump during the 2016 U.S. presidential election campaign. This dataset was uploaded to R Studio for cleaning and analysis.\
\
The goal of this research is to determine whether the sentiment of a tweet has an impact on the amount of favorites it receives so, with this goal in mind, we selected only handle, text, is_retweet, and favorite_count as the relevant columns, removing the others from the dataset (an explanation of the data included in each column can be found in the README file).\
\
Tweets that were not originally created by the two presidential candidates are not relevant to our topic as we are only interested in how the statistics vary between each candidate's original content. For this reason, the dataset was filtered to only include rows (tweets) that had the value "FALSE" in the is_retweet column, indicating that the tweet was not a posted retweet but was created by one of the candidates.\
\
The text of the tweets all had a hyperlink at the end of the tweet's content, beginning with "https://", which would not be relevant to our sentiment analysis. These links were removed from the text.\
\
In order to conduct a sentiment analysis on the text of the tweets, the text of each tweet was divided into sentences so each sentence's sentiment could be individually analyzed. To do this, the get_sentences() function in the "sentimentr" package was used and a new column, "sentences" was created containing lists of the sentences in each tweet.\
\
Finally, positive, neutral, and negative bins for sentiment were created labeling a sentiment score of greater than 0.05 as positive, less than -0.05 as negative, and between -0.05 and 0.05 as neutral.
