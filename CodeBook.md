# Code book for *Getting and Cleaning Data* course assignment

The data set that this code book pertains to is located in the `tidy_data.txt` file of this repository.

See the `README.md` file of this repository for background information on this data set.

The structure of the data set is described in the [Tidy Data](#Tidydata) section, its variables are listed in the [Variables](#variables) section, and the transformations that were carried out to obtain the data set based on the source data are presented in the [Transformations](#transformations) section.

## Tidy Data <a name="Tidydata"></a>

The `tidy_data.txt` data file is a text file, containing space-separated values.

```
tidydata<-read.table("tidy_data.txt",head=TRUE)
```
## Dimension <a name="Dimension"></a>
```
dim(tidydata)
```
```
##[1] 180  81
```

The first row contains the names of the variables, which are listed and described in the [Variables](#variables) section, and the following rows contain the values of these variables. 

## Variables <a name="variables"></a>

Each row contains, for a given subject and activity, 79 averaged signal measurements.

### Identifiers <a name="identifiers"></a>

- `subject`

	Subject identifier, integer, ranges from 1 to 30.

- `activity`

	Activity identifier, string with 6 possible values: 
	- `WALKING`: subject was walking
	- `WALKING_UPSTAIRS`: subject was walking upstairs
	- `WALKING_DOWNSTAIRS`: subject was walking downstairs
	- `SITTING`: subject was sitting
	- `STANDING`: subject was standing
	- `LAYING`: subject was laying

### Average of measurements <a name="average-measurements"></a>

All measurements are floating-point values, normalised and bounded within [-1,1].

Prior to normalisation, acceleration measurements (variables containing `Accelerometer`) were made in *g*'s (9.81 m.s⁻²) and gyroscope measurements (variables containing `Gyroscope`) were made in radians per second (rad.s⁻¹).

Magnitudes of three-dimensional signals (variables containing `Magnitude`) were calculated using the Euclidean norm.

The measurements are classified in two domains:

- Time-domain signals (variables prefixed by `timeDomain`), resulting from the capture of accelerometer and gyroscope raw signals.

- Frequency-domain signals (variables prefixed by `frequencyDomain`), resulting from the application of a Fast Fourier Transform (FFT) to some of the time-domain signals.

#### Time-domain signals

- `timeDomainBodyAccelerometerMeanX`
- `timeDomainBodyAccelerometerMeanY`
- `timeDomainBodyAccelerometerMeanZ`

- `timeDomainBodyAccelerometerStandardDeviationX`
- `timeDomainBodyAccelerometerStandardDeviationY`
- `timeDomainBodyAccelerometerStandardDeviationZ`

- `timeDomainGravityAccelerometerMeanX`
- `timeDomainGravityAccelerometerMeanY`
- `timeDomainGravityAccelerometerMeanZ`

- `timeDomainGravityAccelerometerStandardDeviationX`
- `timeDomainGravityAccelerometerStandardDeviationY`
- `timeDomainGravityAccelerometerStandardDeviationZ`

- `timeDomainBodyAccelerometerJerkMeanX`
- `timeDomainBodyAccelerometerJerkMeanY`
- `timeDomainBodyAccelerometerJerkMeanZ`

- `timeDomainBodyAccelerometerJerkStandardDeviationX`
- `timeDomainBodyAccelerometerJerkStandardDeviationY`
- `timeDomainBodyAccelerometerJerkStandardDeviationZ`

- `timeDomainBodyGyroscopeMeanX`
- `timeDomainBodyGyroscopeMeanY`
- `timeDomainBodyGyroscopeMeanZ`

- `timeDomainBodyGyroscopeStandardDeviationX`
- `timeDomainBodyGyroscopeStandardDeviationY`
- `timeDomainBodyGyroscopeStandardDeviationZ`

- `timeDomainBodyGyroscopeJerkMeanX`
- `timeDomainBodyGyroscopeJerkMeanY`
- `timeDomainBodyGyroscopeJerkMeanZ`

- `timeDomainBodyGyroscopeJerkStandardDeviationX`
- `timeDomainBodyGyroscopeJerkStandardDeviationY`
- `timeDomainBodyGyroscopeJerkStandardDeviationZ`

- `timeDomainBodyAccelerometerMagnitudeMean`
- `timeDomainBodyAccelerometerMagnitudeStandardDeviation`

- `timeDomainGravityAccelerometerMagnitudeMean`
- `timeDomainGravityAccelerometerMagnitudeStandardDeviation`

- `timeDomainBodyAccelerometerJerkMagnitudeMean`
- `timeDomainBodyAccelerometerJerkMagnitudeStandardDeviation`

- `timeDomainBodyGyroscopeMagnitudeMean`
- `timeDomainBodyGyroscopeMagnitudeStandardDeviation`

- `timeDomainBodyGyroscopeJerkMagnitudeMean`
- `timeDomainBodyGyroscopeJerkMagnitudeStandardDeviation`

#### Frequency-domain signals

- `frequencyDomainBodyAccelerometerMeanX`
- `frequencyDomainBodyAccelerometerMeanY`
- `frequencyDomainBodyAccelerometerMeanZ`

- `frequencyDomainBodyAccelerometerStandardDeviationX`
- `frequencyDomainBodyAccelerometerStandardDeviationY`
- `frequencyDomainBodyAccelerometerStandardDeviationZ`

- `frequencyDomainBodyAccelerometerMeanFrequencyX`
- `frequencyDomainBodyAccelerometerMeanFrequencyY`
- `frequencyDomainBodyAccelerometerMeanFrequencyZ`

- `frequencyDomainBodyAccelerometerJerkMeanX`
- `frequencyDomainBodyAccelerometerJerkMeanY`
- `frequencyDomainBodyAccelerometerJerkMeanZ`

- `frequencyDomainBodyAccelerometerJerkStandardDeviationX`
- `frequencyDomainBodyAccelerometerJerkStandardDeviationY`
- `frequencyDomainBodyAccelerometerJerkStandardDeviationZ`

- `frequencyDomainBodyAccelerometerJerkMeanFrequencyX`
- `frequencyDomainBodyAccelerometerJerkMeanFrequencyY`
- `frequencyDomainBodyAccelerometerJerkMeanFrequencyZ`

- `frequencyDomainBodyGyroscopeMeanX`
- `frequencyDomainBodyGyroscopeMeanY`
- `frequencyDomainBodyGyroscopeMeanZ`

- `frequencyDomainBodyGyroscopeStandardDeviationX`
- `frequencyDomainBodyGyroscopeStandardDeviationY`
- `frequencyDomainBodyGyroscopeStandardDeviationZ`

- `frequencyDomainBodyGyroscopeMeanFrequencyX`
- `frequencyDomainBodyGyroscopeMeanFrequencyY`
- `frequencyDomainBodyGyroscopeMeanFrequencyZ`

- `frequencyDomainBodyAccelerometerMagnitudeMean`
- `frequencyDomainBodyAccelerometerMagnitudeStandardDeviation`
- `frequencyDomainBodyAccelerometerMagnitudeMeanFrequency`

- `frequencyDomainBodyAccelerometerJerkMagnitudeMean`
- `frequencyDomainBodyAccelerometerJerkMagnitudeStandardDeviation`
- `frequencyDomainBodyAccelerometerJerkMagnitudeMeanFrequency`

- `frequencyDomainBodyGyroscopeMagnitudeMean`
- `frequencyDomainBodyGyroscopeMagnitudeStandardDeviation`
- `frequencyDomainBodyGyroscopeMagnitudeMeanFrequency`

- `frequencyDomainBodyGyroscopeJerkMagnitudeMean`
- `frequencyDomainBodyGyroscopeJerkMagnitudeStandardDeviation`
- `frequencyDomainBodyGyroscopeJerkMagnitudeMeanFrequency`

## Transformations <a name="transformations"></a>

The zip file containing the source data is located [here](https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip).

The following transformations were applied to the source data:

#### 1. Merging the training and the test sets to create one data set:

Reading files
```
# read training data
trainingSubjects <- read.table(file.path(dataPath, "train", "subject_train.txt"))
trainingValues <- read.table(file.path(dataPath, "train", "X_train.txt"))
trainingActivity <- read.table(file.path(dataPath, "train", "y_train.txt"))

# read test data
testSubjects <- read.table(file.path(dataPath, "test", "subject_test.txt"))
testValues <- read.table(file.path(dataPath, "test", "X_test.txt"))
testActivity <- read.table(file.path(dataPath, "test", "y_test.txt"))

# read features, don't convert text labels to factors
features <- read.table(file.path(dataPath, "features.txt"), as.is = TRUE)

# read activity labels
activities <- read.table(file.path(dataPath, "activity_labels.txt"))
colnames(activities) <- c("activityId", "activityLabel")
```

Merging all data in one set:
```
# concatenate individual data tables to make single data table
humanActivity <- rbind(
  cbind(trainingSubjects, trainingValues, trainingActivity),
  cbind(testSubjects, testValues, testActivity)
)

# remove individual data tables to save memory
rm(trainingSubjects, trainingValues, trainingActivity, 
   testSubjects, testValues, testActivity)

# assign column names
colnames(humanActivity) <- c("subject", features[, 2], "activity")
```

#### 2. Extracts only the measurements on the mean and standard deviation for each measurement.

```
# determine columns of data set to keep based on column name...
columnsToKeep <- grepl("subject|activity|mean|std", colnames(humanActivity))

# ... and keep data in these columns only
humanActivity <- humanActivity[, columnsToKeep]

```

#### 3. Use descriptive activity names to name the activities in the data set.

```
# replace activity values with named factor levels
humanActivity$activity <- factor(humanActivity$activity, 
                                 levels = activities[, 1], labels = activities[, 2])

```

#### 4. Appropriately labels the data set with descriptive variable names.

```
# get column names
humanActivityCols <- colnames(humanActivity)

# remove special characters
humanActivityCols <- gsub("[\\(\\)-]", "", humanActivityCols)

# expand abbreviations and clean up names
humanActivityCols <- gsub("^f", "frequencyDomain", humanActivityCols)
humanActivityCols <- gsub("^t", "timeDomain", humanActivityCols)
humanActivityCols <- gsub("Acc", "Accelerometer", humanActivityCols)
humanActivityCols <- gsub("Gyro", "Gyroscope", humanActivityCols)
humanActivityCols <- gsub("Mag", "Magnitude", humanActivityCols)
humanActivityCols <- gsub("Freq", "Frequency", humanActivityCols)
humanActivityCols <- gsub("mean", "Mean", humanActivityCols)
humanActivityCols <- gsub("std", "StandardDeviation", humanActivityCols)

# correct typo
humanActivityCols <- gsub("BodyBody", "Body", humanActivityCols)

# use new labels as column names
colnames(humanActivity) <- humanActivityCols

```
The variable names were replaced with descriptive variable names using the following set of rules:

	- Special characters (i.e. `(`, `)`, and `-`) were removed
	- The initial `f` and `t` were expanded to `frequencyDomain` and `timeDomain` respectively.
	- `Acc`, `Gyro`, `Mag`, `Freq`, `mean`, and `std` were replaced with `Accelerometer`, `Gyroscope`, `Magnitude`, `Frequency`, `Mean`, and `StandardDeviation` respectively.
	- Replaced (supposedly incorrect as per source's `features_info.txt` file) `BodyBody` with `Body`.

#### 5. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.
```
# group by subject and activity and summarise using mean
humanActivityMeans <- humanActivity %>% 
  group_by(subject, activity) %>%
  summarise_all(funs(mean))

# output to file "tidy_data.txt"
write.table(humanActivityMeans, "tidy_data.txt", row.names = FALSE, 
            quote = FALSE)
```

The collection of the source data and the transformations listed above were implemented by the `run_analysis.R` R script (see `README.md` file for usage instructions).
