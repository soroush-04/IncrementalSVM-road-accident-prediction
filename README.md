# Road Accident Severity Prediction 
---

<u>Table of contents</u>
=======

<!--ts-->
  - [Problem Statement ](#problem-statement-1)
  - [Data Description](#datadescription)
  - [Data Preprocessing](#preprocessing)
  - [Improved SVM Model](#improved)
  - [Visualization Folium Map](#visualization)
  - [Incremental SVM Model](#incremental)
<!--te-->

---

## Problem Statement <a id="problem-statement-1"></a>
The project aims to address road accidents problem through the use of Machine Learning models, particularly an enhanced Support Vector Machine (SVM) model. It also introduces an incremental SVM model. In traditional SVM models scaling is done during the pre processing step however in our model scaling is done after splitting the dataset into training and testing datasets. During scaling, first the input training dataset is fit and transformed using the Standard Scaler object and then the same object is used to transform the input testing dataset.



## Data Description <a id="datadescription"></a>

The Original Dataset contained 47 attributes with 1.5 million accident records. The Dataset included attributes such as Severity which depicts how severe an accident was where 1 indicates the least severe and 4 the most severe. The Dataset also included spatiotemporal attributes; However, the final dataset for the SVM model, which was created after conducting feature extraction, included the 12 most significant factors shown in table below.

<div align="center">

  | Attribute | Description |
  | :------------ | :------------ |
  | ID | The unique identifier of an accident |
  | differ HHMM | This represents the difference between the start time and the end time of the accident. |
  | S time | This Shows the accident’s start time in local time. |
  | Month | This indicates the month in which the accident occurred. |
  | Start Lat | The latitude in GPS coordinates of the starting position of an accident. |
  | Start Lng | The longitude in GPS coordinates of the start- ing position of an accident. |
  | Distance.mi. | The extent to which the accident has impacted the road. |
  | Accident.Description | The accident is described in basic language. |
  | Traffic.Speed | This shows the speed of the vehicle |
  | Street | This depicts the street name. |
  | City | This shows the city name |
  | Weather Condition | This depicts the different weather conditions such as rain, snow, thunderstorm, fog, etc |

</div>

## Data Preprocessing <a id="preprocessing"></a>

-  <u>Analysing the dataset</u>

-  <u>Handling Null Values</u>

-  <u>Handling Categorical Variables</u>: We have used LableEncoder() class from sklearn preprocessing library which encodes the values between 0 to n-1.

- <u> Feature Selection </u>: ExtraTressClassifier from sklearn.essemble has been used which randomises specific decisions, and subsets of data to avoid over learning and over fitting. 

<div align="center">
  <img src="./Images/1.png" alt="Image 2-1" width="400" style="margin: 0 10px;">&nbsp;&nbsp;&nbsp;
</div>


## Improved SVM Model <a id="improved"></a>

Utilized scikit-learn to separate the dataset 70/30 into training and testing. Further, the X train and X test data is scaled using StandardScaler() from sklearn.preprocessing. Standardizing is an important step especially when dealing with spatiotemporal data as some variables may dominate over others. It re-scales the distribution of values so that the mean of observed values is 0 and the standard deviation is 1. In this model scaling is implemented after the data has been split into training and testing dataset. To perform scaling,first the X train data is fitted and transformed using StandardScaler() object and then using the same object the X test data is transformed.

## Visualization Folium Map <a id="visualization"></a>


<div align="center">
  <img src="./Images/2.png" alt="Image 2" width="360" style="margin: 0 10px;">&nbsp;&nbsp;&nbsp;
  <img src="./Images/3.png" alt="Image 3" width="360" style="margin: 0 10px;">
</div>

## Incremental SVM Model <a id="incremental"></a>

The incremental model presented learns from the previously proposed improved support vector machine model to predict the severity. At first, the data is read in a new CSV file and a copy of new CSV is also created to retain the original values of latitude and longitude. Next the data is pre processed and scaled using the same StandardScaler object that was previously used in the improved SVM model. Further, the prediction of the traffic accident severity is done using the improved SVM classifier and the predictions are stored in a new variable. 
 Based on the confusion matrix, the incremental SVM model has almost accuracy up to 70%, while the enhanced SVM model has high accuracy of 94.8 percent. 

 <div align="center">
  <img src="./Images/4.png" alt="Image 2-1" width="400" style="margin: 0 10px;">&nbsp;&nbsp;&nbsp;
</div>

<br>