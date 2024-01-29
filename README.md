# User_Vehicle_Insurance_Classification

Given training dataset consisting information about **101891 car insurance quotes data** in 'Cooperators_Quotes_Dataset_Training.xlsx' and some test data in 'Cooperators_Quotes_Dataset_Test.xlsx' to predict whether the individual who asked for the quote actually took the insurance policy.

The training dataset contains **25 feature columns** (e.g. QUOTE_DATE, VEHICLE_MAKE etc) and a **target column 'IS_BOUND'**. Our task is to predict the target column 'IS_BOUND' on the given test dataset.


* First, we **loaded the training and test dataset** and  applied pre-processing after **combining the test and train** dataset to encode the for similar preprocessing of train and test data.
* To handle with missing values, we **dropped the columns that has high proportions of missing values**(above 90%).
* **Imputing some columns with NAN** values by **most frequent value** or **group-wise mean** was one of the data filling method for empty rows.
* For **categorical columns**, each unique category was converted into columns by **applying one hot encoding** to convert it into numerical values.
* Also, **Identifying the outliers** by checking out the relations and observing the data points by visualising them into the scatter plot helped to remove the influential points that can be diverting the prediction value from the actual output.
* After pre-processing of dataset, we trained the models for predictions which are :
  * **Logistic regression model** where hyperparameter tuning was tried by modyfying the weight of the target categories(i.e.: 1 and 0).
  * **Naive bayes**  by trying to to predict the binary outcome after ensuring the numeric features are standardized and checking out the best prediction accuracy by modying the value of alpha.
* Additionally, we applied **standardization to numeric features** to have a consistent scale which was then used by the model sto predict the target column and also calcualte the overall performance of the model.
* **Plotting ROC curves** for both the logistic regression model and naive bayes model helped us to understand whether the model is actually predicting the outputs or predicting by randomly section the output. By looking at the plots, we can say that since the AUC(Area Under the ROC Curve) for **naive bayes model is higher** than that of logistic regression model, **Naive bayes model provides better prediction** than logistic regression model. Because, higher AUC represents the better overall performance of the model.

We submitted the predcited values for the given test dataset to the leaderboard. The outcome that got is as follows:


*   ***Logistic Regression model***:
  * Accuracy: 61,
  * False positive rate percent: 31,
  * False negative rate percent: 66,
  * Revenue: 1

*   **Naive Bayes model(FINAL CONSIDERED MODEL):**
  * Accuracy: 52,
  * False positive rate percent : 51,
  * False negative rate percent: 29,
  * **Revenue: 16**


**FINAL CONSIDERED MODEL :** Naive Bayes has been considered as the final predicting model as it displays the capability to predict and differentiate the response feature with an auc score of 0.65.


