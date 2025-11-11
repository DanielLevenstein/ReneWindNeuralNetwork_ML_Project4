# Project Info
- Class: Introduction to Neural Networks
- Submission Date: 9/10/2025
- Author: Daniel Levenstein

## Objective
“ReneWind” is a company working on improving the machinery/processes involved in the production of wind energy using machine learning and has collected data of generator failure of wind turbines using sensors. They have shared a ciphered version of the data, as the data collected through sensors is confidential (the type of data collected varies with companies). Data has 40 predictors, 20000 observations in the training set and 5000 in the test set.

The objective is to build various classification models, tune them, and find the best one that will help identify failures so that the generators could be repaired before failing/breaking to reduce the overall maintenance cost.
The nature of predictions made by the classification model will translate as follows:

- True positives (TP) are failures correctly predicted by the model. These will result in repairing costs.
- False negatives (FN) are real failures where there is no detection by the model. These will result in replacement costs.
- False positives (FP) are detections where there is no failure. These will result in inspection costs.

It is given that the cost of repairing a generator is much less than the cost of replacing it, and the cost of inspection is less than the cost of repair.

“1” in the target variables should be considered as “failure” and “0” represents “No failure”.
## Data Description
The data provided is a transformed version of the original data which was collected using sensors.

- Train.csv - To be used for training and tuning of models.
- Test.csv - To be used only for testing the performance of the final best model.
- Debug.csv - Consists of the first 100 rows of the training dataset. 

Both the datasets consist of 40 predictor variables and 1 target variable.

## Methodology
- In this project, I created multiple models to expect the part replacement schedule in a factory. 
- One of the challenges of this project was which model came up on top changed based on which random sead was used for the project.

### Conclusion
- Adam preformed better than SDG when fewer epochs were allowed, but when more training was done, SDG came out ahead.
- Adding more layers increases model performance.
- Attempting to manually tune the model learning rate made the performance worse.
- The performance of these two models was similar, but the SDG model looks more stable based on the graph. 
- The final model has an MSE of about 1%
- When the model was already performing well, additional training did not improve outcomes. 

[Download Results](models/best_models.csv)
# **Actionable Insights and Recommendations**

Write down some insights and business recommendations based on your observations.

I would recommend the client deploy model5 to production which was built with the following parameters.
- Batch Size: 100
- 3 Hidden Layers
- SGD optimization function
- Fifty epochs of training