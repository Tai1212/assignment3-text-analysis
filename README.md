# Hebrew Text Gender Classification 

## Table of Content
* [General Info](#general-info)
* [Architecture](#architecture)
* [Results](#results)
* [Features](#features)

## Features
1. Raw Data:
   * The dataset begins as an Excel file containing rows of sentences, each labeled with a corresponding gender ('m' for male or 'f' for female).
     
2. Data Preprocessing:
   * Text Cleaning:
     * Removed punctuation , symbols, digits, and other non-alphanumeric characters.
     * Eliminated English words from the Hebrew dataset, ensuring language consistency.
     * Standardized text to lowercase for uniformity.
  * Gender Label Validation:
    * Ensured that only valid gender labels ('m' for male and 'f' for female were present in the dataset. Invalid rows were discarded.
      
3. Tokenization:
   * Utilized a Hebrew tokenizer to extract meaningful tokens (words) from the text.
   * The tokenizer filtered and included only hebrew words, further removing noise from the dataset.

4. Feature Engineering:
   * TF-IDF Vectorization: Captured word importance by weighing term frequency against its inverse document frequency.
   * Count Vectorization: Represented the frequency of n-grams (single words or sequence of words) in the text.
  
5. Model Training and Cross Validation:
   * Models: Linear SVC, MLP Classifier, Perceptron, SGD Classifier, K Neighbors Classifier, Decision Tree Classifier.
   * Each model's performance was evaluated using 10-fold cross-validation, focusing on the F1-macro score to balance the evaluation between classes ('m' and 'f').

6. Hyperparameter Tuning:
   * GridSearchCV: Used to identify the best hyperparameters for each model, further improving their accuracy.
   * Performed seperatly for TF-IDF and Count Vectorization representations.

7. Final Predictions:
   * After Identifying the best model and vectorization method, predictions were made on unseen test data.
  
