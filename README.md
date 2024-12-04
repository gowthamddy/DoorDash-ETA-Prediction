# FnB Delivery ETA Prediction  

## Overview  
This project aims to predict the estimated delivery time for food orders from various restaurants across India. Accurate delivery time predictions are crucial for enhancing consumer experience in ride-hailing superapp companies. Research indicates that underestimating delivery times is significantly more detrimental than overestimating, making this prediction model vital for operational success.  

## Problem Statement  
We are provided with a dataset containing information from thousands of restaurants in India regarding their food delivery times for online orders. As data scientists, our objective is to develop a predictive model for delivery times based on the provided features.  

## Features  
The dataset includes the following attributes:  
- **Restaurant**: Unique ID representing each restaurant.  
- **Location**: The geographical location of the restaurant.  
- **Cuisines**: Types of cuisines offered by the restaurant.  
- **Average_Cost**: Average cost per person/order.  
- **Minimum_Order**: Minimum order amount required.  
- **Rating**: Customer rating for the restaurant.  
- **Votes**: Total number of votes received by the restaurant.  
- **Reviews**: Total number of customer reviews for the restaurant.  
- **Delivery_Time**: Actual delivery time of the restaurant (Target variable).  

## Solution Approach  
The problem was tackled using traditional machine learning models.  

### Steps Taken  
1. **Preprocessing**:   
   - Addressed missing values and corrected data types, converting numerical fields from strings to appropriate formats.  
   - Removed irrelevant features from the dataset.  

2. **Feature Engineering**:  
   - Dropped the Restaurant and Location columns as they were not relevant to delivery time prediction.  
   - Identified 101 unique cuisines, implementing a multi-label approach by creating 8 new columns to represent them. Rows with fewer than 8 cuisines were filled with NaN, labeled as None, while new or blank restaurant entries were set to 0.  
   - Scaled the numerical data for better model performance.  

3. **Model Selection**:  
   - Chose Gradient Boosting as the machine learning algorithm and constructed a 4-layer Deep Neural Network (DNN) with the architecture: (5, 20, 20, 7, 1).  

4. **Model Building and Training**:  
   - Built models using Sci-Kit Learn for Gradient Boosting and Keras with TensorFlow for the DNN.  
   - Conducted training on Visual Studio with GPU support for enhanced efficiency.  

5. **Model Evaluation and Output Generation**:  
   - Evaluated model performance using the R² metric.  
   - Generated predictions for the test dataset, which were exported to an Excel file.  

Due to the absence of the target variable (Delivery_Time) in the test dataset, validation was not feasible. Training was concluded once the Mean Squared Error (MSE) reached approximately 0.5-0.6.  

## Data Observations and Processing  
- Dropped the Restaurant and Location columns.  
- Noted a total of 101 cuisines, with a maximum of 8 cuisines per entry.  
- Introduced 8 columns for cuisine representation, filling in with NaN where necessary.  
- Set newly opened or blank restaurant entries to 0.  
- Scaled the data for improved model accuracy.  

This project provides valuable insights into food delivery time predictions, contributing to enhanced consumer satisfaction and operational efficiency.
