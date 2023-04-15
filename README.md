# biostat626_midterm1

## Software:
Rstudio - R 4.1.1

## Packages/Libraries:
neuralnet

e1071

glmnet

nnet

Boruta

ranger

MASS

## Binary Classifier Instructions:

First, the data will be loaded and be cleaned by having it features named correctly. Next, the outcomes was also created and loaded correctly as well. The outcomes should be marked correctly as either 0 or 1 depending the target column.

Cv.glmnet will be used to create lasso regression for feature selection. In this feature selection, there was no cross validation or training data being splitted, because there was high accuracy in the training and testing predictions, and time mananagement was important.

For model training,hold one leave one out validation was used where random 70 percent of the training data was used as training, while the last 30 percent was used as validation. Linear discrimnant analysis, SVM with linear kernel, logistic regression, SVM with radial kernel, neural network and multinomial log-linear via neural networks were used for training. Finally we used majority for all of these models to decide on the final predictions to create ensemble method and training error. 

We also hypertune SVM with radial and linear kernels.

Once we get good training accuracy, we will use the models on the testing data and print into text file.

## Multiclass Classifier Instructions:

Note the multiclass classifer steps are same as that of binary classifer, except for feature selection and models chosen.

First, the data will be loaded and be cleaned by having it features named correctly.  Next, the outcomes was also created and loaded correctly as well. The outcomes should be marked correctly as either 1-7 depending the target column.

Next, the outcomes was also created and loaded correctly as well.
Boruta package(wrapper algorithm revolved around random forest) will be used to create random forest selection. In this feature selection, the training data was splitted into 5 different random groups, and each group was used for feature selection. This is to help prevent overfitting and save time used in the feature selection.

For model training,hold one leave one out validation was used where random 70 percent of the training data was used as training, while the last 30 percent was used as validation. Linear discrimnant analysis, SVM with linear kernel, SVM with radial kernel, and multinomial log-linear via neural networks were used for training. Finally we used majority for all of these models to decide on the final predictions to create ensemble method and training error. 

We also hypertune SVM with radial and linear kernels.

Once we get good training accuracy, we will use the models on the testing data and print into text file.

Baseline Algorithm:

Final Algorithm:

Leaderboard Performance:

Here is the accuracy result of the models being used on the training data:
![Screenshot 2023-04-15 140702](https://user-images.githubusercontent.com/114368995/232246371-532801c3-7b3b-4eb6-a4e1-8e9af2c5345a.png)


Here is the accuracy result of the models being used on the testing data:
![image](https://user-images.githubusercontent.com/114368995/232246296-dabf5203-156f-4cb8-9bde-aa0a387f8372.png)


While the performances of both binary classifiers are the same, we tried to improve the performance of the multiclass classifier by utilizing cross validation in feature selection and using the Boruta package. This is because the testing performance was lower than the training performance, which was due to overfitting. We tried to overcome this issue through cross validation. Furthermore, due to complexity caused by the multiclass data, we used the Boruta package to select our features.
## Future Directions / Improvements:
The multiclass model significantly required a large amount of time to select features for model training. We can possibly look at PCA over the Boruta package used. The PCA will reduce a large amount of dimensionality represented by the data. This will improve our accuracy.

Additionally, for model training, insteading of using hold one leave one out set, we can look into 5 or 10 fold cross validation. This can help give us a true accuracy of our model and prevent overfitting.

Lastly, we should also do more hypertuning of the parameters in our models. This will tailor our models to the data to get better accuracy.
