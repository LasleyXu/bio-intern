# First Assignment
Chenghao Zhu
08/26/2018

## Study background
The egg study is a randomized, cross-over dietary intervention study that looked at the effect of 2 eggs per day versus yolk free substitute to host metabolome and gut microbiome composition. 20 subjects were randomly assigned either whole eggs or yolk free substitute as the first study arm for 4 weeks, followed by a 4 weeks washout, and then assigned to the other study arm. Blood and fecal samples were collected before and after each treatment. Each subjects went through both treatments and samples were collected on the same subject for 4 times.

Yolk is enriched in cholesterol, phospholipids, and choline. Studies shown that cholesterol and choline are able to alter gut microbiome. The gut metabolite TMAO, a gut bacterial metabolite, was also reported as a risk factor of Cardiovascular diseases.

## Files
There are two files in this folder.

1. **mx 349859_Zhu_HILIC-QTOF MSMS_11-2017_submit.xlsx**:
This is the LCMS analysis result ran by the West Coast Metabolomics Center.
2. **metadata.csv**:
This file contains the design of this study.

## Assignment detail:

1. In this very first assignemnt, you will first initialize a Rproject using RStuio, and then add files to the project. Your prject should have the structure as below:

your-project
 |
 +-- R
 |   |
 |   +-- your_analysis.Rmd
 |   +-- your_analysis.html
 |   
 +-- data_raw
 |   |
 |   +-- mx 349859_Zhu_HILIC-QTOF MSMS_11-2017_submit.xlsx
 |   +-- metadata.csv
 |
 +-- README.md
 +-- your_analysis.Rproj
 +-- gitignore

2. In RStudio, create a Rmd file, and save to the directory of "R". Read the .xlsx file and .csv file in to R, and create 3 data.frame objects, with one contains all variables of each sample, one contains all variables of each feature, and the last data.frame as a pure numeric matrix-like object, that contains only the intensity(abundance) of each feature in each sample. The dimensions of the last data.frame should be n_samples x n_features. All quality control samples should be summarized into mean, sd, and cv for each feature, and included into the feature data.frame.

3. Features that the Metabolite_name is missing should be removed. All features with a "iSTD" in the end of the Metabolite_name are internal standards. They also should be removed (for now). Features that the InChI Key is missing should also be removed.

4. Now try to answer this question. How many features have 0 missing values (observed in all samples)? How many features have 1 missing values? How many have 2, 3, 4, ...? Remove features with more than 25% of the samples are missing. And for the rest, fill up the missing values with half of the lowest value observed for this feature.

5. Print first 6 rows of the feature and sample data.frame. And print the first 6 rows and first 6 columns of the numeric concentration data.frame. Also print out the dimensions of each data.frame.

6. What is the technical variability of each features analyzed? How would we know that? (Hint: making a scatter plot with QC data, using mean of each feature as x-axis, and the cv of each feature as y-axis may help answering this question.)

7. Is TMAO effected differently by whole egg vs yolk-free substitute?

8. Knit your Rmarkdown to generate a html report.

9. Edit your gitignore file to exclude the data_raw directory, commit and push to the master. Create a new branch called "gh-pages", and push to it, too.
