In the following we present two project ideas. Since the second idea is a bit ambitious and we have a lot of uncertainty about whether we would be able to realize it we also included a more reasonable idea which is idea 1. If you read and grade just one idea please grade idea 1. If you are willing to look at both ideas that would be great.

# Idea 1

## Title:
Testing BFS sampling approach as a generation method of representative samples

## Abstract: 
The authors of the paper claim that the BFS sampling approach could not generate representative samples. Our aim is to verify this assertion. Hence, we are going construct a new dataset, then validate its representativeness using Kolmogorov-Smirnov test as the authors in the paper, and finally repeat some investigations made by the Hai L. et al. In order to generate the dataset we will randomly generate some Twitter IDs and check if there exists a corresponding Twitter user. Then we will use those egos as sources to launch BFSs. The nodes of a search graph are Twitter users while edges are both follower and followee relationships. We will generate a dataset which size will be approximately equal to the one used by the authors of the paper. Finally, using new dataset we will repeat verifications of some prepositions. 

## Research questions
1. Is the BFS sampling approach representative based on Kolmogorov-Smirnov test?
2. How many sources we need to to generate a representative dataset?
3. Are the authors' prepositions agree with the conclusions drew from our dataset?

## Proposed datasets
- Dataset generated in a way described below

## Methods
- **Dataset generation** We will try different number of sources (100-1000) for BFS and choose the best dataset using Kolmogorov-Smirnov test. To download the data we will use Twitter API

- **Verification of prepositions** We have decided to focus on one preposition from each section, i.e. "Circadian rhythms" (usage), "Dunbar’s number" (structure), and "Influential hypothesis" (information diffusion).

## Proposed timeline
- **Week 1:** Dataset generation
- **Week 2:** Verification of chosen prepositions
- **Week 3:** Prepare report and a short video

## Organisation within the team:
- Viktor will find out how to get an access to Twitter API
- Maciek will write BFS and the setup for fetching data using Twitter API
- Maciek will clean the data and verify two prepositions (usage and structure)
- Viktor will verify the third preposition (information diffusion)
- Maciek will organise and clean the code, and work on making a data story notebook
- Viktor will prepare video

## Questions to TA:
- Is it ambitious enough?
- Should we increase or reduce the number of tested prepositions?


# Idea 2

## Title:
Testing exposure hypothesis for exposure to Tweets on global warming

## Abstract: 
We propose to study the exposure hypothesis on the topic of global warming. We will train a NLP algorithm on the Kaggle “Twitter Climate Change Sentiment Dataset“ to classify Tweets about global warming in 4 categories: News) news Pro) belief in man-made climate change Neutral) neither supports nor refutes the belief of man-made climate change and Anti) doesn't believe in man-made climate change. A dataset will be built by randomly selecting accounts whose Tweets mention at least one neutral word closely related to global warming. The relation between exposure to Tweets of different categories and user's Tweets will be studied. Changes of opinions will also be examined by fitting linear models to Pro, Neutral and Anti label timeseries. Characteristics of accounts and clusteres where people change their opinions will be sought.

## Research questions
1. What is the probability of retweeting Tweets or Tweeting about global warming as a function of the number of exposures to Tweets about global warming? How do the results change for exposure to Tweets about global warming with the label News, Pro, Neutral or Anti ? How do the results change for probability of retweeting Tweets with the labels News, Pro, Neutral or Anti ?
2. What are the characteristics of accounts and clusteres where people change their opinions ? Can causality be established between these characteristics or is it mere correlations ?

## Proposed datasets
-	Testing Propositions Derived from Twitter Studies dataset from the paper for comparing our results (if replicating figure 6 is too time consuming we could skip this part and use a screenshot for comparing results).
-	Build a dataset of users Tweeting about the environment using the Twitter API (think about how much time this will take if we use randomly generated Twitter ids, if it takes too long we could employ a BFS algorithm but then the dataset would not allow generalizability)
-	Twitter Climate Change Sentiment Dataset from Kaggle, https://www.kaggle.com/edqian/twitter-climate-change-sentiment-dataset

## Methods
### NLP sentiment analysis model: 
We will do research on what model would perform well on classifying Tweets. We will consider random tree, and SVM as well as other models found in literature.
### Data collection: 
We have signed up to the Twitter API to build a dataset including the number of followees, the number of followers, a list of Tweets including words like “climate change” in some time window (up to 10 years if this is possible), a list of the dates of those Tweets, probability of retweeting Tweets with each of the labels. An obstacle to building this dataset might be the number of requests that can be made through the Twitter API (up to 3200 requests / hour).
### Data analysis: 
We are interested on how exposure to Tweets of the 4 different categories (New, Pro, Neutral, Anti) influence users to Retweet or Tweet messages of different categories. We might be able to do dimensionality reduction to isolate important effects.
Time series analysis: The labels of a user’s Tweets in time define a time series. We could imagine keeping only the labels corresponding to the categories Pro and Anti and fitting a linear model. We will refer to this time series as the “opinion time series”. The slope thus obtained would be a good proxy for change of opinion. We could then study what causes users to change their opinions. Is it the characteristics of the cluster they are part of? Or is it their individual properties that cause them to change their mind? We will have to think about how we can infer causality instead of just correlation.

We realize that this project proposal is full of wild ideas. We are prepared to discover that the data does not allow to realize some of these ideas. We will clarify what we do as we explore the data.

## Proposed timeline
- **Week 1:** One of us will build the dataset and the other will train the NLP model.
- **Week 2:** We will work together on plotting the probability of Tweet/Retweet of a certain category as a function to exposure to difference categories of Tweet.
- **Week 3:** Explore interesting data analysis opportunities, preparing the data story and short video.

## Organisation within the team:
-	Viktor will work on building the dataset using the Twitter API and Maciek will train a NLP model for the classification task using the Kaggle dataset
-	Viktor will work on making plots similar to figure 6 in the paper and Maciek will explore the possibilities of data analysis using the opinion time series
-	Viktor will work on making the video while Maciek will work on making a data story notebook

## Questions to TA:
- Is this project too ambitious?
- Do you think the number of requests limit on the Twitter API is going to be a problem if we want to build a large enough dataset ? Should we use BFS instead of randomly generating Tweeter ids ?
