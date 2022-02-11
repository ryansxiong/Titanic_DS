# Titanic - Machine Learning From Disaster (Competition)
This is a machine learning competition on Kaggle. The goal is to create a model to predict which passengers survive in the Titanic shipwreck.
_link:_ https://www.kaggle.com/c/titanic 

## Codes and Resources Used
* **Python Version**: 3.8
* **Packages**: Pandas, Numpy, Scikit-learn
* **Visual Tools**: Matplotlib, Seaborn

## EDA
Before creating a model I cleaned and familiarized myself with the data to find if there were any trends and correlations.

**Histograms**

![Screenshot (92)](https://user-images.githubusercontent.com/91089401/153504811-f7155ae5-955d-489a-b27f-0b526eed961f.png)
![Screenshot (93)](https://user-images.githubusercontent.com/91089401/153504836-591536ba-8df3-4b24-8b1b-5e7db69c5f23.png)

**Heat Map**

![Screenshot (113)](https://user-images.githubusercontent.com/91089401/153505030-35a6c345-3e1e-4a5a-ab81-438854f0712a.png)

**Bar Graphs**

![Screenshot (95)](https://user-images.githubusercontent.com/91089401/153505188-03968d88-0a27-45e2-80cf-e08b0a3758d9.png)
![Screenshot (96)](https://user-images.githubusercontent.com/91089401/153505200-a3baeb9d-abfa-4942-8731-1c4aef158d77.png)

## Feature Engineering
Now that I am more familiar with the data, this is where I manipulate the data for modeling. 

1) I first took a look at the 'Cabin' column. I separated the column into 'cabin letter' and 'cabin multiple'. I then took a look at the survival percentages.  
2) Taking a look at fare prices and categorizing them into small, medium, and large price ranges. I did not include this in the final model since I produced better results with the original fare. This may be due to overfitting the model. Although, I did not include this, I still think this is still something to keep in mind.
3) For the tickets column, I also separated the numbers and letters ('ticket_number', 'ticket_letters'). I also used a pivot table to compare those who survived if they had a number on their ticket.
4) I created a new column to count the family size. _I did not include this in the final model_
5) I then fixed and categorized name titles for each passenger. Once I got the name title for each passenger, I categorized the least common names into the other categories, and had a special category for specific titles. For example, mlle would count as 'miss' and 'don' would count as 'other'.


**Cabin**

![Screenshot (97)](https://user-images.githubusercontent.com/91089401/153506309-7c82c477-f396-4f0f-bf85-b10534ad7ad3.png)

**Fare** 

![Screenshot (119)](https://user-images.githubusercontent.com/91089401/153518559-dda393c2-47bb-4736-87a3-b0ed3f31d5bd.png)

**Tickets**

![Screenshot (118)](https://user-images.githubusercontent.com/91089401/153518268-5cb52897-738b-42aa-ac8e-972a040284cc.png)

**Family Size**

![Screenshot (120)](https://user-images.githubusercontent.com/91089401/153518706-8e62ea99-8b71-4f5a-8e78-059e3cf07004.png)

## Prepare for Modelling
1) Looked at the percentage of missing values for the dataset.
2) Dropped 'embarked' null values.
3) Filled NA values for both 'Fare' and 'Age'.
4) Changed pclass into string since it is a categorical value.
5) Used logarithm for 'Fare' to normalize the distribution.

![Screenshot (121)](https://user-images.githubusercontent.com/91089401/153519257-edb2e636-d75f-4792-bbfc-a3bf7a57151b.png)

## Getting Dummies
Used pandas to get dummies and split to train test.

![Screenshot (122)](https://user-images.githubusercontent.com/91089401/153519567-94623116-0322-4ad3-b188-4791cd77aed1.png)

## Basic Modelling
Below you will find all the models that I used and how accurate the model was.

| **Model** | **Percentage** |
|---|---|
| xgboost classifier | 82.23% |
| Gaussian NB | 76.50% |
| MultinomialNB | 79.19% |
| Random Forest Classifier | 80.32% |
| Logistic Regression | 82.23% |
| Support Vector Machine | 73.23% |
| SGDClassifier | 76.15% |
| KNeighborsClassifier | 81.11% |
| Decision Tree Classifier | 78.74% |
| Gradient Boosting Classifier | 83.58% |

![Screenshot (123)](https://user-images.githubusercontent.com/91089401/153520613-a1593bfd-4913-43f9-aa24-290851c133e1.png)
![Screenshot (124)](https://user-images.githubusercontent.com/91089401/153520663-13d3afb6-8fe6-4d12-8bb6-4e5dd43358a0.png)
![Screenshot (125)](https://user-images.githubusercontent.com/91089401/153520709-03b6739a-4c0e-43f2-94e8-8afe775931f0.png)

## Tuning Models With GridsearchCV
Using GridsearchCV to tune the models

| **Model** | **New Score** |
|---|---|
| xgboost classifier 82.23% | **85.72%** |
| Gaussian NB 76.50% | not tuned |
| MultinomialNB 79.19% | not tuned |
| Random Forest Classifier 80.32% | **83.36%** |
| Logistic Regression 82.23% | **82.57%** |
| Support Vector Machine 73.23% | not tuned |
| SGDClassifier 76.15% | not tuned |
| KNeighborsClassifier 81.11% | **81.22%** |
| Decision Tree Classifier 78.74% | **82.34%** |
| Gradient Boosting Classifier 83.58% | **83.36%** |

![Screenshot (129)](https://user-images.githubusercontent.com/91089401/153521727-76d39993-3435-4feb-a2cb-d95265aee488.png)
![Screenshot (126)](https://user-images.githubusercontent.com/91089401/153521559-7fcf2651-5604-4761-af58-f2229e5da307.png)
![Screenshot (127)](https://user-images.githubusercontent.com/91089401/153521617-57318332-5b29-40c9-b6b8-97a6bda7d92d.png)
![Screenshot (128)](https://user-images.githubusercontent.com/91089401/153521676-57b3fc37-b209-46bd-8a68-57ee5998b19f.png)



