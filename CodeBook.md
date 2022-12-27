# Code Book
CodeBook Describes the variables, the data, and any transformations or work performed to clean up the data.

Data Source: Here are the data for the project: https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip 
A full description is available at the site where the data was obtained: http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

Data Set Description: Abstract: Human Activity Recognition database built from the recordings of 30 subjects performing activities of daily living (ADL) while carrying a waist-mounted smartphone with embedded inertial sensors.

Data Set Information:

The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data.

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain.

Data Files Inlcude:

'README.txt'
'features_info.txt': Shows information about the variables used on the feature vector.
'features.txt': List of all features.
'activity_labels.txt': Links the class labels with their activity name.
'train/X_train.txt': Training set.
'train/y_train.txt': Training labels.
'test/X_test.txt': Test set.
'test/y_test.txt': Test labels.

The following files are available for the train and test data. Their descriptions are equivalent.

'train/subject_train.txt': Each row identifies the subject who performed the activity for each window sample. Its range is from 1 to 30.
'train/Inertial Signals/total_acc_x_train.txt': The acceleration signal from the smartphone accelerometer X axis in standard gravity units 'g'. Every row shows a 128 element vector. The same description applies for the 'total_acc_x_train.txt' and 'total_acc_z_train.txt' files for the Y and Z axis.
'train/Inertial Signals/body_acc_x_train.txt': The body acceleration signal obtained by subtracting the gravity from the total acceleration.
'train/Inertial Signals/body_gyro_x_train.txt': The angular velocity vector measured by the gyroscope for each window sample. The units are radians/second.



## Actions performed on data:
* merging all *_test.txt and *_train.txt files into one dataset: `fullData`
* subsetted `fullData` into `finalData` keeping only the key columns and features containing `std` or `mean`, 
* merged `./data/UCI HAR Dataset/activity_labels.txt` contents with correct `activity_num` column, effectivly appending `activity_name` to `finalData`
* Appropriately labels the data set with descriptive variable names.
* From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.
* write to file  `./MeanData.txt`

## `MeanData` variable

### key columns

Variable name       | Description
--------------------|------------
`activity`          | Label of activity, Factor w/ 6 levels
`subject`           | ID of subject, int (1-30)
### non-key columns

