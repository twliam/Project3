# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 3: Web APIs & NLP

### Liam Ting Wei, SG-DSI33

### Problem Statement
This project aims to build a model with >90% accuracy that helps to identify between those who are looking for bootcamp style learning vs computer science majors/prospective students based on the words they use online.
In addition, important trends and keywords should be picked up and explored as part of the analysis.

### Background
General Assembly is feeling the heat with more and more coding bootcamps popping up over the years. As an industry leader, the organization would like to keep its position and the marketing team is thus interested in streamlining and raising the effectiveness of its digital advertising efforts. They have as such, roped the data team in to provide some insights.

The starting point of most digital advertising strategies is finding the right keywords. While keywords such as 'bootcamps' and 'coding' are immediately apparent, being able to identify other less obvious ones are important here as well. Keywords that can help to differentiate similar groups of online personas into potential leads and less likely ones are appreciated.
Taking this into account and adding on the rise of social media (see [ourworldindata](https://ourworldindata.org/rise-of-social-media)) and its place in the advertising space, your team has decided to gather data from Reddit due to its uniqueness - it is a social media platform done in a forum style. Reddit contains a large amount of subreddits, which are essentially communities within the platform. According to Reddit themselves, 'there's a community for everybody'.
Each subreddit contains posts that are relevant to its topic. These features make Reddit a trove of social media-like text posts and therefore an ideal scraping candidate. 

### Summary
A total of approximately 10000 posts were scraped from r/codingbootcamp and r/csMajors, extracting almost 5000 posts per subreddit. This was done via request from the PushShift API.
The datasets were then preprocessed for NLP. Several models were then built using a combination of vectorizers (CountVectorizer and TF-IDF) and classifiers (Naive Bayes, Logistic Regression, Random Forest)
Models were then trained and evaluated for accuracy. ROC AUC was also used as a supplementary metric for evaluation.
Logistic Regression with TF-IDF Vectorizer (n-gram range (1,2)) was found to be the best performing model.

### Data
Two datasets,`codingbootcamp_submissions` and `csmajors_submissions` containing posts from the subreddits r/codingbootcamp and r/csMajors respectively were obtained by scraping popular community aggreggator site Reddit.com using the PushShift API.
* [`codingbootcamp_submissions.csv`](./data/codingbootcamp_submissions.csv): r/codingbootcamp submissions
* [`csmajors_submissions.csv`](./data/csmajors_submissions.csv): r/csmajors submissions

## Data Dictionary
|Feature|Type|Description|
|:---|---:|---:|
|subreddit|str|Name of Subreddit post belongs to|
|title|str|Title of post|
|created_utc|int|Timestamp of post creation|
|selftext|str|Content of post|
|all_text|str|Title and content of post combined|
|all_text_clean|str|Combined title and content that has been processed|

### Conclusions and Recommendations
Key Takeaaways:
1. Logistic Regression using TF-IDF vectorizer and an n-gram range of (1,2) was the best performing model.
2. The production model is capable of predicting if a post belongs in to an accuracy of 92%, surpassing the 90% goal.
3. Top keywords relating to coding bootcamps are names of bootcamp providers and programming languages. The focus seems to be more on learning as well, as opposed to job-centric keywords related to the computer science major.

Recommendations to increase house value before listing:
1. Keyword findings from the exploratory data analysis and interpretation of the production model's coefficients should be used to guide advertising strategy and content.
2. The produtction model in its current form may be used to identify if a person is a worthwhile advertising target based on his/her online posts.
3. Names of competitors appear to be useful keywords to identify if searchers are potential bootcamp enrollers.

### Future Direction
The model in its current form is able to perform relatively well when it comes to predicting if a post should be classified as coming from someone interested in coding bootcamps or a computer science major, and by extension, able to identify said interest based on new posts. More subreddits could be added to increase its versatility in discerning other similar topics as well. 

At present, the model is only trained on data scraped from Reddit and while expected to generalize well across multiple social media platforms, it should be even more so if further trained on data from other sites. More formal texts could also be parsed through the model to identify keywords from a different perspective and for a different marketing angle.

Finally, the model could be deployed on a larger scale, continuously sorting through posts on popular platforms to find potential customers.

