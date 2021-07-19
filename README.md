## Description of the script inlcuded in the "run_analysis.R" file
***dply, tibble, tidlyr** packages need to be loaded.

First, it loads all the data into R program using ***read.table()*** function.
Then, it renames the column names of the loaded tables using ***colnames()*** function.
After that, it creates a merged data set using ***cbind() and rbind()*** functions.
Then it subsets ID, activity, and columns regarding measurements on the mean and standard deviation for each measurement using ***grepl() and select()*** functions.
After that, it uses descriptive activity names to name the activities in the data set by using ***as.factor() and levels()*** functions.
Then it labels the data set with descriptive variable names. It simply subsutitues "-" with "-" and remove "()" to make descriptive variable names.
And it creates a tidy data set using ***as.tibble(), group_by() and summarize_all()*** functions.
Finally, it Write the data set as a text file using ***write.table()*** function. The result is saved as "result.txt".
