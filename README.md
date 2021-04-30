# Kickstarter Project Success Analysis

## Background Information

Over $2 billion has been raised using the massively successful crowdfunding service, Kickstarter, but not every project has found success. Of the more than 300,000 projects launched on Kickstarter, only a third have made it through the funding process with a positive outcome.

Getting funded on Kickstarter requires meeting or exceeding the project's initial goal, so many organizations spend months looking through past projects in an attempt to discover some trick for finding success. For this project, I effectively organized and analyzed a database of 4,000 past projects in Microsoft Excel in order to uncover any hidden trends.

## Initial Analysis Setup

Using the Excel table provided (https://umn.bootcampcontent.com/University-of-Minnesota-Boot-Camp/uofm-stp-data-pt-12-2020-u-c/blob/master/02-Homework/01-Excel/Instructions/StarterBook.xlsx), I modified and analyzed the data of 4,000 past Kickstarter projects in an attempt to uncover some market trends.

* I utilized conditional formatting to fill each cell in the `state` column with a different color, depending on whether the associated campaign was successful, failed, or canceled, or is currently live.

* I created a new column O called `Percent Funded` that uses a formula to uncover how much money a campaign made to reach its initial goal.

* Within the new `Percent Funded` column, I used conditional formatting to fill each cell based on a three-color scale. The scale begins at 0 with a dark shade of red, which transitions to green at 100, and blue at 200.

  * Further, I added in a new column P called `Average Donation` that uses a formula to uncover how much each backer for the project paid on average.

  * I generated two new columns, one called `Category` at Q and another called `Sub-Category` at R, which use formulas to split the `Category and Sub-Category` column into two parts.

![landing](Images/landing_layout.png)


## Category and Sub-Category Pivot Tables

* I generated a new worksheet with a pivot table that analyzed my initial worksheet to count how many campaigns were successful, failed, canceled, or are currently live per **Category**.

  * Utilizing this pivot table, I was able to create a stacked column pivot chart that can be filtered by country.

  ![Category Stats](Images/success_by_category.png)

  * To provide a deeper analysis of campaign succses, I created a new worksheet with a pivot table that analyzed my initial dataset to count how many campaigns were successful, failed, or canceled, or are currently live per **Sub-Category**.

  ![Subcategory](Images/succes_by_subcategory.png)

  * Create a stacked column pivot chart that can be filtered by country and parent-category based on the table you have created.

* The dates stored within the `deadline` and `launched_at` columns use Unix timestamps. Fortunately for us, [there is a formula](https://www.extendoffice.com/documents/excel/2473-excel-timestamp-to-date.html) that can be used to convert these timestamps to a normal date.

  * Create a new column named `Date Created Conversion` that will use [this formula](https://www.extendoffice.com/documents/excel/2473-excel-timestamp-to-date.html) to convert the data contained within `launched_at` into Excel's date format.

  * Create a new column named `Date Ended Conversion` that will use [this formula](https://www.extendoffice.com/documents/excel/2473-excel-timestamp-to-date.html) to convert the data contained within `deadline` into Excel's date format.


## Campaign Outcomes Based on Launch Date

  * Within my Excel workbook, I created a new sheet with a pivot table with a column of `state`, rows of `Date Created Conversion`, values based on the count of `state`, and filters based on `parent category` and `Years`.

  * Now create a pivot chart line graph that visualizes this new table.

* Create a report in Microsoft Word and answer the following questions.

1. Given the provided data, what are three conclusions we can draw about Kickstarter campaigns?
2. What are some limitations of this dataset?
3. What are some other possible tables and/or graphs that we could create?

## Campaign Outcomes Based on Target Goal

* Create a new sheet with 8 columns:

  * `Goal`
  * `Number Successful`
  * `Number Failed`
  * `Number Canceled`
  * `Total Projects`
  * `Percentage Successful`
  * `Percentage Failed`
  * `Percentage Canceled`

* In the `Goal` column, create 12 rows with the following headers:

  * Less than 1000
  * 1000 to 4999
  * 5000 to 9999
  * 10000 to 14999
  * 15000 to 19999
  * 20000 to 24999
  * 25000 to 29999
  * 30000 to 34999
  * 35000 to 39999
  * 40000 to 44999
  * 45000 to 49999
  * Greater than or equal to 50000

  ![Goal Outcomes](Images/GoalOutcomes.png)

* Using the `COUNTIFS()` formula, count how many successful, failed, and canceled projects were created with goals within the ranges listed above. Populate the `Number Successful`, `Number Failed`, and `Number Canceled` columns with this data.

* Add up each of the values in the `Number Successful`, `Number Failed`, and `Number Canceled` columns to populate the `Total Projects` column. Then, using a mathematical formula, find the percentage of projects that were successful, failed, or canceled per goal range.

* Create a line chart that graphs the relationship between a goal's amount and its chances at success, failure, or cancellation.

## Campaign Backer Statistical Analysis

If one were to describe a successful crowdfunding campaign, most people would use the number of campaign backers as a metric of success. One of the most efficient ways that data scientists characterize a quantitative metric, such as the number of campaign backers, is by creating a summary statistics table.

To provide a more concrete financial analysis of these Kickstarter campaigns, I created my own summary statistics table to evaluate the number of backers of successful and unsuccessful campaigns.

* I generated a new worksheet in my Excel workbook and created a column each for the number of backers of successful campaigns and unsuccessful campaigns.

* For both successful and unsucessful campaigns, I used Excel filtering functions and statistical analysis formulas to perform the following:

  * The mean number of backers

  * The median number of backers

  * The minimum number of backers

  * The maximum number of backers

  * The variance of the number of backers

  * The standard deviation of the number of backers

  ![backers](Images/backers_stat_analysis.png)

* Within my Excel worksheet, I described why the mean summarizes the data more effectively than the median. This is due to ...

* Use your data to determine if there is more variability with successful or unsuccessful campaigns. Does this make sense? Why or why not?

- - -

© 2019 Trilogy Education Services
