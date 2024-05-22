## Income Prediction on the Census Population dataset

**Project description:** 

This project  involves data cleaning, data wrangling, feature correlation, model training and model evaluation. The project goal was do understand what factors were significant to determine salary income. The approach for this was a binary classification.
The goal of this is to Predict whether income exceeds $50K/yr based on census data and what census features can lead to higher income

### 1. Data Exploration

The features and target dataset were merged into one dataframe and the table below shows an idea of what the dataframe looked like. The initial datafra,me had 48842 rows before cleaning

![image](https://github.com/moyinajayi/moyinajayi.github.io/assets/9222400/6ca57b30-5f3a-41f0-9a18-0135aa31cf7c)


### 2. Data Cleaning  and alignment

AT first glance, the data in the Target column seems to have a mismatch. SO Daata cleaning was done to align teh column to have just 2 target labels.
![image](https://github.com/moyinajayi/moyinajayi.github.io/assets/9222400/dcefcd9d-08a3-4ba0-aef2-6edbaf4413c8)
```python
df['income'] = df['income'].replace(['<=50K.', '>50K.'], ['<=50K','>50K'])
df['income'].value_counts()
```
![image](https://github.com/moyinajayi/moyinajayi.github.io/assets/9222400/8d6db985-bd32-4f71-9fe6-a8ef07bf24bc)


### 3. Data visualizations

Distribution of Age, Fnlwgt and education
![image](https://github.com/moyinajayi/moyinajayi.github.io/assets/9222400/0adfb1db-52e9-4c8f-8d51-49a43076bf75)

Distribution of Occupation, Family Relationship and Race
![image](https://github.com/moyinajayi/moyinajayi.github.io/assets/9222400/da194dfe-afc3-4c85-badc-ea9ea9b5b11a)


### 4. Feature scaling and correlation

The features in the data were then scaled using a standard scaler. Then afterwards, a correlation heatmap was displayed to identify highly correlated features in the dataset

![image](https://github.com/moyinajayi/moyinajayi.github.io/assets/9222400/582ac9fc-aa67-4d29-bc8c-fe15e4a1d9fc)



### 5. Model Training
The approach to this was to train multiple models and identify the best performing based on  Accuracy and Recall metrics.
![image](https://github.com/moyinajayi/moyinajayi.github.io/assets/9222400/5a9580f9-c49c-4d74-b02a-346c5390944a)

The 4 Models selected for training were teh Logistic regression, Random Forest, Decision Tree, XGBoost classifiers. These are popular models typically used in binary classification.
As this was a simple project, no hyper parameter tuning was done. The default model objects were simply initialized to train the model.

![image](https://github.com/moyinajayi/moyinajayi.github.io/assets/9222400/f3b3c099-558a-483d-8729-1760fff7a06c)
Below is the result of the model training for each algorithm .
![image](https://github.com/moyinajayi/moyinajayi.github.io/assets/9222400/a1827a41-5910-43ae-83d6-7e9672fe7d3f)



### 6. Model Evaluation

The XGBoost classifier seems to be the best performing with  

![image](https://github.com/moyinajayi/moyinajayi.github.io/assets/9222400/b0171b81-f750-4106-98b3-6fe87928a9d2)

![image](https://github.com/moyinajayi/moyinajayi.github.io/assets/9222400/755f60bd-014e-4488-a921-3097f8c58b3d)


### 7. Model Feature Importance

The feature Importance was then calculated to understand teh significant features from  the dataset.
![image](https://github.com/moyinajayi/moyinajayi.github.io/assets/9222400/6cb7d913-a4b3-4973-804d-dc69a30e1119)

Relationship, capital gain, Education num, marital status as well as capital loss are featuesres that can influence the salary income.

### 8. Conclusion

I have identified features that could be significant in determinging a higher salary range in the population dataset. 
Future work might be to further engineer features, or apply hyper parameter tuning to select best params for fine tuning the model and improving performance.




For more details see [Repo](https://github.com/moyinajayi/Income_prediction_xgboost)
