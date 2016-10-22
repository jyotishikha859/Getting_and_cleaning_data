# Getting_and_cleaning_data

One of the most exciting areas in all of data science right now is wearable computing - see for example this article . Companies like Fitbit, Nike, and Jawbone Up are racing to develop the most advanced algorithms to attract new users. The data linked to from the course website represent data collected from the accelerometers from the Samsung Galaxy S smartphone. A full description is available at the site where the data was obtained:

[site](http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones)

Here are the data for the project:
[data](https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip)
You should create one R script called run_analysis.R that does the following.

1. Merges the training and the test sets to create one data set.
2. Extracts only the measurements on the mean and standard deviation for each measurement.
3. Uses descriptive activity names to name the activities in the data set
4. Appropriately labels the data set with descriptive variable names.
5. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each   subject.

##Steps to produce this project

1. When sourced, the script checks if the required R packages are available and proceeds to install them if they are not found
 Calling download.data() downloads the zipped dataset and unarchives it.
2. Feature vector label data is loaded from features.txt
3. Activity labels are loaded from features.txt
4. Activity labels and selected features are given as parameters to function which loads the training or test  dataset, based on the type value given also as a parameter.
5. Paths to data files are created based on type parameter
6. Data files are loaded. Feature vector data is filtered using ids of the selected features.
7. Activity and subject id data are loaded
8. Feature vector data is renamed using the names of selected features
9. Activies and subjects are given labels using factor levels of activity and subject data.
10. Finally, processed dataset is returned.
 (The previous processing is repeated to both training and test datasets.)
 Training and test datasets are merged using rbind() and converted to data.table to make it easier to do groupwise operations in the  following step
11. Mean is calculated for all variables for each activity and subject
12. Variable names are loaded to separate vector and tidied.
13. New names are applied to dataset
14. Tidy dataset is written to disk
