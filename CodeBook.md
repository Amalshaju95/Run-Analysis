CODE BOOK
The below Function creates a tidy dataset from the given file and is named run_analysis.R
1.	The data set “ UCI HAR Dataset “ is downloaded from the link provided
2.	The downladed files are assigned to different dataframes
o	features <- features.txt : 561 rows, 2 columns
o	activities <- activity_labels.txt : 6 rows, 2 columns
o	subject_test <- test/subject_test.txt : 2947 rows, 1 column
o	x_test <- test/X_test.txt : 2947 rows, 561 columns
o	y_test <- test/y_test.txt : 2947 rows, 1 columns
o	subject_train <- test/subject_train.txt : 7352 rows, 1 column
o	x_train <- test/X_train.txt : 7352 rows, 561 columns
o	y_train <- test/y_train.txt : 7352 rows, 1 columns
3.	As menstioned in question the datasets from test and train are combined together
o	X (10299 rows, 561 columns) is created by merging x_train and x_test using rbind() function
o	Y (10299 rows, 1 column) is created by merging y_train and y_test using rbind() function
o	Subject (10299 rows, 1 column) is created by merging subject_train and subject_test using rbind() function
o	Final_Data (10299 rows, 563 column) is created by merging Subject, Y and X using cbind() function
4.	The mean and standard deviation from each file is being extracted
o	TidyData (10299 rows, 88 columns) is created by subsetting Final_Data, selecting only columns: subject, code and the measurements on the mean and standard deviation (std) for each measurement
5.	Uses descriptive activity names to name the activities in the data set
o	Entire numbers in code column of the TidyData replaced with corresponding activity taken from second column of the activities variable
6.	Labelling  the data set with descriptive variable names
o	code column in TidyData renamed into activities
o	All Acc in column’s name replaced by Accelerometer
o	All Gyro in column’s name replaced by Gyroscope
o	All BodyBody in column’s name replaced by Body
o	All Mag in column’s name replaced by Magnitude
o	All start with character f in column’s name replaced by Frequency
o	All start with character t in column’s name replaced by Time
7.	From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject
o	Output (180 rows, 88 columns) is created by sumarizing TidyData taking the means of each variable for each activity and each subject, after groupped by subject and activity.
o	Export Output into Output.txt file.



