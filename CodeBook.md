Download the dataset
Dataset downloaded and in the folder called UCI HAR Dataset

Assign data to variables
features <- features.txt : 561 rows, 2 columns
The features selected for this database come from tAcc-XYZ and tGyro-XYZ.
activities <- activity_labels.txt : 6 rows, 2 columns
Activities performed when measurements were taken and its labels
subject_test <- test/subject_test.txt : 2947 rows, 1 column
has test data of 9/30 test subjects observed
x_test <- test/X_test.txt : 2947 rows, 561 columns
has recorded features data
y_test <- test/y_test.txt : 2947 rows, 1 columns
has test data of activities code labels
subject_train <- test/subject_train.txt : 7352 rows, 1 column
has train data of 21/30 volunteer subjects observed
x_train <- test/X_train.txt : 7352 rows, 561 columns
has recorded features training data
y_train <- test/y_train.txt : 7352 rows, 1 columns
has training data of activites code labels

Merge training and test datasets to make a single dataset
X (10299 rows, 561 columns) created by merging x_train and x_test using rbind()
Y (10299 rows, 1 column) created by merging y_train and y_test using rbind()
Subject (10299 rows, 1 column) created by merging subject_train and subject_test using rbind()
Merged_Data (10299 rows, 563 column) created by merging Subject, Y and X using cbind()

Takes the mean and standard deviation for each measurement
TidyData (10299 rows, 88 columns) created by subsetting Merged_Data, selecting columns: subject, code and the mean and standard deviation (std) for each measurement

Uses descriptive words to name the activities in dataset
Numbers in code column of TidyData subbed with activity taken from second column of the activities variable

Labels the dataset with descriptive names
code column in TidyData renamed into activities
All Acc in column’s name replaced by Accelerometer
All Gyro in column’s name replaced by Gyroscope
All BodyBody in column’s name replaced by Body
All Mag in column’s name replaced by Magnitude
All start with character f in column’s name replaced by Frequency
All start with character t in column’s name replaced by Time

From step four, creates second independent tidy dataset with the average of each variable for each activity and each subject
FinalData (180 rows, 88 columns) is created by summarizing TidyData taking the means of each variable for each activity and each subject, after grouped by subject and activity.
Export FinalData into FinalData.txt file.
