# Quora Question Pairs Detection

## 📌 Project Overview
This repository contains a machine learning pipeline designed to identify duplicate question pairs on Quora. By analyzing over a random 30,000 question pairs, the goal is to build a model that can determine if two questions have the same intent, which is crucial for reducing redundancy in large-scale Q&A platforms.

## 📊 Dataset Analysis
The project utilizes the Quora Question Pairs dataset:
* **Total Pairs**: ~404,290
* **Pairs Taken**: ~30,000

## 🛠️ Feature Engineering
The core of the project involves transforming raw text into meaningful numeric features:
* **Basic Features**: Length of each questions,	number of words, common words	total words, words share ratio (common words / total words)
*  **Advanced Features**:
*  *Token Features*: common word count (min and max), common stopword count (min and max), common token count(min and max), last word equality, first word equality
*  *Length Features*: absolute length difference, mean length, longest substring ratio, mean word length
*  *Fuzzy Features*: fuzzy ratio, fuzzy partial ratio, fuzzy token sort ratio, fuzzy token set ratio

* **Vectorization**: Implemented `CountVectorizer` (Bag of Words) with the top 3,000 features to represent text data.

## 🚀 Machine Learning Models
Three high-performance classification models were implemented and compared:
1. **Random Forest**: Baseline ensemble model.
2. **XGBoost**: Gradient boosted decision trees for improved accuracy.
3. **LightGBM**: Optimized for speed and handling large-scale data.

**Result**: 

**Base Model accuracy**

1. **Random Forest**: 75.95%
2. **XGBoost**: 75.716%
3. **LightGBM**: 76.63%

**After Feature Engineering**

1. **Random Forest**: 79%
2. **XGBoost**: 79.77%
3. **LightGBM**: 80.12%

**Confusion Matrix for Random Forest**: 
 [[4331  736]
 [ 944 1989]]
**Confusion Matrix for XGBoost Model**: 
 [[4270  797]
 [ 821 2112]]
**Confusion Matrix for LightGBM**: 
 [[4251  816]
 [ 774 2159]]
