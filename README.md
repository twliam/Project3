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


### Conclusions and Recommendations

Recommendations for agents to identify higher value houses:
1. Location is important, as always. houses in good neighborhoods sell for more. 
2. Use built-up size as a gauge rather than total lot size. Having more livable area above ground or a larger garage seems to impact selling price more than just how big the lot area is.
3. Look out for the overall quality of materials and finishing of a house.  

Recommendations to increase house value before listing:
1. Improving the overall quality of the house just prior to selling might be feasible, as finishings such as painting, flooring, plastering or minor woodwork can be done on short notice.
2. Upgrading your kitchen is another viable option.
3. Some of the stronger factors that impact sale prices (built-up area, garage size) may be costly and time consuming to pursue. May not be worth your while.

### Future Direction
Track if the use of the insights above help agents not just in fair valuation and increasing value of properties but also in closing their clients as well. In some instances, selling price is not the only target. Closing is as important.

### Data
Two datasets,`train` and `test`, are obtained from the Ames Assessor's Office and provided for analysis and modelling. Both datasets are a record of sales for residential properties sold in Ames, Iowa from 2006 to 2010.
* [`train.csv`](./data/train.csv): Contains both features and target
* [`test.csv`](./data/test.csv): Contains only the features without target
