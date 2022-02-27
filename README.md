# The Power of Plots

## Background

You've joined Pymaceuticals Inc., a burgeoning pharmaceutical company based out of San Diego. Pymaceuticals specializes in anti-cancer pharmaceuticals. In its most recent efforts, it began screening for potential treatments for squamous cell carcinoma (SCC), a commonly occurring form of skin cancer.

As a senior data analyst at the company, you've been given access to the complete data from their most recent animal study. In this study, 249 mice identified with SCC tumor growth were treated through a variety of drug regimens. Over the course of 45 days, tumor development was observed and measured. The purpose of this study was to compare the performance of Pymaceuticals' drug of interest, Capomulin, versus the other treatment regimens. You have been tasked by the executive team to generate all of the tables and figures needed for the technical report of the study. The executive team also has asked for a top-level summary of the study results.

## Requirements

Your tasks are to do the following:

- Generate a summary statistics table consisting of the mean, median, variance, standard deviation, and SEM of the tumor volume for each drug regimen.

- Generate a bar plot that shows  the number of total mice for each treatment regimen throughout the course of the study.

- Generate a pie plot that shows the distribution of female and male mice in the study.

- Calculate the final tumor volume of each mouse across four of the most promising treatment regimens: Capomulin, Ramicane, Infubinol, and Ceftamin. Calculate the quartiles and IQR and quantitatively determine if there are any potential outliers across all four treatment regimens.

- Using Matplotlib, generate a box and whisker plot of the final tumor volume for all four treatment regimens and highlight any potential outliers in the plot by changing their color and style.

- Select a mouse that was treated with Capomulin and generate a line plot of tumor volume vs. time point for that mouse.

- Generate a scatter plot of mouse weight versus average tumor volume for the Capomulin treatment regimen.

- Calculate the correlation coefficient and linear regression model between mouse weight and average tumor volume for the Capomulin treatment. Plot the linear regression model on top of the previous scatter plot.

## Summary

This simulation of a medical drug study requires extensive use of matplotlib and/or pyplot to generate all of the visuals required. I started by doing some data cleanup, removing any rows that contained duplicate timepoints for a given mouse ID number. With this clean data set, I was able to start my analysis.

The first step was grouping the data by drug regimen, then calculating the mean, median, variance, standard deviation, and standard error per drug.


I then created a bar chart showing the total count of mice being treated with each drug using both matplotlib and pyplot. This showed an even distribution of mice across all drugs tested, with the exception of Stelaysn which had one fewer mice.


It was also requested that a pie chart be created showing the breakdown between male and female mice. As with the bar chart, I used both matplotlib and pyplot. There was a near perfect split between the sexes, making this a very balanced study.


To calculate the quartiles and find outliers, I had to extract the final tumor size of each mouse. It was requested that this only be done for four of the drugs: Capomulin, Ramicane, Infubinol, and Ceftamin. I combined these results into one data frame.


The quartiles and IQR were determined by setting up a for loop to go through the test subjects of the four drugs and calculating the lower quartile, upper quartile, interquartile range, and upper/lower bounds, while also appending the final tumor volume to a list.


Using the merged drug data frame, I charted box plots to visualize these quartiles and upper/lower bounds, as well as any outliers. It was clear from this chart that there two of the drugs were much more successful at reducing tumor volume than the others - Capomulin and Ramicane.


The next task was to create a line chart showing the tumor volume for a given mouse over time. I selected a mouse ID at random and plotted the tumor volume vs timepoint. 


An interesting note for this chart is that I tested it with multiple mouse IDs and they all showed a slight uptick in tumor volume at the end of the study. I would be interested to see a longer-term study to see how well the drug continues to work.

I also created a scatter plot to show the average tumor volume by mouse weight. I then applied a linear regression model to it, showing there was a positive correlation between the weight of the mouse and the size of the tumor. This would suggest either that the tumors are proportional to the size of the mouse or that the larger the tumor, the heavier the mouse becomes. 




