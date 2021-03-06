# kickstarter-data-analysis
projects and files related to kickstarter
# Kickstarting – A Challenge focusing on Excel skills and data analysis

## Overview of Project: 
* Our project focuses on Kickstarter campaign performance – success/fail/cancelled/live and performance versus goal for a series of fundraiser categories encompassing film, food, video, games, theater, television, publishing, music, and others.

### Purpose:
*Louise, a client, has requested assistance. Her Theater project “Fever- A workshop Project” had an average donation of $248.50 and $2485 pledged versus a goal of $2885. Louise has hired our team to dig deeper into the data to assist in understanding Fever’s Performance versus others in category and to aid in selecting her next venture.

## Analysis and Challenges:
* Initial analysis focused on understanding the Kickstarter dataset with 4115 Rows of Data and twenty-two columns in the final state. Critical path activities included:
o Reviewed data formats and changed columns B, C, F, G, H, M, N to Text formats.
o Froze panes at B2 as target to Freeze columns A,B and Row 1
o Left D & E as accounting formats using $ symbol
o Color Coded Column F using conditional formatting.


o Recognized that Deadline and Launch Date (columns I & J are Unix date formats starting from an EPOCH date and would need converted. Columns S & T added. Formula used to convert dates: =(((J2/60)/60)/24)+DATE(1970,1,1). Format- Date with Category  Month DD, YYYY selected. 
o Added a bonus column “Campaign Length in Months” calculated using the DATEDIF function:  =DATEDIF(S2,T2,"M")
o Launch Date – Year generated in Column V using the Year() function.  =YEAR(S2)
o Sorted Data Set based on Pledge $ from Highest to Lowest 
o Used conditional Formatting in the % Funded column with two color gradient with red as minimum and Blue as Maximum.  ***Due to outliers in the data set the column stays red for most values.
o The Parent Category/Subcategory column divided into separate columns - Q & R using the Text to Columns Feature under the Data tab. Delimiter selected as other with 
“/” and text. 
*Data Analysis - Initial
o Completed Pivot table analyzing Outcomes by Category
* In support of this effort – filtered data set in Kickstarter tab to validate Pivot output.
* Pivot outputs included Filtering by Country and evaluating Successful campaign outputs by parent category. 


o Completed Pivot on Outcomes by subcategory.  Created Stacked bar and side by side Bar charts for Subcategories in the Great Britain and Theater category. Changed colors and types of pivot bar charts – stacked, side by side. Also created Pivot of all US subcategories versus outcome.
 




o Inserted new pivot into Outcomes by Launch tab – Investigated Launch Month versus outcomes for all years and countries, theater only outcomes, limited pivot chart to only look at successful, failed, and canceled projects. Adjusted line column colors and compared US to Great Britain.



* Completed Edinburg tab with VLOOKUP features to investigate five specific plays and performance data. =VLOOKUP(A2,Kickstarter!B:E,3,FALSE)


o All 5 plays were successful with Pledged dollars exceeding goal. The Average Donation across all campaigns is $40.48 and average number of backers per play was fifty-two. Donors range was 26-113.

* Completed analysis of successful and failed US Kickstarter campaigns for the subcategories plays, animation, and Nonfiction. 
o Data is filtered on subcategory and outcome status to create the data tables. With separate sheets created for success and fail per subcategory.


o Note for the Animation tab, all countries included to expand the dataset.
o Finally, a Descriptive Statistics tab created comparing Successful versus Failed data collected utilizing VLOOKUPs to compare mean, median, standard deviations, quartiles, and IQR information.


o Working with the data on Nonfiction and Animation subcategories provided a challenge as each subcategory was either all successful or all failing. To deal with the uniqueness of this data set, the IFERROR feature was incorporated into the calculations to deal with the lack of data in selected Outcomes and deliver a numerical result. =IFERROR(AVERAGE('Successful Animation'!$D:$D),0) 

*Box and Whisker Chart – Sheet Box&Whisker GB Musical  
o Filtered Data on Kickstarter sheet to GB and Musical. Selected Pledged and Goal columns then selected histogram then selected Box & Whisker chart then moved to own sheet. 


##Challenge 1 Deliverable Theater Outcomes Based on Launch
o Added new column to Kickstarter tab in Column V called Launch Date – Years.  Utilized the YEARS calculation using the following formula: =YEAR(S2) to obtain year of campaign.
o Created new Pivot table in Tab – Theater Outcomes by Launch Date. In working with this Pivot, adding Launch Date Conversion to the Rows resulted in Years, Quarters, and months automatically add for adding Launch Date. Years and Quarters removed from the row categories. Filters were added for Parent Category, Country, and Years.  Columns were set to the outcomes with a count of outcomes reported as values. Under the Column labels – live projects filtered out using the drop down. Row labels were filtered A to Z to put months into correct order for ease of viewing.  Pivot line charts added to view all countries, GB only, US only, and all countries except US & GB. 






## Challenge 1 Deliverable Outcomes Based on Goals
o Created new sheet Outcomes Based on Goals  
o Added 8 New columns Goal, # Successful, # Failed, # Cancelled, Total Projects, % successful, % Failed, % Cancelled. Added a ninth column to validate % calculations - Validating total % which would be 100% if correct.
o 
o For the Goal column created a set of ranges to categorize project goals into ranges of $ targets. These were set to a general format.
o To calculate the number of successful, failed, or canceled projects the COUNTIF function was utilized. By searching the Kickstarter data Tab on the associated row for the desired outcome. #Successful: =COUNTIFS(Kickstarter!$F:$F,"Successful",Kickstarter!$D:$D,"<1000"). # Failed: =COUNTIFS(Kickstarter!$F:$F,"Failed",Kickstarter!$D:$D,"<1000). # Canceled: =COUNTIFS(Kickstarter!$F:$F,"Canceled",Kickstarter!$D:$D,"<1000") 
o Total number of projects calculated by completing Sum() of # successful, # Failed, and # canceled.
o % Successful was calculated by Dividing the number successful by total projects by each Goal Category and repeated for % failed and % canceled. All percentage columns were formatted as % in the format columns menu. An alternative is to calculate the percentage by taking the #successful/Total projects and multiplying by one hundred then formatting the column as general or a number.
o A line chart created and saved as a .png file for reference. The line chart analyzes the campaign outcomes over increasing value goal setpoints and aggregates multiple campaigns for each Goal range to assess for trends/correlations.



##Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?
1. The best time of year for Theater project campaigns is May, followed by June. December is the worst.
2. The US & Great Britain represent 92.2% of all Theater Kickstarter campaigns overall. The US has the lead with a total of nine hundred campaigns in the dataset while has Great Britain has 363.  1369 is the total of theater campaigns with the database. Based on this information, the US and GB drive the overall data trends and analysis.
3. When comparing the US to GB with this data set the trends are similar for the two countries as to the months with the most successful campaigns with the caveat that GB experiences a sharp drop off in total campaigns after August, while US projects see a gradual drop in total month to month downturn in campaign successes while failures are consistent throughout the year.
 
- What can you conclude about the Outcomes based on Goals?
1. Performance/Success at meeting a campaign goal is most successful in smaller/lower $ campaigns versus large/high $ campaigns.  We see 71% success at Less than $1000 and the success rate has a linear decline.  
2. Once the goal reaches $20k we see success versus failure shifts to failures out pace successes.
3. For Projects above $40K we see a steep increase in the percentage of failures which, when combined with cancellations pushes the failure/cancelation rate above 60%.   
- What are some limitations of this dataset?
1. Data is anywhere from 5-9 years old.
2. The dataset is heavily biased as 65% of the data is coming from the US. Great Britain is a secondary influencer as they provide an additional 26.5% of the data. This impact compounds as the US and GB show similar trends with key measures and trends.
3. Several subcategory data sets are extremely limited with only success or failure data which skews the analysis and influences are minimal in the larger aggregated dataset.

- What are other tables and/or graphs that we could create?
1. Outcomes by Year to see if specific years have more significant impact/influence on the data.
2. A breakout of the data by parent category – count of items and a distribution by subcategory within each parent to understand if a particular subcategory is driving the parent category.

### Final Thoughts for Louise:
* As we look at your future endeavors, although the data is from more than 5 years old there are key points to keep in mind while planning your next play:
o May/June/July is the best time of year for a campaign based on this dataset.
o Setting Reasonable and attainable goals is critical to success. A modest campaign of up to $30,000 has the highest chances of success and reaches more donors.
o When in doubt – plays and theater Kickstarter data for the US appears to correspond well with Great Britain trends and performance measures.
o If still unsure, we can always look for more recent data as Covid has had a significant impact on these social activities and may present a different landscape for fundraising.
