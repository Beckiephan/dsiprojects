# Capstone Project Instacart Enhance Business Process - Multiclass Classification

## Problem Statement
Instacart being a grocery delivery and pick-up service, offers its services through the website and mobile app. Being an e-commerce business especially now, during the Covid period, it is important to maintain user experience and ease in finding products on their online store. As a data analyst with Instacart, it has come to our attention that there are quite a lot of missing information of which department and aisles a product belongs to. As products are categorized into departments, users could search for products by departments. With missing departments, those products would not appear if users were to search by department. To solve this problem, we will build a model that would automatically take the product name and map them to their most likely department which would ensure all items are mapped to their most closely related department. This would not only ease users search for items and prevent any omission of products if users search by departments, which may result in higher sales as well, it would give a more complete and organized inventory and help make reporting more efficient, complete and accurate, for example, reporting the department-wise sales.

## Executive Summary
The goal is to help find solutions using data to predict which product goes to which department automatically. This would help not only more efficient inventory management, it would also help reporting to be more efficient and accurate by preventing any ommission of data. For example, when looking at the department-wise revenue.

The data gathered for this project is from [Kaggle](https://www.kaggle.com/c/instacart-market-basket-analysis/data). The data is from an American company that operates a grocery delivery and pick-up service in the United States and Canada and consists of:
* All the Product Name and ID
* Aisle Name and ID corresponding to its product
* Department Name and ID corresponding to its product

The data from the 3 sets mentioned above were cleaned and combined together to form the full dataset called "products_df" for more EDA and analysis and ultimately modelling.

From the vast data collection, missing departments and aisles were found for some products. Since Instacart is known for their e-commerce business, this could mean that users who were to search by department for products to buy, may never get the opportunity to see these products as one of their choices, which would then affect sales on these products. This is assuming that these data would feed into the algorithm of their website and mobile app. Building a model that would map the product to its department automatically and as accurately as possible, might improve user experience and sales. The target variable "department" was chosen as the product names in each aisle were too similar, which is a limitation to help in accurate predictions.

The product name was used as features to predict which department a product would be in. They were preprocessed, extracted to form the vocabulary and fitted into the model.

Preprocessing steps:
* Removal of stop words
* Removal of punctuations and special characters
* Lemmatization
* Train_test_split

Gridsearching was done with a combination of feature extraction steps:
* CountVectorizer
* TfifdVectorizer
* Doc2Vec

and modeling:
* Logistic Regression
* MultinomialNaiveBayes
* Transfer Learning - RNN(LSTM)

Different Vectorizers were used to see how well the model could see order and frequency and count of each word would be in the prediction of products and its departments. Logistic Regression was chosen as it was a simple and effective model which could be used as benchmark to other models. Each hyperparameters were tuned for its feature extraction and modelling steps. Gridsearch with 5 Cross-validations was done to get the best "macro-average" F1score, precision and recall. The production model was chosen by comparing the train and validation scores between models.

The production model choses what the Logistic Regression model with count vectorized features. There were about 216,000 features after vectorizing, we used the count vectorizer of max features 80,000 to fit into the model. The model may have been slightly overfitted with the train accuracy at 0.97 and test at 0.84. However it had the highest F1-score which was our main metric for measuring the performance of our models. Looking at the confusion matrix was another method for choosing the model. Most of the confusion matrix had similar results, except for all the Doc2Vec features that were fitted, where most of the classes were predicted correctly. I would recommend to first implement a simple model, and looking at how the model performs and whether there was improved sales especially for those products that were missing initially, and from there we could probably fine-tune the model more, build a recommender system to recommend products that are similar to those the customer tends to buy or even build a model to categorize products by aisles(subcategory to department) to help filter items better, if we see that the model helps improve sales for products especially those initially with missing departments.

### Contents:
- [Data Dictionary](#Data-Dictionary)
- [Data munging & initial EDA](#Data-munging-and-initial-EDA)
- [Initial Data Preprocessing](#Initial-Preprocessing)
- [Comparison of products between classes](#Comparison-of-products-between-classes)
-[Preparation for Train & Test](Preparing-Train-and-Test-sets)
-[Feature Extraction & Modelling](Feature-Extraction-and-Modelling)
-[Evaluation of Production Model](Evaluation-of-Production-Model)
-[Conclusion & Recommendation](Conclusion-and-Recommendation)

#### Data Dictionary
|<div style="text-align: left">Feature</div>|Type|Dataset|<div style="text-align: left">Description</div>|
|---|---|---|---|
|<div style="text-align: left">**product_name_words**</div>|<div style="text-align: left">*object*</div>|<div style="text-align: left">products_df</div>|<div style="text-align: left">Cleaned words of each product name</div>|
|<div style="text-align: left">**department_id**</div>|<div style="text-align: left">*integer*</div>|<div style="text-align: left">products_df</div>|<div style="text-align: left">All 21 IDs of each department and the target classes</div>|
|<div style="text-align: left">**department_name**</div>|<div style="text-align: left">*object*</div>|<div style="text-align: left">products_df</div>|<div style="text-align: left">All the 21 department names which would be used to label the confusion matrix for better visualization</div>|

## Conclusions
The production model choses what the Logistic Regression model with count vectorized features. There were about 216,000 features after vectorizing, we used the count vectorizer of max features 80,000 to fit into the model. The model may have been slightly overfitted with the train accuracy at 0.97 and test at 0.84. However it had the highest F1-score which was our main metric for measuring the performance of our models. Looking at the confusion matrix was another method for choosing the model. Most of the confusion matrix had similar results, except for all the Doc2Vec features that were fitted, where most of the classes were predicted correctly. I would recommend to first implement a simple model, and looking at how the model performs and whether there was improved sales especially for those products that were missing initially, and from there we could probably fine-tune the model more, build a recommender system to recommend products that are similar to those the customer tends to buy or even build a model to categorize products by aisles(subcategory to department) to help filter items better, if we see that the model helps improve sales for products especially those initially with missing departments.
