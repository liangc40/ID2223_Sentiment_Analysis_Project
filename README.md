# ID2223 Sentiment Analysis Project



## Abstract

Nowadays, with social media flourishing, more and more people publish their thoughts and feelings on apps such as Tweet. By classifying whether a tweet is depressed, psychiatrists could effectively judge whether their patients are mentally healthy, and such work could be achieved automatically with Machine Learning which could save a lot of time and social resources.  To accomplish such a task, we need to train our model based on real-life Tweet data and make predictions on new Tweet to check whether the predictions are correct. 
 
 

## Dataset


## Model

BERT is the most popular transformer for a wide range of language-based machine learning and has enabled diverse innovation across many borders and industries; it could also be applied to our sentimental analysis task. Applying the BERT model would require several steps, including word piecing, building the tokenizer, and data formatting. After preprocessing our data, we store all the features on Hopsworks for further access. 

## General Structure
### sentiment-feature-pipeline.py
A feature pipeline that insert features and labels into our serverless model. Specifically, we created our feature group with a specified name, version, primary key, etc. Then insert the sentiment analysis dataflow into our feature group.

### sentiment-training-pipeline.py
It reads training data with a Feature View from Hopsworks, packages the data into data loaders, creates a sentiment classifier based on the BERT model. and trains our model. The final weights of the model is saved on HuggingFace model hub. URL: https://huggingface.co/liangc40/sentiment_analysis

### sentiment analysis batch inference pipeline

## Deployment on HuggingFace

https://huggingface.co/spaces/qisan/Depressed_sentimental_analysis

### Sentiment Analysis Based on Single Text

![Alt text](https://github.com/liangc40/ID2223_Sentiment_Analysis_Project/Image/single_text.png)
