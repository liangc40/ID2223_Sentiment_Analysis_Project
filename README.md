# ID2223 Sentiment Analysis Project



## Abstract

Nowadays, with social media flourishing, more and more people publish their thoughts and feelings on apps such as Tweet. By classifying whether a tweet is depressed, psychiatrists could effectively judge whether their patients are mentally healthy, and such work could be achieved automatically with Machine Learning which could save a lot of time and social resources.  To accomplish such a task, we need to train our model based on real-life Tweet data and make predictions on new Tweet to check whether the predictions are correct. 
 
 

## Dataset
We use historical data set to train our classifier and the NEW data can be fetched on demand with UI on HuggingFace.

## Model

BERT is the most popular transformer for a wide range of language-based machine learning and has enabled diverse innovation across many borders and industries; it could also be applied to our sentimental analysis task. Applying the BERT model would require several steps, including word piecing, building the tokenizer, and data formatting. After preprocessing our data, we store all the features on Hopsworks for further access. 

## General Structure
### sentiment-feature-pipeline.py
A feature pipeline that insert features and labels into our serverless model. Specifically, we created our feature group with a specified name, version, primary key, etc. Then insert the sentiment analysis dataflow into our feature group.

### sentiment-training-pipeline.py
It reads training data with a Feature View from Hopsworks, packages the data into data loaders, creates a sentiment classifier based on the BERT model. and trains our model. The final weights of the model are saved on HuggingFace model hub. URL: https://huggingface.co/liangc40/sentiment_analysis

### sentiment analysis inference pipeline
Model trained by training pipeline is deployed on Huggingface helping users to analyse sentiment of any sentances or Tweets. 

## MLOPs implementations
### Trining Monitering and Looging with Weights and Biases
URL: https://api.wandb.ai/report/liangchen40/018tb72h
![Alt text](https://github.com/liangc40/ID2223_Sentiment_Analysis_Project/blob/main/Image/wandb.JPG)

### Unit Testing
We implemented Unit Testing for the data loader, Twseet Daaset class and the Depression Classifier model. The code is included in the training pipeline.

![Alt text](https://github.com/liangc40/ID2223_Sentiment_Analysis_Project/blob/main/Image/unit_testing.png)

## Deployment on HuggingFace

https://huggingface.co/spaces/qisan/Depressed_sentimental_analysis

### Sentiment Analysis Based on Single Text

Users can type in the sentence to analyse the sentiment. 

![Alt text](https://github.com/liangc40/ID2223_Sentiment_Analysis_Project/blob/main/Image/single_text.png)

### Sentiment Analysis on Tweets with the Keyword

Users can input any keywords to search the relevant Tweets. The first 10 tweets with sentiments will be shown.

![Alt text](https://github.com/liangc40/ID2223_Sentiment_Analysis_Project/blob/main/Image/multiple_text.png)

