# Credit Card Fraud Detection

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?logo=numpy&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?logo=scikitlearn&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?logo=plotly&logoColor=white)

## Short description

A machine learning project that classifies credit card transactions as fraudulent or genuine, using the well-known Kaggle credit card fraud dataset and a desktop GUI built with Tkinter.

## Technologies

Python, pandas, NumPy, scikit-learn (RandomForestClassifier), Matplotlib, Tkinter

## Features

- A Tkinter desktop interface for loading a dataset, training a model, and running predictions without touching the command line
- Splits the dataset into training and test sets and reports their sizes
- Trains a Random Forest classifier on the transaction data, using balanced class weights to account for how rare fraud cases are
- Reports model accuracy after training
- Loads a separate test file and classifies each transaction as fraudulent or clean
- A bar chart summarizing total, normal, and fraudulent transactions in a given test file

## The process

The dataset for this kind of problem is extremely imbalanced (fraud is a very small fraction of all transactions), so the main design decision was using a Random Forest with balanced class weights rather than a plain classifier that could get high accuracy by mostly predicting "not fraud." Wrapping the workflow in a simple Tkinter GUI (upload data, train, predict, visualize) made it possible to run the whole pipeline step by step and see the results at each stage instead of just printing to a terminal.

## What I learned

- Handling a strongly imbalanced classification problem with class weighting
- Splitting data into training and test sets and evaluating a model with accuracy and classification metrics
- Building a basic desktop GUI with Tkinter to wrap a machine learning workflow
- Visualizing classification results with Matplotlib
- Structuring a script around global state shared across GUI callback functions

## How it can be improved

- Report precision, recall, and F1-score alongside accuracy, since accuracy alone is misleading on imbalanced data
- Add cross-validation instead of a single train/test split
- Let the user choose or tune the model instead of hardcoding a Random Forest
- Package the dataset download step into the app instead of a manual setup instruction

## How to run the project

1. Clone the repo
2. Download the dataset from Kaggle's "Credit Card Fraud Detection" dataset and place `creditcard.csv` inside the `dataset/` folder
3. Run `python CreditCardFraud.py` (or use `run.bat` on Windows)
