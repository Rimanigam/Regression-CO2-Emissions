TITLE : 
Project Report on CO2 Emissions in Canada using various regressors algorithms.

INTRODUCTION : 
In this project, I have built various model of the ‘CARBON DIOXIDE (CO2) LEVELS IN CANADA’ dataset which contains various information of the vehicles that are responsible for emitting CO2 levels. This dataset captures the details of how CO2 emissions by a vehicle can vary with the different features. The dataset has been taken from Canada Government official open data website. This is a compiled version. This contains data over a period of 7 years.
Canadians top the chart with cars that emit an average 206 grams of CO2 (gCO2) per kilometer. That's just from the fuel used to move them around. It's roughly equal to 8.7 liters of gasoline per 100 kilometers. American cars are only slightly less climate polluting.

DATASET EXPLORATION  : 
The foremost step to begin with the journey of analysis of data is to explore the data then various analysis and visualization methods and information acquisition will be done with Python. This dataset was explored using various inbuilt function like info (), shape (), unique () to know the variable/ column names, values and observations in the dataset. This gave us a quick insight into the dataset. Accessing the column names gave a quick idea as from where the analysis should be start.

Features : 
This dataset captures the details of how CO2 emissions by a vehicle can vary with the different features. The dataset has been taken from Canada Government official open data website. This is a compiled version. This contains data over a period of 7 years.

There is total 7385 rows and 12 columns. There are few abbreviations that has been used to describe the features. I am listing them out here. The same can be found in the Data Description sheet.
Model
4WD/4X4 = Four-wheel drive
AWD = All-wheel drive
FFV = Flexible-fuel vehicle
SWB = Short wheelbase
LWB = Long wheelbase
EWB = Extended wheelbase

Transmission
A = Automatic
AM = Automated manual
AS = Automatic with select shift
AV = Continuously variable
M = Manual
3 - 10 = Number of gears

Fuel type
X = Regular gasoline
Z = Premium gasoline
D = Diesel
E = Ethanol (E85)
N = Natural gas

Fuel Consumption : 
City and highway fuel consumption ratings are shown in litres per 100 kilometres (L/100 km) - the combined rating (55% city, 45% hwy) is shown in L/100 km and in miles per gallon (mpg)

CO2 Emissions : 
The tailpipe emissions of carbon dioxide (in grams per kilometre) for combined city and highway driving.

DATA ANALYSIS : 
After exploring the dataset, there was a need to analyze the data. In this study, I aimed to find a correlation between personal medical expenses and different factors, and compare them. In research, I found a strong positive relationship between CO2 Emissions(Y) and Engine Size(X) followed by Cylinders(X), Fuel Consumption Hwy(X) and Fuel Consumption City(X).
Y AND X VARIABLE FRAMEWORK
In this dataset, my Y variable was CO2 Emissions and the X variables were Make, Vehicle Class, Engine Size, Cylinders, Transmission, Fuel Type, Fuel Consumption City, Fuel Consumption Hwy, Fuel Consumption Comb. After looking at the P-values further we would decide which variables in X we should keep.

DATA PRE-PROCESSING : 
Handling Missing Values: - There are no null values in the dataset.	
Encoding the categorical Variables: - In this dataset, there are four categorical variables – Make, Vehicle Class, Transmissions and Fuel Type. For these categorical variables I created the dummy variables.

DATA VISUALIZATION : 
Data Visualization is the most important step because it gives the visual summary of the data which makes it easier for a layman as well to understand and identify the data patterns and trends than looking through thousands of rows on a spreadsheet. 
So, to gain insights, we have visualized our CO2 Emissions Prediction using various visualization methods. In this project, we have used various graphs like bar plot, boxplot, violin plot, histogram and heatmap to give a clear picture of the dataset.
By analysing all the plots created in the project code, we can see that,
•	A trend of increasing CO2 emissions can be observed from the increase in the number of cylinders.
•	Transmissions seems to hold some correlation to CO2 Emissions.
•	There seems to be a strong positive correlation between Fuel Consumption, Engine Size, Cylinders and the CO2 Emissions.
•	SUV-Small Vehicles are mostly in the trend among the people.
•	Ford, Chevrolet and BMW seem to be the most dominant make in the Automobile industry.

Correlation: From the heatmap, we can see that, Fuel Consumption has the highest impact on the CO2 Emissions, even though the CO2 levels are growing with Engine Size, Cylinders and Transmissions. Other variables didn’t show a strong positive correlation with the CO2 Emissions(y) variable.

STANDARDIZATION : 
As, in this dataset, there are different ranges of values, which can deviate our results. So, scaling is required to avoid that situation.  I used StandardScaler which is a class of sklearn.

BACKWARD FEATURE ELIMINATION : 
Using the stats model coding, we found the P-values of the variables and by doing feature elimination we dropped those variables whose P-values are higher. Now our model is good with p-values under the acceptable range.

K-FOLD CROSS VALIDATION SCORE : 
The k-fold cross-validation procedure is a standard method for estimating the performance of a machine learning algorithm or configuration on a dataset. 
The motivation to use cross validation techniques is that when we fit a model, we are fitting it to a training dataset. Without cross validation we only have information on how does our model perform to our in-sample data. Ideally, we would like to see how does the model perform when we have a new data in terms of accuracy of its predictions. 

SPLITTING THE DATA INTO TRAIN AND TEST AND MODEL CREATION : 
After splitting the data into Training and Testing, model building was done. There are many models for machine learning, and each model has its own strengths and weaknesses. In this project, I have tried various linear algorithms and tuned the parameters using the GridSearchCV which tries all the combinations of the values passed in the dictionary and evaluates the model for each combination using the Cross-Validation method. Hence after using this function we get accuracy/loss for every combination of hyperparameters and we can choose the one with the best performance.
The Regressors I used to find the best model out of them are: -
1)	Linear Regression
2)	K-Nearest Neighbors (KNN) Regressor
3)	Support Vector Regression (SVR)
4)	Decision Tree Regressor
5)	Random Forest Regressor
6)	AdaBoost Regressor


FINAL CONCLUSION: 
After comparing all the six models, I came to this conclusion which will help to choose the best model out of all the models to get the best results.
•	All the models gave the best score as around 99% except the K-Neighbors Regressor whose best score came out to be 97% which is also a good score.
•	The test scores are also near to the best scores of all the models except the Decision Tree Regressor whose best score is 99% and test score is 90%.
•	The K-fold cross Validation score of all the models is high around 99% except the AdaBoost Regressor 93% and Support Vector Regressor 82%.
•	The R-Squared values are good for all the models which is around 99%.
•	The MSE values are lower in Random Forest Regressor, AdaBoost Regressor and Support Vector Regressor which indicates a good model.
•	The RMSE values are a bit higher in Linear Regressor and K-Neighbors Regressor, though not much higher and lower in other models indicating a better fit model.
•	The Adjusted R-Square values are almost same and higher for all the models except with the Linear Regression which indicates that additional input variables are adding value to the model.
•	The testing and the training scores for all the models are almost near to each other that means there is no overfitting and underfitting, instead they are the best fit models.

So, after comparing all the scores, it seems that Linear Regressor Model, Random Forest Regressor the best model followed by the Decision Tree Regressor Model but I will choose the Linear Regression Model as it will be easy and less complex to deploy.
