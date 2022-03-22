# Project 8: Deploy a model in the cloud

*Keywords* : big data, spark/hadoop, AWS, GCP, computer vision

## Goal
Build a scalable big data architecture. The cloud services selected must unable a computer vision model to run on thousands of images.

The program should classify fruits/vegetable images correctly (multi-class supervised classification).

The model itself is not required, but the first steps of loading and preprocessing images must be implemented.

## Dataset
The dataset used is "Fruits 360" from Kaggle that you can dowload here: https://www.kaggle.com/moltean/fruits

Tests were made with 9 images (3 classes, 3 images each).

## Files
* *P8_spark.ipynb*: the main notebook file that output the extracted and reduced features.
* *Read_export.ipynb*: to test if the csv output has the correct format.
* *data_pca.csv*: features extracted from pre-trained model and reduced with PCA.
* *learn_spark.ipynb*: basic spark manipulation.

## Big data framework
* First, I ran several tests on an EC2.micro instance (Ubuntu) on AWS with S3 bucket and appropriate IAM users configuration. All the necessary data science packages were installed and functional (Anaconda distribution of python, spark/hadoop, java, etc...).
* I moved to a slightly bigger instance (E2 medium) on GCP with cloud storage and always the IAM users configuration. The tests on the spark scripts were also successfull.
* Operations were distributed as much as possible with spark.

## Spark script
* The notebook present a short loading/preprocessing of the images.
* Then a feature extraction from the pre-trained ResNet50 model.
* The features are then reduced with a PCA and exported to csv.
