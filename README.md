## Description of the script inlcuded in the "run_analysis.R" file

Note: ***dply, tibble, tidlyr** packages need to be loaded.

1. First, it loads all the data into R program using ***read.table()*** function.  
2. Then, it renames the column names of the loaded tables using ***colnames()*** function.  
3. After that, it creates a merged data set using ***cbind() and rbind()*** functions.  
4. Then it subsets ID, activity, and columns regarding measurements on the mean and standard deviation for each measurement using ***grepl() and select()*** functions.  
5. After that, it uses descriptive activity names to name the activities in the data set by using ***as.factor() and levels()*** functions.  
6. Then it labels the data set with descriptive variable names. It simply subsutitues "-" with "-" and remove "()" to make descriptive variable names.  
7. And it creates a tidy data set using ***as.tibble(), group_by() and summarize_all()*** functions.  
8. Finally, it Write the data set as a text file using ***write.table()*** function. The result is saved as "result.txt".  

## Code book
 [1] "ID": Volunteer ID in the range of 1 - 30  
 [2] "activity": Activity; one of the follwing six (6) activities   
"WALKING" / "WALKING_UPSTAIRS" / "WALKING_DOWNSTAIRS" / "SITTING" / "STANDING" / "LAYING"    
 
***The follwing variables (Column 3 thorugh Column 88) are measurements on the mean and standard deviation for each measurment***  
  [3] "tBodyAcc_mean_X"                    "tBodyAcc_mean_Y"                     
  [5] "tBodyAcc_mean_Z"                    "tBodyAcc_std_X"                      
  [7] "tBodyAcc_std_Y"                     "tBodyAcc_std_Z"                      
  [9] "tGravityAcc_mean_X"                 "tGravityAcc_mean_Y"                  
 [11] "tGravityAcc_mean_Z"                 "tGravityAcc_std_X"                   
 [13] "tGravityAcc_std_Y"                  "tGravityAcc_std_Z"                   
 [15] "tBodyAccJerk_mean_X"                "tBodyAccJerk_mean_Y"                 
 [17] "tBodyAccJerk_mean_Z"                "tBodyAccJerk_std_X"                  
 [19] "tBodyAccJerk_std_Y"                 "tBodyAccJerk_std_Z"                  
 [21] "tBodyGyro_mean_X"                   "tBodyGyro_mean_Y"                    
 [23] "tBodyGyro_mean_Z"                   "tBodyGyro_std_X"                     
 [25] "tBodyGyro_std_Y"                    "tBodyGyro_std_Z"                     
 [27] "tBodyGyroJerk_mean_X"               "tBodyGyroJerk_mean_Y"                
 [29] "tBodyGyroJerk_mean_Z"               "tBodyGyroJerk_std_X"                 
 [31] "tBodyGyroJerk_std_Y"                "tBodyGyroJerk_std_Z"                 
 [33] "tBodyAccMag_mean"                   "tBodyAccMag_std"                     
 [35] "tGravityAccMag_mean"                "tGravityAccMag_std"                  
 [37] "tBodyAccJerkMag_mean"               "tBodyAccJerkMag_std"                 
 [39] "tBodyGyroMag_mean"                  "tBodyGyroMag_std"                    
 [41] "tBodyGyroJerkMag_mean"              "tBodyGyroJerkMag_std"                
 [43] "fBodyAcc_mean_X"                    "fBodyAcc_mean_Y"                     
 [45] "fBodyAcc_mean_Z"                    "fBodyAcc_std_X"                      
 [47] "fBodyAcc_std_Y"                     "fBodyAcc_std_Z"                      
 [49] "fBodyAcc_meanFreq_X"                "fBodyAcc_meanFreq_Y"                 
 [51] "fBodyAcc_meanFreq_Z"                "fBodyAccJerk_mean_X"                 
 [53] "fBodyAccJerk_mean_Y"                "fBodyAccJerk_mean_Z"                 
 [55] "fBodyAccJerk_std_X"                 "fBodyAccJerk_std_Y"                  
 [57] "fBodyAccJerk_std_Z"                 "fBodyAccJerk_meanFreq_X"             
 [59] "fBodyAccJerk_meanFreq_Y"            "fBodyAccJerk_meanFreq_Z"             
 [61] "fBodyGyro_mean_X"                   "fBodyGyro_mean_Y"                    
 [63] "fBodyGyro_mean_Z"                   "fBodyGyro_std_X"                     
 [65] "fBodyGyro_std_Y"                    "fBodyGyro_std_Z"                     
 [67] "fBodyGyro_meanFreq_X"               "fBodyGyro_meanFreq_Y"                
 [69] "fBodyGyro_meanFreq_Z"               "fBodyAccMag_mean"                    
 [71] "fBodyAccMag_std"                    "fBodyAccMag_meanFreq"                
 [73] "fBodyBodyAccJerkMag_mean"           "fBodyBodyAccJerkMag_std"             
 [75] "fBodyBodyAccJerkMag_meanFreq"       "fBodyBodyGyroMag_mean"               
 [77] "fBodyBodyGyroMag_std"               "fBodyBodyGyroMag_meanFreq"           
 [79] "fBodyBodyGyroJerkMag_mean"          "fBodyBodyGyroJerkMag_std"            
 [81] "fBodyBodyGyroJerkMag_meanFreq"      "angletBodyAccMean,gravity"           
 [83] "angletBodyAccJerkMean,gravityMean"  "angletBodyGyroMean,gravityMean"      
 [85] "angletBodyGyroJerkMean,gravityMean" "angleX,gravityMean"                  
 [87] "angleY,gravityMean"                 "angleZ,gravityMean"  
