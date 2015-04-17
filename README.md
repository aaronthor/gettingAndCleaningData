# gettingAndCleaningData


Getting and Cleaning Data Project Assignment Apr 2015

Data used for the project: 
https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip 

Objective of the project is to create one R script called run_analysis.R that does the following: 

1. Merges the training and the test sets to create one data set.
2. Extracts only the measurements on the mean and standard deviation for each measurement. 
3. Uses descriptive activity names to name the activities in the data set
4. Appropriately labels the data set with descriptive variable names. 
5. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.

******************************************************************************

The included R script (run_analysis.R) performs the following:
1. Merged the training and the test sets to create one data set. 
Both X_train.txt and X_test.txt training datasets are merged, achieving the resulting data frame of 10299x561 ("Number of Instances: 10299" and "Number of Attributes: 561"). Merged subject_train.txt and subject_test.txt, archiving the resulting data frame of 10299x1 with subject IDs, and y_train.txt with y_test.txt, achieving the resulting data frame of 10299x1 with activity IDs.

2. Extracts only the measurements on the mean and standard deviation for each measurement.
Extracting measurements on the mean and standard deviation from features.txt, resulting in data frame of 10299x66 since 66 out of 561 attributes are measurements on the mean and standard deviation. Note that the resulting measurements are floating numbers ranging between (-1, 1).

3. Uses descriptive activity names to name the activities in the data set
Reading from activity_labels.txt and applying descriptive activity names to activities within the data set consisting of the following:
(i)walking, (ii)walkingupstairs, (iii)walkingdownstairs, (iv)sitting, (v)standing, (vi)laying

4. Appropriately labels the data set with descriptive variable names. 
Attributes and activity names are uniformly converted to a common denorminator: all lower cased letters, with underscoring and parenthesis removed. Merging of data frame containing features and activity labels and subject IDs, and storing the output in as part4-combinedDataset.txt. Subject IDs and activity names make up the first 2 columns, and the remaining 66 columns refer to measurement readings. Note that the Subject IDs are integers in the range bewteen 1 to 30. Attribute names are:
(i)tbodyacc-mean-x, (ii)tbodyacc-mean-y, (iii)tbodyacc-mean-z, (iv)tbodyacc-std-x, (v)tbodyacc-std-y, (vi)tbodyacc-std-z, (vii)tgravityacc-mean-x, (viii)tgravityacc-mean-y

5. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.
A second independent tidy data set with the average of each measurement for each activity and each subject is created, with a data frame of 180x68 stored as part5-independentAverageActivitySubject.txt
