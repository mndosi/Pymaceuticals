## Pymaceuticals

### Prep: Importing Dependencies, Reading data into Dataframes, Merging to One Dataframe

1. Using the provided code, I imported the dependencies.

2. I studied the data and setup paths for the mouse metadata and the study results.

3. Used Pandas to read the mouse data and the study results into two distinct dataframes.

4. Merged dataframes into one dataframe - `mouse_study_df`

### Cleaning the Data

1. I checked the number of mice.

2. I set up a variable to identify the columns I wanted to call, and 

3. I used `dup_s = mouse_study_df.duplicated(dup_columns)` and `dup_s.sum()`  and `dup_mice = mouse_study_df[dup_s]['Mouse ID'].unique()` to identify the duplicated data and the unique Mouse ID's in the duplicated data.

4. I made a Dataframe of the duplicated mouse info to identify all data associated with the one duplicated mouse. - `dup_mice_s = mouse_study_df["Mouse ID"].isin(dup_mice)`

5. I made a clean DataFrame by dropping the Mouse with duplicated data using `clean_mouse_study_df = mouse_study_df[~dup_mice_s]` .

6. Then I checked the length of the new DataFrame to be sure the dup mouse had been dropped.

### Summary Statistics

1. I used groupby and summary statistical methods to calculate the following properties of each drug regimen:  mean, median, variance, standard deviation, and SEM of the tumor volume.

2. I assembled the resulting series into a single summary DataFrame.

3. Generated a summary statistics DataFrame of mean, median, variance, standard deviation, and SEM of the tumor volume for each regimen - `sum_stats_df`.

4. Used the aggregation method to produce the same summary statistics in a single line.

### Bar and Pie Plots
To generate a bar plot showing the total number of timepoints for all mice tested for each drug regimen using Pandas

1. Grouped dataset by Drug Regimen and counted the Mouse ID's.

2. Bar Plotted Data- `timepoint_df.plot(kind = "bar", xlabel = "Drug Regimen", ylabel = "Number of Time Points")`

To plot Timepoint counts for all mice tested for each regimen using pyplot.

1. Made list of unique drug names.

2. Turned them into a timepoint array and a drug names array and printed them.

3. Bar plotted data for all mice tested for each regimen.

To generate a pie plot showing the distribution of female versus male mice using Pandas.

1. Set up variable for counts for each sex.

2. Generated a pie plot using Pandas.

To generate a pie plot showing the distribution of female versus male mice using pyplot.

1. Set up an array for mice sex counts.

2. Used Pyplot to generate and label the Pie Plot.

### Quartiles, Outliers and Boxplots

To generate a box and whisker plots that shows the distrubution of the tumor volume for each treatment group.

1. Got the last (greatest) timepoint for each mouse, made it into a DataFrame and reset the index.

2. Merged this group df with the original DataFrame to get the tumor volume at the last timepoint.

3. Checked length and dataFrame and printed the number of rows and the df.head.

4. Put treatments into a list for for loop (and later for plot labels).

5. Created an empty list to fill with tumor vol data (for plotting).

6. Located the rows which contain mice on each drug and used a for loop to populate the tumor volume list.

7. Set up subsets for each of the four drug regimens.

8. Set up lower and upper quantiles, calculated upper and lower bounds and printed them for each drug.

9. Set up tumor volume DataFrame for all treatment groups.

10. Box plotted data that shows the distrubution of the tumor volume for each treatment group.

### Line and Scatter Plots 
  To generate a line plot of tumor volume vs. time point for a mouse treated with Capomulin

1. Set up a DataFrame from one mouse who was treated with Capomulin and set the indes to "Timepoint"

2. Merged this group df with the original DataFrame to get the tumor volume at the last timepoint and checked the data.

3. Plotted the Timepoint and Tumor volume as x and y values.

To generate a scatter plot of average tumor volume vs. mouse weight for the Capomulin regimen.

1. Made a dataframe of all mice treated with Capomulin.

2. Made dataFrame Grouped by Mouse ID and Average Tumor Volume, sorted and reset the index.

3. Merged avg tumor volume dataframe with Capomulin Treatment dataFrame and renamed the Average Tumor Volume Column.

4. Plotted Mouse Weight and Average Tumor Volume for mice given Capomulin treatment.

### Correlation and Regression

To calculate the correlation coefficient and linear regression model for mouse weight and average tumor volume for the Capomulin regimen.

1. Set up x and y values as the Weight and Tumor Volume of the mice treated with Capomulin.

2. Set up the linegregress variables, the predicted y values.

3. Got string of line regression line

4. Plotted and showed the data, the regression line, and tried to add the line equation to the plot.

## High Level Analysis Added

Pymaceutials treated 249 mice using ten different drugs to measure their effects on tumor volume. We analyzed the data from 248 mice (51% male, 49% female) measured at five-day intervals. Of the ten drug regimens applied, Capomulin and Ramicaine treatments had the largest reduction of tumor volume. Capomulin had the lowest variability in effect on tumor volume. There was a strong correlation (.84) between tumor volume and mouse weight for mice treated with Capomulin. More study is needed.


