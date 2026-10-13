# obesity-ml-comparison
Comparing neural networks and random forests for obesity level classification, with a focus on feature selection and model limitations.


# Obesity Level Classification: Machine Learning Comparison

## Overview

This project revisits an Artificial Neural Network (ANN) originally developed during my Bachelor's degree in Biology.

The original goal was to predict obesity levels using demographic, dietary, and physical activity data. The ANN was implemented in R using Keras and TensorFlow.

The initial model achieved approximately **91.9% test accuracy**. However, this raised an interesting methodological question: since obesity categories are closely related to Body Mass Index (BMI), how much of the model's performance depends on the inclusion of height and weight?

This repository aims to investigate that question while exploring alternative machine learning approaches.

## Dataset

**Estimation of Obesity Levels Based on Eating Habits and Physical Condition**

Source: [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/544/estimation+of+obesity+levels+based+on+eating+habits+and+physical+condition)

The dataset contains 2,111 observations and 16 predictor variables describing eating habits, physical conditions, and demographic characteristics.

The target variable (`NObeyesdad`) represents seven weight categories.

## Original Implementation

The initial ANN includes:

- Two hidden dense layers (32 and 16 neurons) with ReLU activation
- A Softmax output layer for multiclass classification
- Adam optimizer and categorical cross-entropy loss
- An 80/20 training/test split
- Model evaluation using accuracy, confusion matrices, and training/validation loss curves

A simpler ANN with one hidden layer was also evaluated.

The original implementation is available in `notebooks/01_original_ANN.Rmd`.

## Current Objectives

- [x] Restore and run the original ANN
- [ ] Improve preprocessing and validation methodology
- [ ] Evaluate ANN performance without height and weight
- [ ] Implement a Random Forest classifier
- [ ] Compare models using appropriate classification metrics
- [ ] Investigate feature importance and discuss dataset limitations

## Methodological Considerations

Several limitations motivate the ongoing work:

- **BMI-related features:** Height and weight may explain much of the predictive performance because the target classes are closely related to BMI.
- **Synthetic observations:** A substantial portion of the dataset consists of synthetic observations, potentially affecting model evaluation and generalizability.
- **Validation strategy:** The original preprocessing and validation procedure can be improved to reduce information leakage.

The goal is not simply to maximize predictive accuracy, but to better understand what the models learn and how reliably their performance can be evaluated.

## Technologies

- R
- Keras / TensorFlow
- caret
- tidyverse

## Running the Project

1. Download the dataset from the UCI repository.
2. Place `ObesityDataSet_raw_and_data_sinthetic.csv` in the `data/` directory.
3. Install the required R packages and configure the TensorFlow environment.
4. Open the RStudio project and run `notebooks/01_original_ANN.Rmd`.

The original implementation uses legacy Keras with a TensorFlow 2.16 backend. Python dependencies are declared in the R Markdown file.

## Project Background

The original ANN was developed as my individual contribution to a group machine learning assignment during my Bachelor's degree in Biology.

The subsequent methodological analysis and model comparisons are independent extensions of that work.

## Status

**Work in progress** — Original ANN restored; additional experiments planned.
