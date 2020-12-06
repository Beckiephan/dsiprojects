# Project 3 Subreddits Classification - r/netflix vs r/hulu

## Problem Statement
Working as a data scientist in Netflix, I am tasked to help the content team to identify what are some of the series or films that our audience seems to be interested in to maintain customer satisfaction. Looking at what the Netflix users and Hulu users are posting about on Reddit could help to give an idea as to what content Netflix could continue or should start to produce or acquire.

## Executive Summary
What Netflix contents are doing great and which ones needs improvement? This is the big question we are trying to answer.

In this project, I will look at 2 subreddit posts, [r/Netflix](https://www.reddit.com/r/netflix/) and one of Netflix's competitors [r/Hulu](https://www.reddit.com/r/Hulu/). Netflix and Hulu are very similar in that sense they are both streaming platforms for shows. To answer the question above, I will have to look past the similarities and find the differences which are the titles to the different shows they house in their libraries. Using these show titles, I can then find out which contents Netflix and Hulu are known for and tackle the question above.

To look at the top different posts in each subreddit, I have developed a classification model to predict which subreddit some unseen posts belongs to. Models were evaluated and finally the final model selected was the Multinomial Naive Bayes classifier predicting base on 2 word ranges. This model has an accuracy of 66% which is acceptable considering how similar these 2 subreddits are. The misclassifications especially for Netflix is due to the smaller proportion of posts collected from the subreddit compared to Hulu. We can look to improve the model accuracy by scraping more posts for Netflix.

Based on the classification and EDA of film/series titles based on the top words predicted to occur in each subreddits, Netflix does well in what they are known for which is their original series but can improve on the Anime genre which Hulu seems to thrive on.

### Contents:
- [Data Dictionary](#Data-Dictionary)
- [Data Collection](#Data-Collection)
- [Data Cleaning & EDA](#Data-Cleaning-&-EDA)
- [Preprocessing & Modeling](#Preprocessing-&-Modeling)
- [Model Evaluation](#Model-Evaluation)
- [Conclusion and Recommendation](#Conclusion-and-Recommendation)

#### Data Dictionary
|Feature|Type|Dataset|<div style="text-align: left">Data</div>|<div style="text-align: left">Description</div>|
|---|---|---|---|---|
|<div style="text-align: left">**all_words**</div>|<div style="text-align: left">*object*</div>|<div style="text-align: left">posts_df</div>|<div style="text-align: left">Combined title and selftext</div>|<div style="text-align: left">Each individual posts, which consists of the title and selftext, from the subreddits of r/netflix and r/hulu</div>|
|<div style="text-align: left">**target**</div>|<div style="text-align: left">*integer*</div>|<div style="text-align: left">posts_df</div>|<div style="text-align: left">0 = r/Hulu<br>1 = r/netflix</div>|<div style="text-align: left">Target variable to identify which subreddit the post belongs to</div>|
|<div style="text-align: left">**length_all_words**</div>|<div style="text-align: left">*integer*</div>|<div style="text-align: left">posts_df</div>|<div style="text-align: left">range 1 to 579</div>|<div style="text-align: left">The number of words in each posts(length of each posts)</div>|

## Conclusions
The final model (model 1) was able to classify the unseen posts into the 2 classes, r/netflix and r/hulu, with an acceptible accuracy of 66%. This shows that the 2 subreddits are quite different but still with some similarities, which is expected since both of these subreddits are about streaming platforms for shows. Even with many similarities the model was able to classify accurately 66% of the time which is better than the basline accuracy of 60%, the reason for this may be that they have many different shows which targets different audiences.

Netflix is known for their original series and this is supported based on the findings as one of the top words are "original series". Netflix is also know to have an extensive library for different genres, based on the top words, there are many shows titles that appear in the top words to support this. For example, we see that r/netflix top words comprise of "Queen Gambit" and "Crown" which are historical dramas and they are netflix original series. Other top words are "umbrella academy" - science fiction, "rick morty" - adult comedy, "narcos mexico" - crime drama, "hill house" and "stranger things" - supernatural/thriller/horror and "social dilemma" - documentary.

As for Hulu, based on the top words like "naruto shippuden", "hero academia" and "anime recommendation", seems to have a wide range of anime, and the consumers seem to be very interested in it. This is one genre in which netflix is lacking in which we could improve on. [anime](https://www.quora.com/Which-has-better-anime-Hulu-or-Netflix)

Netflix should continue producing more original series since they are one of the most popular contents base on our findings. Netflix has a good range of genres to keep customers satisfied, but one thing we could do to increase our customer base is to acquire the rights to more anime shows. Acquiring the rights to shows are never easy and there are many considerations like costs, and as we are well aware that the cost to buy the rights to air the show in different geographical locations differs, we should then do some research into the cost and reward for airing them is different countries. [Investopedia](https://www.investopedia.com/articles/investing/050515/why-netflix-content-different-other-countries.asp#:~:text=Studios%20enforce%20copyright%20by%20country,different%20demands%20for%20specific%20content.&text=Because%20the%20content%20deals%20are,in%20other%20regions%20fall%20flat.)

The model has a lot of room for improvements, especially in classifying for the r/netflix posts. The model shows great performance in classifying words into r/hulu correctly but many misclassifications happens when trying to classify the words from r/netflix. This may be due to the smaller proportion of posts scraped from r/netflix compared to r/hulu. The model can therefore be improved by increasing the corpus size to hold more posts from r/netflix. This means having to find ways to scrape more posts from r/netflix.

This model can also be used to improve product development in most companies, by looking at customer's feedback or even just comments to see what are the products that are most popular. This is a continuous process as people's taste change and there are always new products being developed all the time.
