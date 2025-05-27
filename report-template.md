# Report: Predict Bike Sharing Demand with AutoGluon Solution
####Luluwa Modeer

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
TODO: Add your explanation

When I tried to submit my predictions, I saw that some values were negative. The system did not accept negative numbers, so I changed all negative predictions to zero. After that, I was able to submit the results without any problems.


### What was the top ranked model that performed?
TODO: Add your explanation

The top-ranked model was WeightedEnsemble_L3. This model performed the best on the validation set and generated the most accurate predictions on the test set.

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
TODO: Add your explanation

During the exploratory data analysis, I first checked for any missing values using df.isnull().sum(). This helped me identify whether the dataset contained any empty or null entries.

Next, I used df.info() to examine the data types of each column and to get a quick overview of the dataset’s structure.

I also printed the column names as well as the total number of rows and columns to better understand the dataset’s dimensions.

For the datetime column, I extracted the year, month, day, and hour into separate columns. This feature engineering step allowed the model to better capture temporal patterns in the data.

After training the models, I used model_names to list all the models that were trained. Additionally, I plotted histograms to visualize the performance distribution of each model.

### How much better did your model preform after adding additional features and why do you think that is?
TODO: Add your explanation

The model's performance improved noticeably after adding the additional features, such as the separated year, month, day, and hour extracted from the datetime column. 

This improvement likely occurred because breaking down the datetime into more granular components allowed the model to capture important temporal patterns and trends that were not obvious from the original datetime column alone. 


## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
TODO: Add your explanation

Once the hyperparameters were adjusted, the model's performance dramatically increased. After adding features, the Kaggle RMSE score was 0.670; after hyperparameter adjustment, it fell to 0.493. This suggests that choosing model parameters like learning_rate and max_depth carefully improved the model's ability to generalize and produce more precise predictions.


### If you were given more time with this dataset, where do you think you would spend more time?
TODO: Add your explanation

If I were given more time with this dataset, I would spend more time on training the model to improve its accuracy and fine-tune its performance, and try more feature engineering.


### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|hpo1|hpo2|hpo3|score|
|--|--|--|--|--|
|initial|-53.104|-53.464|-54.920| 1.801 |
|add_features|[-30.846|-31.013|-31.997|0.670|
|hpo|-38.386|-38.634| -39.060|0.493|


### Create a line plot showing the top model score for the three (or more) training runs during the project.

TODO: Replace the image below with your own.

<img width="524" alt="image" src="https://github.com/user-attachments/assets/e07d2230-df56-402e-b2b9-9adc59bf643c" />


### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.

<img width="517" alt="image" src="https://github.com/user-attachments/assets/a7fb8955-f809-4dba-bc6a-1368920b7466" />

## Summary
TODO: Add your explanation

I used AutoGluon in this project to forecast demand for bike sharing. After preliminary training, the model was improved by collecting valuable temporal characteristics from the datetime column using exploratory data analysis and feature engineering. The model's performance significantly improved when these additions were added.

Hyperparameter adjustment allowed for further enhancements, which greatly decreased the RMSE score and improved the predicted accuracy of the model. The WeightedEnsemble_L3, which fused several models to get the most precise predictions, was the top-performing model.


I also discovered during the assignment how crucial it is to handle negative values and format forecasts accurately for submission. All things considered, our research showed how meticulous feature engineering, data preparation, and model tuning can greatly enhance prediction results in a real-world dataset.