Variable name       | Description
--------------------|------------
`timeBodyAccMean-X`   | the average value for this feature, num (range: -1:1)
`timeBodyAccMean-Y`   | the average value for this feature, num (range: -1:1)
`timeBodyAccMean-Z`   | the average value for this feature, num (range: -1:1)
`timeBodyAccStd-X`   | the average value for this feature, num (range: -1:1)
`timeBodyAccStd-Y`   | the average value for this feature, num (range: -1:1)
`timeBodyAccStd-Z`   | the average value for this feature, num (range: -1:1)
`tGravityAccMean-X`   | the average value for this feature, num (range: -1:1)
`tGravityAccMean-Y`   | the average value for this feature, num (range: -1:1)
`tGravityAccMean-Z`   | the average value for this feature, num (range: -1:1)
`tGravityAccStd-X`   | the average value for this feature, num (range: -1:1)
`tGravityAccStd-Y`   | the average value for this feature, num (range: -1:1)
`tGravityAccStd-Z`   | the average value for this feature, num (range: -1:1)
`timeBodyAccJerkMean-X`   | the average value for this feature, num (range: -1:1)
`timeBodyAccJerkMean-Y`   | the average value for this feature, num (range: -1:1)
`timeBodyAccJerkMean-Z`   | the average value for this feature, num (range: -1:1)
`timeBodyAccJerkStd-X`   | the average value for this feature, num (range: -1:1)
`timeBodyAccJerkStd-Y`   | the average value for this feature, num (range: -1:1)
`timeBodyAccJerkStd-Z`   | the average value for this feature, num (range: -1:1)
`timeBodyGyroMean-X`   | the average value for this feature, num (range: -1:1)
`timeBodyGyroMean-Y`   | the average value for this feature, num (range: -1:1)
`timeBodyGyroMean-Z`   | the average value for this feature, num (range: -1:1)
`timeBodyGyroStd-X`   | the average value for this feature, num (range: -1:1)
`timeBodyGyroStd-Y`   | the average value for this feature, num (range: -1:1)
`timeBodyGyroStd-Z`   | the average value for this feature, num (range: -1:1)
`timeBodyGyroJerkMean-X`   | the average value for this feature, num (range: -1:1)
`timeBodyGyroJerkMean-Y`   | the average value for this feature, num (range: -1:1)
`timeBodyGyroJerkMean-Z`   | the average value for this feature, num (range: -1:1)
`timeBodyGyroJerkStd-X`   | the average value for this feature, num (range: -1:1)
`timeBodyGyroJerkStd-Y`   | the average value for this feature, num (range: -1:1)
`timeBodyGyroJerkStd-Z`   | the average value for this feature, num (range: -1:1)
`timeBodyAccMagMean`   | the average value for this feature, num (range: -1:1)
`timeBodyAccMagStd`   | the average value for this feature, num (range: -1:1)
`tGravityAccMagMean`   | the average value for this feature, num (range: -1:1)
`tGravityAccMagStd`   | the average value for this feature, num (range: -1:1)
`timeBodyAccJerkMagMean`   | the average value for this feature, num (range: -1:1)
`timeBodyAccJerkMagStd`   | the average value for this feature, num (range: -1:1)
`timeBodyGyroMagMean`   | the average value for this feature, num (range: -1:1)
`timeBodyGyroMagStd`   | the average value for this feature, num (range: -1:1)
`timeBodyGyroJerkMagMean`   | the average value for this feature, num (range: -1:1)
`timeBodyGyroJerkMagStd`   | the average value for this feature, num (range: -1:1)
`frequenceBodyAccMean-X`   | the average value for this feature, num (range: -1:1)
`frequenceBodyAccMean-Y`   | the average value for this feature, num (range: -1:1)
`frequenceBodyAccMean-Z`   | the average value for this feature, num (range: -1:1)
`frequenceBodyAccStd-X`   | the average value for this feature, num (range: -1:1)
`frequenceBodyAccStd-Y`   | the average value for this feature, num (range: -1:1)
`frequenceBodyAccStd-Z`   | the average value for this feature, num (range: -1:1)
`frequenceBodyAccJerkMean-X`   | the average value for this feature, num (range: -1:1)
`frequenceBodyAccJerkMean-Y`   | the average value for this feature, num (range: -1:1)
`frequenceBodyAccJerkMean-Z`   | the average value for this feature, num (range: -1:1)
`frequenceBodyAccJerkStd-X`   | the average value for this feature, num (range: -1:1)
`frequenceBodyAccJerkStd-Y`   | the average value for this feature, num (range: -1:1)
`frequenceBodyAccJerkStd-Z`   | the average value for this feature, num (range: -1:1)
`frequenceBodyGyroMean-X`   | the average value for this feature, num (range: -1:1)
`frequenceBodyGyroMean-Y`   | the average value for this feature, num (range: -1:1)
`frequenceBodyGyroMean-Z`   | the average value for this feature, num (range: -1:1)
`frequenceBodyGyroStd-X`   | the average value for this feature, num (range: -1:1)
`frequenceBodyGyroStd-Y`   | the average value for this feature, num (range: -1:1)
`frequenceBodyGyroStd-Z`   | the average value for this feature, num (range: -1:1)
`frequenceBodyAccMagMean`   | the average value for this feature, num (range: -1:1)
`frequenceBodyAccMagStd`   | the average value for this feature, num (range: -1:1)
`frequenceBodyBodyAccJerkMagMean`   | the average value for this feature, num (range: -1:1)
`frequenceBodyBodyAccJerkMagStd`   | the average value for this feature, num (range: -1:1)
`frequenceBodyBodyGyroMagMean`   | the average value for this feature, num (range: -1:1)
`frequenceBodyBodyGyroMagStd`   | the average value for this feature, num (range: -1:1)
`frequenceBodyBodyGyroJerkMagMean`   | the average value for this feature, num (range: -1:1)
`frequenceBodyBodyGyroJerkMagStd`   | the average value for this feature, num (range: -1:1)
