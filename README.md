# Getting_and_Cleaning_Data_Course
Getting_and_Cleaning_Data_Course_Assignment
----------------------------------------------------------
##Load all the files into R studio
train_set <- read.table("./data/train/X_train.txt")
train_label <- read.table("./data/train/Y_train.txt")
subject_train <- read.table("./data/train/subject_train.txt")
test_set <- read.table("./data/test/X_test.txt")
test_label <- read.table("./data/test/Y_test.txt")
subject_test <- read.table("./data/test/subject_test.txt")
feature <- read.table("./data/features.txt")
label <- read.table("./data/activity_labels.txt")

##Set column names
colnames(test_set) <- feature[,2]
colnames(train_set) <- feature[,2]
colnames(test_label) <- "activity"
colnames(train_label) <- "activity"
colnames(subject_test) <- "ID"
colnames(subject_train) <- "ID"

##Create a data frame for each of test and train data set
test <- cbind(subject_test, test_label, test_set)
train <- cbind(subject_train, train_label, train_set)

##Create the merged data frame
data <- rbind(test, train)

##Filter for "mean" and "std"
##Subset ID, activity, and columns regarding measurements
##on the mean and standard deviation for each measurement
f <- ((grepl("[Mm]ean", names(data))) | (grepl("std", names(data))))
f_data <- select(data, ID, activity, names(data[,f]))

##Uses descriptive activity names to name the activities in the data set
f_data[,"activity"] <- as.factor(f_data[,"activity"])
levels(f_data[,"activity"]) <- label[,2]

##Labels the data set with descriptive variable names. 
names(f_data) <- gsub("[()]", "", names(f_data))
names(f_data) <- gsub("-", "_", names(f_data))

##Create a tidy data set with the average of each variable
##for each activity and each subject.
data_tibble <- as.tibble(f_data)
data_group <- group_by(data_tibble, ID, activity)
result <- summarize_all(data_group, mean)

##Write the data set as a text file   
write.table(result, row.names = FALSE, file = "result.txt")
