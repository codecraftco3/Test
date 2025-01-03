
# Twitter Analytics-Dashboard

### Dashboard Link : https://app.powerbi.com/links/Koi8KvzLrg?ctid=68038a1c-5cea-46d0-942e-08bef26d424f&pbi_source=linkShare

## Problem Statement

This dashboard helps to Track and visualize Twitter metrics such as followers, tweets, retweets, likes, and replies over time. It helps to Analyze sentiment analysis and emotion detection to understand public opinions and emotions towards our brand. It identify top influencers, hashtag and keywords related to our brand and industry. By creating this dashboard, we aim to improve our social media strategy, engage with our audience more effectively, and make data driven decision to enhance our brand reputation and online presence. 

### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : It was observed that in none of the columns errors & empty values were present in following all columns.
- Step 5 : For calculating time, null values were not taken into account as only less than 1% values are null in this column,seperate date and time was extracted from the time column.
- Step 6 : In the report view, under the view tab, theme was selected.
- Step 7 : Since the data contains Engagement Rate ,only Total Engagement Rate value is derived from DAX Function-(Sum Function) and dragged into Card Visual. 
- Step 8 : Visual filters (Slicers) were added for Three fields named "Month", "Weekdays", "Given Time Range".
- Step 9 : Card visuals were added to the canvas, representing Impression,Engagement Rate, Tweet Count.
           Using visual level filter from the filters pane, basic filtering was used & null values were unselected for consideration into Total calculation.
           
           Although, by default, while calculating Total, blank values are ignored.
- Step 10 : A Line chart was also added to the report design area representing the Trend over particular period of time .Other Line chart for impression over week ,Cluster Bar chart to show Tweet with sum of URL Clicks and other visuals.
- Step 11 : Pie Chart Visual was used to represent Sections mentioned below,

  (a) Hashtag Clicks
  (b) URL Clicks
  (c) User Profile Click
In our dataset, Some parameters were assigned value 0, representing those parameters are not applicable for some Data.

All these values have been ignored while calculating Totals for each of the parameters mentioned above.

- Step 12 : In the report view, under the insert tab, three text boxes were added to the canvas, Task mentioned were written for each page. 
- Step 13 : In the report view, under the insert tab, using shapes option from elements group a rectangle was inserted for App-Open and App-not-Open was added to the report design area. 
- Step 14 : Calculated column was created in which,

for creating new column following DAX expression was written;
       
       Calender1 = CALENDARAUTO()        

        
- Step 15 : New measure was created to find total engagement rate.

Following DAX expression was written for the same,
        
        Total Engagement Rate = sum('SocialMedia (1)'[engagement rate])

A card visual was used to represent Total Engagement Rate.



![2](https://github.com/user-attachments/assets/90fa855f-fa84-4326-ba57-755504db068c)


        
 - Step 16 : New measure was created to find  Odd Date posted Tweet ,
 
 Following DAX expression was written to find Odd Date posted Tweet ,
 
        odd date = if(mod(day(Calender1[Date]),2)=1,Calender1[Date])
 
 
 
 - Step 17 : New measure was created to calculate Tweet character count with below 30 .
 
 Following DAX expression was written ,
 
         Tweet char 30 below = 
VAR MaxLength = 29
VAR SubText = LEFT([Tweet], MaxLength)
VAR LastSpace = FIND(" ", SubText, LEN(SubText), -1)
RETURN IF(LastSpace > 0, LEFT([Tweet], LastSpace - 1), SubText)
    
 
 
 
 ![10](https://github.com/user-attachments/assets/2bf50ce4-2f36-4e4f-b95a-9351347bf164)
 
 - Step 18 : The report was then published to Power BI Service.
 
 
![7](https://github.com/user-attachments/assets/395898b9-7161-4c7f-9ee9-ac67507375a0)


# Snapshot of Dashboard (Power BI Service)

![11](https://github.com/user-attachments/assets/f9d66b42-de37-4f79-9e2e-e00c6f3ad78d)

 
 # Report Snapshot (Power BI DESKTOP)

 
![12](https://github.com/user-attachments/assets/7f0d9f84-df6d-4b8c-aab0-a355cfc145f7)

# Insights

A single page report was created on Power BI Desktop & it was then published to Power BI Service.

Following Task were worked out ,

1. Develop a chart that displays tweets with the highest engagement rates (top 10%). Include only those tweets that have received more than 50 likes and were posted on weekdays and this graph should work only between 3PM IST to 5 PM IST apart from that time we should not show this graph in dashboard itself as well as tweet character count should be below 30.

SnapShot of Task 1

![4](https://github.com/user-attachments/assets/1a1f0943-7b57-4ecd-a9ca-3438114b0da8)

2. Plot a scatter chart to analyse the relationship between media engagements and media views for tweets that received more than 10 replies. Highlight tweets with an engagement rate above 5% and this graph should work only between 6PM IST to 11 PM IST apart from that time we should not show this graph in dashboard itself and the tweet date should be odd number as well as tweet word count be above 50.

Snapshot of Task 2

![5 1](https://github.com/user-attachments/assets/5fc71164-b4df-4904-8ab7-3d80163637c7)

3. Analyse tweets to show a comparison of the engagement rate for tweets with app opens versus tweets without app opens. Include only tweets posted between 9 AM and 5 PM on weekdays and this graph should work only between 12PM IST to 6PM IST and 7 AM to 11AM apart from that time we should not show this graph in dashboard itself and the tweet impression should be even number and tweet date should be odd number as well as tweet character count should be below 30 and need to remove tweet word which has letter 'D'.

Snapshot of Task 3

![6](https://github.com/user-attachments/assets/34292ce5-f3cf-410c-9bc3-34533203852f)
