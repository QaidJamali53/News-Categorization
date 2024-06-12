# News-Categorization

## Objective:
The objective of this project is to classify news articles into predefined categories (e.g., Political, Technology, Entertainment, Business) using a combination of BERT embeddings and traditional machine learning classifiers. The project involves training a model on a labeled dataset and predicting the categories for a separate set of articles.

## Data:
Train DataFrame (train_df): Contains news articles (STORY) and their corresponding categories (SECTION).
Test DataFrame (test_df): Contains news articles (STORY) without categories. The task is to predict the categories for these articles.

## Methodology:
### Data Preparation:
Encode the categories (SECTION) in train_df using LabelEncoder.

### Feature Extraction using BERT:
Use the BERT tokenizer and model (bert-base-uncased) to extract embeddings from the news articles.
Focus on the [CLS] token representation from BERT's output, which captures the contextual embedding of the entire article.

### Classifier Training:
Convert BERT features to a format suitable for training (handling non-negative features for Multinomial Naive Bayes).
Train a Multinomial Naive Bayes classifier on the BERT embeddings of the training dataset.

### Prediction:
Apply the trained classifier to the test dataset to predict the categories of the articles.
Convert the predicted numeric labels back to the original category names using the label encoder.

### Evaluation (Optional):
Evaluate the model's performance on a validation set (if available) using metrics such as accuracy, precision, recall, and F1-score.
Visualize the results using confusion matrices and word clouds to understand the distribution of categories and the common words in each category.
