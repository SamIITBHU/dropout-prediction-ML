
# Student Dropdown Prediction

This project that aims to contribute to the reduction of academic dropout and failure in higher education, by using machine learning techniques to identify students at risk at an early stage of their academic path, so that strategies to support them can be put into place.



## Acknowledgements

 - [Dataset Creators ](https://archive.ics.uci.edu/dataset/697/predict+students+dropout+and+academic+success)


## Dataset Description

The dataset includes information on academic path, demographics, and socioeconomic factors related to the students who enrolled in undergraduate degrees, such as education, nursing, and journalism at the time, as well as the students’ academic performance at the end of the first and second semesters. The ‘Target’ values were ‘dropout’, ‘enrolled’ and ‘graduate’. By using the provided features and employing **classification** techniques, I classified the data into these 3 categories.

The dataset consists of **36** features and **4,424** student records. These features encompass demographic, socioeconomic, and academic information. Demographic features include nationality, gender, age, and international student status. Socioeconomic features include marital status, parents' occupations, and tuition fee status. Academic standing features include previous degree grade, admission grade, semester grades, and acquired curricular credits. All values in the dataset are numeric, except for the "Target" column, which contains labels for dropout, enrollment, and graduation. I utilized all features in my analysis.
## Roadmap

- Prior to applying any classification model, the data underwent extensive **preprocessing** by the authors to address anomalies, unexplainable outliers, and missing values. For my part, I focused on encoding the "Target" values, scaling the data with a Standard Scaler, and dividing it into train, validation, and test sets. The test set comprised 20% of the data, while 20% of the remaining data formed the validation set. The rest constituted the training set, which consisted of 2,831 instances. The validation set contained 708 instances, and the testing set contained 885 instances.

- All **hyperparamete**r tunings were carried out on the training data, and tested on the validation data. Finally, tuned models were applied to test set to measure the success of the model.

- Four **classification algorithms** were applied; *K Nearest Neighbors (KNN)*, *Support Vector Machines (SVM)*, *SGDClassifier* (used as a Logistic Regression Classifier) and *Random Forests*. For each model, manual cross validation was performed and average and standard deviation of the scores were computed to observe whether overfitting occurred. Additionally, grid search cross validation was performed to obtain the best hyperparameters. Consequently, the models tuned with these best hyperparameters were applied on the test sets.

- Finally, as **statistic measures**, confusion matrices, classification reports and accuracy scores were printed for validation and test sets. Additionally, features that were used in decision making were plotted for each mode.
## Conclusion

- In this project, I employed four classification models to predict student outcomes, including dropout, graduation, and enrollment. I conducted cross-validation on the combined training and validation datasets for each model. Subsequently, I utilized grid search to identify the optimal hyperparameters for each model and fine-tuned them accordingly. I also identified the most influential features used by the models to make their predictions. 

- Finally, I applied the tuned models to unseen data. However, despite Random Forest yielding a high training accuracy of 94%, its performance declined when tested on validation and testing data. This indicates that Random Forest is prone to overfitting and is the most affected model among all. SVM also exhibits overfitting tendencies, although to a lesser extent compared to Random Forest. On the other hand, KNN provides the lowest accuracy among the models.

- The most generalizable model, with the highest testing accuracy, appears to be **SGD Classifier**, which behaves similarly to a Logistic Regression Classifier. While its testing accuracy of 76% is not exceptional, it still **outperforms** all other models.

- The models achieved satisfactory results for the "Dropout" and "Graduate" classes, but encountered challenges when classifying instances in the "**Enrolled**" class. This difficulty arises because the "Enrolled" class is not as exclusive as the "Dropout" and "Graduate" classes. Dropout and graduation are mutually exclusive events, implying that a student who graduated did not drop out, and vice versa. However, this exclusivity does not apply to the "Enrolled" class. A student in the "Enrolled" class can either drop out or graduate, while students who dropped out or graduated were once enrolled.

- If the dataset were divided into two classes, specifically "Graduate" and "Dropout," I believe the models would have achieved significantly **higher accuracy**.