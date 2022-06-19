# Kickstarter-analysis
Performing Analysis on Kickstarter Data to uncover trends
## Overview of the Project:
The purpose of this analysis is to help an upcoming playwright Louise who wants to start a crowdfunding campaingn to underplay fever. she is estimating a budget of $10,000.
## Analysis and Challenges
### The first step of the analysis is to take an initial look at the data.
By looking at the data provided we can understand the following:
1. How large is the data we are working with like number of rows and columns. 
2. Familiarizing with the type of data present and Checking whether all the data type is classified correctly. 
3. Is the Data readable or does it need to convert.

**Observations**
* The type of Data present in the sheet are General, Accounting, etc.,
<img width="1440" alt="Type of Data" src="https://user-images.githubusercontent.com/107584361/174467671-75026183-a46a-4f89-88ce-0c76b76aaa5c.png">
* Column I & J look like date but are not readable they contain unix timestamps rather than standard format.
But to be sure that the data are timestamps, we can use a timestamp converter [Timestamp converter](https://www.epochconverter.com/).

### The next step in the analysis is to Organize the data.
Before organizing the data,let us understand the data in each column that we are working with:
1. Goal Column tells how much money each campaign will need to succeed.
2. Pledge Column tells how much money each campaign actually made.
3. Outcome column tells whether campaign was successful or not.
4. Country column tells us which country campaign was started.

To Organizing the data, we can use filters and formatting, and by freezing specific columns and rows. 
Here are the further analysis steps to organize the Kickstarter data.
Adding the columns to interpret the data more easily.
#### Adding Percentage funding Column
- Many of the campaigns missed their goal amount by a small margin. So to determine how much of the campaign goal was met,lets add a column "Percentage funded". Data from the Pledged and Goal columns will be used to find the percentage funded. 
#### Adding Average Donations Column
- Crowdfunding platforms, allows project creators to add incentives for different pledge amounts. We can determine how much money people have pledged to campaigns by add another column "Average Donations". Data from the Pledged column divide by the backers gives the Average Donations.

**Observations**
"Average Donations" column has an error *`#DIV/0!`*. Even though the formula is valid, Excel doesn't recognize a formula's output format. Kickstarter requires every campaign to have a fundraising goal. However, not every campaign has backers, which means, in some cases, there is no number to divide by in the formula. To address this error we will use *`iferror(value,value if error)`* formula . 
#### Spliting Category/Subcategory column to two distinct columns
- To view our data in more detail, lets split our category and sub-category column into two distinct columns: "parent category" and "subcategory".

**To create a new Subcategory column:**
1. select category and subcategory column.
2. Copy the column
3. paste the data into a new column 
4. click Data tab
5. click "Text to Column" button.
6. The "Convert Text to Columns Wizard" appears. 
7. Inside the "Convert Text to Columns Wizard:"
   - Select "Delimited" and click "Next."
   - Uncheck the "Tab" box and check "Other."
   - Place a backslash ( / ) in the box, then click "Next."
   - Select "Text" from the "Column data format."
   - Click "Finish."
Now we have a new column name subcategory.
- Another data to be consider is the length of the fundraising campaign. lets determine will the length of a campaign makes a difference in determining its success.
The data in the launched_at and deadline columns are not readable. They contain Unix timestamps. To convert this we need to use a formula: 
*`=(((J2/60)/60)/24)+DATE(1970,1,1)`*
After applying the formula to the column, change the format of the column from General to Date.
### The next analysis is to create Summary tables, charts and graphs.
**Pivot Tables** helps us to condense the data into summary to deliver information.
**Pivot charts** complement pivot tables by using table data to create visualizations such as bar charts and line graphs. Visualizations aid in uncovering a link or trend, especially when a table isn't able.
#### Create Pivot table
- click on the insert 
- select pivot table
- select table and new sheet in the wizard
- In the pivot table field select:
- date created convertion on row and outcomes on columns, 
- category and years in filters.   
#### Creating a Pivot chart
1. Click anywhere on the pivot table to bring up the PivotTable Analyze tab, and then click it.
2. Click the PivotChart button, located in the Tools group on the ribbon. When this button is clicked, Excel will automatically choose a chart based on the table data, which in our case is a clustered column.
3. Click on the chart, and then click the Design tab on the toolbar.
4. Click the Change Chart Type button, and then select Line Chart from the pop-up menu.
Add a title to your bar chart by completing the following steps:
1. Return to the Design tab and click Add Chart Element on the left side of the toolbar.
2. From the pop-up menu, select Chart Title **"Theater outcomes by Launch date"** followed by Centered Overlay.
## Results
### Theater Outcomes based on launch Date:
1. The month that launched the most successful Kickstarter campaigns was May, but diminish by the end of the year.
2. January, June, July and October all had roughly the same number of failed campaigns launched.
### Outcomes based on Goals:
oucomes based on goals chart shows that instead of one large spike, the lines trend all over and less predictable. 
Louise estimates her play costs arount $10,000. Lets look at the percentage success for a goal amount ranging from $10,000 to $15,000. The percentage successful was 54.17% anf percentage failure is around 45.83%. This means the chances of success and failure are almost same.
### Other Possible Analysis:
By Using the statistical Analysis we can understand how the data is distributed and the central tendency, variance and outlier. 
