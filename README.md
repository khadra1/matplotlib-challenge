# Matplotlib: The Power of Plots

What good is data without a good plot to tell the story?

In this homework assignment, you’ll apply what you've learned about Matplotlib and to a real-world situation and dataset.
## Background

I've been given access to the complete data from recent animal study from Pymaceuticals Inc., a new pharmaceutical company that specializes in anti-cancer pharmaceuticals. Recently, it began screening for potential treatments for squamous cell carcinoma (SCC), a commonly occurring form of skin cancer.

In this study, 249 mice identified with SCC tumor growth were treated with a variety of drug regimens. Over the course of 45 days, tumor development was observed and measured. The purpose of this study was to compare the performance of Pymaceuticals' drug of interest, Capomulin, versus the other treatment regimens. 

I generagted all of the tables and figures needed for the technical report of the study. Including a top-level summary of the study results.

### Steps taken

* #### Prepare the data.

    * Before data cleaning: 1893 rows and 249 number of unique Mous IDs
 
      * ![Screenshot 2022-08-18 at 19 38 12](https://user-images.githubusercontent.com/67019030/185469534-70ded001-61c3-44b7-974f-e2e58951d7b6.png)
 
     * After data cleaning:  1888 rows and 249 number of unique Mous IDs
     
       * ![Screenshot 2022-08-18 at 19 35 11](https://user-images.githubusercontent.com/67019030/185469046-bf82dfe6-0e73-4f68-9605-9178b2793f22.png)

#### Summary statistics
**Two summary statistics DataFrames:***

First table using the `groupby` method to generate the mean, median, variance, standard deviation, and SEM of the tumor volume for each drug regimen. This resulted in five unique series objects which was combined into a single summary statistics DataFrames:
 
  * ![Screenshot 2022-08-18 at 20 23 16](https://user-images.githubusercontent.com/67019030/185477380-9406cd3c-05e0-47a6-b8c0-ef37437a5bb8.png)
  
Second table using the `agg` method to produce the same summary statistics table by using a single line of code:

  * ![Screenshot 2022-08-18 at 19 58 26](https://user-images.githubusercontent.com/67019030/185473613-522f05a8-5840-49d4-9c9e-69f4331788aa.png)



#### Bar charts showing the total number of timepoints for all mice tested for each drug regimen:

<table>
  <tr>
    <td>Using Pandas`DataFrame.plot()` method</td>
     <td>Using Matplotlib's `pyplot` methods</td>
  </tr>
  <tr>
    <td><img src="Pymaceuticals/Images/pymaceuticals_barplot.png" width=500height=400></td>
    <td><img src="Pymaceuticals/Images/pymaceuticals_plyplot.png" width=500 height=400></td>
  </tr>
 </table>
   

#### Pie charts showing the distribution of female versus male mice:
<table>
  <tr>
    <td>Using Pandas`DataFrame.plot()` method</td>
     <td>Using Matplotlib's `pyplot` methods</td>
  </tr>
  <tr>
    <td><img src="Pymaceuticals/Images/pymaceuticals_pieplot.png" width=500 height=400></td>
    <td><img src="Pymaceuticals/Images/pieplyplot.png" width=500 height=400></td>
  </tr>
 </table>




#### Calculating Quartiles, Finding Outliers, and creatinga Box Plot 
* Quartiles and Outliers, 
* 
* box plot

* Line plot and a scatter plot.

* Calculating correlation and regression. 








1. I calculated the final tumor volume of each mouse across four of the most promising treatment regimens: Capomulin, Ramicane, Infubinol, and Ceftamin. Then, I calculated the quartiles and IQR and determine if there are any potential outliers across all four treatment regimens:

    * A grouped DataFrame that shows the last (greatest) time point for each mouse. 
    * Merged the grouped DataFrame with the original cleaned DataFrame.
    * Determine outliers by using the upper and lower bounds, and then print the results.
    
2. Using Matplotlib, generate a box plot of the final tumor volume for all four treatment regimens. Highlight any potential outliers in the plot by changing their color and style.

  **Hint**: All four box plots should be within the same figure. Use this [Matplotlib documentation page](https://matplotlib.org/gallery/pyplots/boxplot_demo_pyplot.html#sphx-glr-gallery-pyplots-boxplot-demo-pyplot-py) for help with changing the style of the outliers.

### Create a Line Plot and a Scatter Plot

1. Select a mouse that was treated with Capomulin and generate a line plot of tumor volume vs. time point for that mouse.

2. Generate a scatter plot of tumor volume versus mouse weight for the Capomulin treatment regimen.

### Calculate Correlation and Regression

1. Calculate the correlation coefficient and linear regression model between mouse weight and average tumor volume for the Capomulin treatment. 

2. Plot the linear regression model on top of the previous scatter plot.

