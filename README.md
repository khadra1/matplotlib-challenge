# Matplotlib: The Power of Plots

I used the complete data from recent animal study from Pymaceuticals Inc., a new pharmaceutical company that specializes in anti-cancer pharmaceuticals. Recently, it began screening for potential treatments for squamous cell carcinoma (SCC), a commonly occurring form of skin cancer.

In this study, 249 mice identified with SCC tumor growth were treated with a variety of drug regimens. Over the course of 45 days, tumor development was observed and measured. The purpose of this study was to compare the performance of Pymaceuticals' drug of interest, Capomulin, versus the other treatment regimens. 

I generagted all of the tables and figures needed for the technical report of the study. Including a top-level summary of the study results.

### Steps taken

* #### Prepare the data.

    * Before data cleaning: 1893 rows and 249 number of unique Mous IDs
 
      * ![Screenshot 2022-08-18 at 19 38 12](https://user-images.githubusercontent.com/67019030/185469534-70ded001-61c3-44b7-974f-e2e58951d7b6.png)
 
     * After data cleaning:  1888 rows and 249 number of unique Mous IDs
     
       * ![Screenshot 2022-08-18 at 19 35 11](https://user-images.githubusercontent.com/67019030/185469046-bf82dfe6-0e73-4f68-9605-9178b2793f22.png)

## Summary statistics
**Two summary statistics DataFrames:**

First table using the `groupby` method to generate the mean, median, variance, standard deviation, and SEM of the tumor volume for each drug regimen. This resulted in five unique series objects which was combined into a single summary statistics DataFrames:
 
  * ![Screenshot 2022-08-18 at 20 23 16](https://user-images.githubusercontent.com/67019030/185477380-9406cd3c-05e0-47a6-b8c0-ef37437a5bb8.png)
  
Second table using the `agg` method to produce the same summary statistics table by using a single line of code:

  * ![Screenshot 2022-08-18 at 19 58 26](https://user-images.githubusercontent.com/67019030/185473613-522f05a8-5840-49d4-9c9e-69f4331788aa.png)



## Bar charts showing the total number of timepoints for all mice tested for each drug regimen:

<table>
  <tr>
    <td>Using Pandas`DataFrame.plot()` method</td>
     <td>Using Matplotlib's `pyplot` methods</td>
  </tr>
  <tr>
    <td><img src="Pymaceuticals/Images/pymaceuticals_barplot.png" width=500 height=400></td>
    <td><img src="Pymaceuticals/Images/pymaceuticals_plyplot.png" width=500 height=400></td>
  </tr>
 </table>
   

## Pie charts showing the distribution of female versus male mice:
<table>
  <tr>
    <td>Using Pandas`DataFrame.plot()` method</td>
     <td>Using Matplotlib's `pyplot` methods</td>
  </tr>
  <tr>
    <td><img src="Pymaceuticals/Images/pymaceuticals_pieplot.png" width=450 height=400></td>
    <td><img src="Pymaceuticals/Images/pieplyplot.png" width=520 height=400></td>
  </tr>
 </table>




# Statistical Analysis
I calculated the final tumor volume of each mouse across four of the most promising treatment regimens: Capomulin, Ramicane, Infubinol, and Ceftamin. Then, I calculated the quartiles and IQR and determine if there are any potential outliers across all four treatment regimens:

## Calculating Quartiles, Finding Outliers and plotting the results
![Screenshot 2022-08-25 at 16 44 23](https://user-images.githubusercontent.com/67019030/186710609-8fa0d63f-e03c-460b-8a90-b3b966c1e254.png)

* Box plot of the final tumor volume of each mouse across four regimens of interest.

![Screenshot 2022-08-25 at 16 46 48](https://user-images.githubusercontent.com/67019030/186711743-15dcf4c3-a60d-4244-b829-dcdba9df2432.png)


* Line plot

![Screenshot 2022-08-25 at 16 50 17](https://user-images.githubusercontent.com/67019030/186712561-757e5358-4315-40da-b96b-15a35391d611.png)

* Scatter plot

![Screenshot 2022-08-25 at 16 49 45](https://user-images.githubusercontent.com/67019030/186712615-6726f34c-d7b6-4910-b8e2-605bf5b2b00e.png)


* Calculating correlation and regression. 

![Screenshot 2022-08-25 at 17 55 46](https://user-images.githubusercontent.com/67019030/186725463-6439f5f9-989d-4e7f-a38e-f90051c5b74a.png)


![Screenshot 2022-08-25 at 17 57 04](https://user-images.githubusercontent.com/67019030/186725531-58910d6e-6728-4849-9dc7-76921ab537a4.png)





# Analysis 

### Observations and Insights
Using Panda and Matplotlib I investigated the two datasets after merging them into one PandDataframe and then cleaning the data. After plotting and calculating this data I have concluded that:

* There is somewhat of a medium correlation between the Tumor Volume and Weight, further plotting them reveals that there is no clear correlation between them

* Out of the six outliers 5 are female and only 1 is male. Of these 5 females, 4 are considerable younger than the other 2 mice. And these 4 are under the following Drug Regimen
  - Propriva x 2(both are above the upper_bound of tumor volume)
  - Capomulin x 2(both are below lower_bound of tumor volume) 

* There is an even distribution of male vs female mice

* Ramicane and Capomulin have the heighest total number of timpoints
Capomulin may have the best result but that would need investigating further.
