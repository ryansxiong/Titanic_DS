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

**Cabin**
* I first took a look at the 'Cabin' column. I separated the column into 'cabin letter' and 'cabin multiple'. I then took a look at the survival percentages.  

![Screenshot (97)](https://user-images.githubusercontent.com/91089401/153506309-7c82c477-f396-4f0f-bf85-b10534ad7ad3.png)

**Fare**
* Taking a look at fare prices and categorizing them into small, medium, and large price ranges. I did not include this in the final model since I produced better results with the original fare. This may be due to overfitting the model. 

![Screenshot (98)](https://user-images.githubusercontent.com/91089401/153507811-e55def0a-eb7b-443a-bb36-a04bbe566817.png)
