## CodeBook

`run_analysis.R` script downloads and performs the data preparation required for this project

## Downloading of the dataset
Download and unzip raw data to the folder "UCI HAR Dataset"


## Assign data to relevant variables

features <- features.txt
561 rows, 2 columns
The features comes from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ.

activities <- activity_labels.txt
6 rows, 2 columns
List of activities performed when the corresponding measurements were taken and its codes (labels)

subject_test <- test/subject_test.txt
2947 rows, 1 column
Test data of 9/30 observed test subjects

x_test <- test/X_test.txt
2947 rows, 561 columns
Recorded features of test data

y_test <- test/y_test.txt
2947 rows, 1 columns
Test data of activities code labels

x_train <- test/X_train.txt
7352 rows, 561 columns
Recorded features of train data

y_train <- test/y_train.txt : 7352 rows, 1 columns
contains train data of activities’code labels

subject_train <- test/subject_train.txt
7352 rows, 1 column
Train data of 21/30 observed train subjects


## Joining the train and the test set into Merged_Data

X <- Created by merging x_train and x_test using rbind() function (10299 rows, 561 columns)

Y <- Created by merging y_train and y_test using rbind() function (10299 rows, 1 column) 

Subject <- Created by merging subject_train and subject_test using rbind() function (10299 rows, 1 column)

Merged_Data <- Created by merging Subject, X and Y using cbind() function (10299 rows, 563 column)


## Extracts only the measurements on the Mean and SD for each measurement

TidyData <- Created by subsetting Merged_Data, selecting only columns "subject", "code" and the measurements on the Mean and SD (std) for each measurement (10299 rows, 88 columns)


## Add descriptive activity names to replace activities IDs

All numbers in "code" column of the TidyData are replaced with corresponding activity from second column of the activities variable


## Appropriately name the data set with descriptive variable names

"code" column in TidyData renamed into "activity"

"Acc" in columns name changed to "Accelerometer"

"Gyro" in columns name changed to "Gyroscope"

"BodyBody" in columns name changed to "Body"

"Mag" in columns name changed to "Magnitude"

What starts with character "f" in columns name changed to "Frequency"

What starts with character "t" in columns name changed to "Time"


## Create a second, independent tidy data set with the average of each variable for each activity and each subject

EndData is created by sumarizing TidyData taking the means of each variable for each activity and each subject groupped by activity and subject (in that order).

Export EndData into EndData.txt file (180 rows, 88 columns) 
