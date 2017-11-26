# Introduction

The script `run_analysis.R`performs the 5 steps described in the assignment:

* First, all the similar data is merged using the `rbind()` function. By similar, those files are addressed which have the same number of columns and referring to the same entities.
* Next, those columns with the mean and standard deviation measures are taken from the dataset. After extracting these columns, their names are replaced with correct names, taken from `features.txt`.
* Activity data is addressed with values 1:6. The activity names and IDs are extracted from `activity_labels.txt` and they are substituted in the dataset.
* Those columns within the dataset with vague column names are corrected.
* Finally, a new dataset is produced with all the average measures for each subject and activity type (30 subjects * 6 activities = 180 rows). The output file is called `averages_data.txt`, and has been uploaded to this repository.

# Variables

* `x_train`, `y_train`, `x_test`, `y_test`, `subject_train` and `subject_test` contain the data from the downloaded files.
* `x_data`, `y_data` and `subject_data` merge the previous datasets for further analysis.
* `features` contains the correct names for the `x_data` dataset, which are applied to the column names stored in `mean_and_std_features`.
* A similar approach is taken with activity names through the `activities` variable.
* `all_data` merges `x_data`, `y_data` and `subject_data` in a big dataset.
* Finally, `averages_data` contains the relevant averages which will be later stored in a `.txt` file. `ddply()` from the plyr package is used to apply `colMeans()` and improve the development.
