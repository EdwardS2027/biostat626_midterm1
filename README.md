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

For the binary classifier, we first do a lasso regression on our training data to select our features. Then, we splitted the training data into 70 percent training and 30 percent validation. We fitted the logistic regression, linear discriminant analysis, SVM with linear kernel, SVM with radial kernel, neural network, and multinomial log linear model. The neural network has three hidden layers, and both of the SVM models have the cost of 10.

Below is the accuracy results of the baseline algorithms for the binary classifier:
![Screenshot 2023-04-15 181148](https://user-images.githubusercontent.com/114368995/232257795-465d3acc-1d24-454f-8d04-c4780fca673a.png)


For the multiclass classifier, we utilized the cross validation with 5 fold in our feature selection. The feature selection was composed by the Boruta Package, which is random forest classification. We also splitted the training data into 70 percent training and 30 percent validation. For model training, we choose SVM with linear kernel, SVM with radial kernel, linear discriminant analysis, and multinomial log linear model. We also hypertune the parameters for SVM, which both resulted in 15 costs.

Below is the accuracy results of the baseline algorithms for the multiclass classifier:
![Screenshot 2023-04-15 181706](https://user-images.githubusercontent.com/114368995/232257810-53758d6b-873f-4022-9bfb-b9a9ce92c445.png)


Final Algorithm:

For the binary classifier, to improve the accuracy, I used the ensemble method, which composed of all algorithms used in the baseline algorithm: logistic regression, linear discriminant analysis, SVM with linear kernel, SVM with radial kernel, neural network, and multinomial log linear model. I also hypertune the parameters for the SVM models.

Below is the accuracy results of the ensemble method and the baseline algorithms for binary:
![Screenshot 2023-04-15 191207](https://user-images.githubusercontent.com/114368995/232257827-fb6632f6-d113-4312-b241-d2563a2d2b6c.png)

For the multiclass classifier, we simply used the ensemble method like in the binary classifier to improve our accuracy. We also used cross validation in feature selection and hypertung for more optimization.

Below is the accuracy results of the ensemble method and the baseline algorithms for multiclass:


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
