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

## Binary Classifier:

First, the data will be loaded and be cleaned by having it features named correctly. Next, the outcomes was also created and loaded correctly as well.
cv.glmnet will be used to create lasso regression for feature selection. In this feature selection, there was no cross validation or training data being splitted, because there was high accuracy in the training and testing predictions, and time mananagement was important.

For model training,hold one leave one out validation was used where random 70 percent of the training data was used as training, while the last 30 percent was used as validation. Linear discrimnant analysis, SVM with linear kernel, logistic regression, SVM with radial kernel, neural network and multinomial log-linear via neural networks were used for training. Finally we used majority for all of these models to decide on the final predictions to create ensemble method and training error. 

We also hypertune SVM with radial and linear kernels.

Once we get good training accuracy, we will use the models on the testing data and print into text file.

## Multiclass Classifier

Note the multiclass classifer steps are same as that of binary classifer, except for feature selection and models chosen.

First, the data will be loaded and be cleaned by having it features named correctly. Next, the outcomes was also created and loaded correctly as well.
cv.glmnet will be used to create lasso regression for feature selection. In this feature selection, there was no cross validation or training data being splitted, because there was high accuracy in the training and testing predictions, and time mananagement was important.

For model training,hold one leave one out validation was used where random 70 percent of the training data was used as training, while the last 30 percent was used as validation. Linear discrimnant analysis, SVM with linear kernel, logistic regression, SVM with radial kernel, neural network and multinomial log-linear via neural networks were used for training. Finally we used majority for all of these models to decide on the final predictions to create ensemble method and training error. 

We also hypertune SVM with radial and linear kernels.

Once we get good training accuracy, we will use the models on the testing data and print into text file.
