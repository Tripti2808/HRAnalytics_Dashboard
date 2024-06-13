# HRAnalytics_Dashboard

## Problem Statement

This dashboard helps the company to understand the attrition rate and reason of attrition. It helps the Company/Manager to know that their employees are satisfied with their job. Through different ratings, they get to know their improvement area, & thus they can improve their services by identifying these area. It also lets them know the departments where attrition is high, their salary, the ratings they gave before leaving thus since by using this dashboard they have identified this problem, they can further work on factors responsible for these attritions.

### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : It was observed that in yearwithcurrmanager empty values were found 
that column was not useful so we removed the column.
- Step 4 : Then we looked for duplicate values which were removed by selecting all the column with shift and then removed the duplicates. 
- Step 5 : Then we looked whether the data is in proper type or format.
- Step 6 : Then we calculated the arritationcount and attritionrate.
- Step 7 : Visual filters (Slicers) were added for field named "Department"
- Step 8 : Card visuals were added like Attrition, Attritionrate, Avg Age, Avg Salary, Year at company.
           Using visual level filter from the filters pane, basic filtering was done.
- Step 10 : Calculated column was created in which, customers were grouped into various age groups.

for creating new column following DAX expression was written;
       
        Age Group = 
        
        if(HR_Analytics[Age]>=18, "18-25",
        
        if(HR_Analytics[Age]>=26, "26-35",
        
        if(HR_Analytics[Age]>=36, "36-45",
        
        if(HR_Analytics[Age]>=46, "46-55",

        if(HR_Analytics[Age]>=55, "55+")

        
- Step 11 : New measure was created to find Attrition rate.

Following DAX expression was written for the same,
        
        Attritionrate = sum(HR_Analytics[Attritioncount])/sum(HR_Analytics[Employeecount])
 
# Insights

A single page report was created on Power BI Desktop & it was then published to Power BI Service.

Following inferences can be drawn from the dashboard;

### [1] Total Number of Employees = 1470

   Number of Employees (Male) = 140

   Number of Employees Customers (Female) = 79
           
  ### [2] Average Monthly Income 
  
      a) Average monthly income of males - 6380.51
      b) Average monthly income of females - 6686.57

###  [3]  Salary hike

      a) Average of salary hike of males- 15.22
      b) Average of salary hike of females- 15.20
 ### [3] Some other insights
 
 ### salary slab
 
 1.1) 50.95 % employees belong to 'upto 5k.
 
 1.2) 29.93 % employees belong to '5k-10k'.

 1.3) 10.07 % employees belong to '10k-15k'.

 1.4) 9.05 % employees belong to '15k+'.
 
         thus, maximum employees have salary 'upto 5k'.
 
 ### Age Group
 
 2.1)  8.37 % employees belong to '18-25' age group.
 
 2.2)  41.22 % employees belong to '26-35' age group.
 
 2.3)  31.84 % employees belong to '36-45' age group.
 
 2.4)  15.37 % employees belong to '45-55' age group.

 2.5)    3.2 % employees belong to '55+' age group.
 
         thus, maximum employees belong to '26-35' age group.
         
