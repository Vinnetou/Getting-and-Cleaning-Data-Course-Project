# Getting-and-Cleaning-Data-Course-Project
  Getting and Cleaning Data Course Project - Coursera - JHU

- Collecting and cleaning a data set. The goal is to prepare tidy data that can be used for later analysis. 
- Raw data:   https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip
- Full description of the raw dataset and its variables: http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

Only the following files from the initial dataset are used:
  1. ***features.txt*** - measured futures description
  2. ***train/X_train.txt*** - features measurements of train set (561 features)
  3. ***train/y_train.txt*** - activity id for each measurement in the train set
  4. ***train/subject_train.txt*** - subject for each measurement in the train set
  5. ***test/X_test.txt*** - features measurements of test set
  6. ***test/y_test.txt*** - activity id for each measurement in the test set
  7. ***test/subject_test.txt*** - subject for each measurement in the test set
 
# Files
- `CodeBook.md` data and variables descritpion, comments to expalin my work to clean and prepare the dataset.

- `run_analysis.R` has all the code of collecting and pre-processing the dataset to finish this project.

- `exportedtidydata.txt` is a text file output from `run_analysis.R`

# How script works
  `run_analysis.R` performs 6 steps required as described in the course project definition:
  1. Merge the training set and the test set to create one joined data set
  2. Extracts only the measurements on Mean and Standard Deviation for each measurement
  3. Add descriptive activity names to replace the activities IDs in the joined data set
  4. Appropriately name the data set with descriptive variable names
  5. Create a second, independent tidy data set with the average of each variable for each activity and each subject
  6. `exportedtidydata.txt` are the exported data after going through all the steps described above
