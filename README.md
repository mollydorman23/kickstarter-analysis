# Kickstarting with Excel

## Overview of Project

My analysis of the data available for Kickstarter fundraising campaigns focused on filtering for the types of campaigns that were most relevant to Louise’s projects (ie: plays in the US). From there, I sorted the data based on if the campaign was successful or not, when it launched and what the goals were for the campaigns. 

### Purpose

The purpose of this specific analysis is to determine what type of impact, if any, the launch date and goal amount had on Kickstarter fundraising campaigns for plays. This analysis is intended to help guide Louise’s strategic planning for future fundraising campaigns, in order to ensure a successful outcome. In this case, success is defined as raising enough money to fund the production of a play. 

- - - -

## Analysis and Challenges

The two main analyses I performed visualized theater outcomes based on launch date and on fundraising goals. 

### Analysis of Outcomes Based on Launch Date

In order to determine outcomes based on launch date, I completed the following steps:
1.	I created a new column in my Kickstarter worksheet tab and used the years() formula to extract the year each fundraising campaign took place.
2.	Then, I created a new pivot table using “years” and “parent category” as the filters, “outcomes” as the columns and values and the date created conversion data as the rows. 
3.	I then made sure to filter the "outcomes" data to only show “successful,” “failed,” and “canceled” campaigns. Initially, I wasn’t sure why my table had different data than the instructions, but quickly realized it was because I still was pulling “live” campaigns into my table. 
4.	Next, I used the “ungroup” and “group” actions to have the rows listed as months instead of years. This was a little more challenging to figure out but I did so with some trial and error. 
5.	Next, I filtered for Theater campaigns only and sorted the outcome data in descending order, so that successful outcomes showed in the first column. 
<img width="329" alt="Outcome vs launch pivot" src="https://user-images.githubusercontent.com/103781847/164944170-bca5f097-39c6-4bee-831f-76a9cb9cf02f.png">
7.	Lastly, I created a line chart from the pivot table to show the relationship between outcomes and launch month.

![Theater_Outcomes_vs_Launch](https://user-images.githubusercontent.com/103781847/164944255-df706199-51b5-41c3-99c3-77c745bffb27.png)


### Analysis of Outcomes Based on Goals

In order to determine outcomes based on (fundraising) goals, I completed the following steps:
1.	I created a new data sheet and calculated the number of successful, failed and canceled campaigns based on each goal range of ~$5000, starting with campaigns of $1000 or less and ending with any above $50,000. 
* Using the COUNTIFS formula was the most challenging part of the assignment for me. It took a fair amount of trial and error, reviewing the videos and other resources provided. I finally figured out that in order to show a conditional statement that is a range (ie: >=$5000 but <$9999) you have to first code the selected data range and the criteria of being greater than or equal to XX number and then code the same data range and the criteria of being less than or equal to XX number. 
* Once I got the main formula down, I was able to edit it with the different goal parameters and the different outcomes to fill out all of my columns.
Code: =COUNTIFS(Kickstarter!$D2:$D4115,">=1000",Kickstarter!$D2:$D4115,"<=4999",Kickstarter!$F2:$F4115,"successful",Kickstarter!$R$2:$R$4115,"plays")
2.	Using the SUM function was much easier since I’m more familiar with it. I was quickly able to sum the total amount of projects within each goal range (SUM(# of successful, failed, canceled))
3.	From there, I calculated the % of successful, failed and canceled campaigns by dividing the number of successful or failed or canceled campaigns over the total number of campaigns.
4.	Lastly I created a line chart to show the relationship between campaign goals and their outcomes (% successful, failed and canceled). 
*	This chart was a little more challenging but I figured out how to right click on the chart and select “select data” from the menu in order to remove the unnecessary data and only use the % successful, failed and canceled on the Y-axis and goals along the X-axis.
*	I also changed the colors of the lines in order to match the instructions and gave the chart the title “Outcomes vs Goals.”
 ![Outcomes_vs_Goals](https://user-images.githubusercontent.com/103781847/164944330-e82c26ac-02b0-47a6-97d1-69b10a2b85f7.png)

### Challenges and Difficulties Encountered
1. As shared above, in the first part of the assignment it was challenging to figure out how to show months in the rows of my pivot table, instead of years. With some trial and error and using the “group” and “ungroup” tools, I was able to change the rows to months.
2. As shared above, using the COUNTIFS formula was the most challenging part of the assignment for me. I had to review several of the videos and resources multiple times and do some trial and error before I determined how the code should look to show a range for the goal amount. 

- - - -

## Results

### What are two conclusions you can draw about the Outcomes based on Launch Date?
1.	May had the highest number of successful Theater Kickstarter campaigns with 111 and June was a fast follow with 100. May also had the highest number of failed campaigns with 52, so it’s possible that it is simply a busy month to launch a campaign in general. 
2.	December was the worst month in terms of successful campaigns. There were only 37 successful campaigns and 35 failed. December is the only month where there are almost as many failed campaigns as successful ones. 

### What can you conclude about the Outcomes based on Goals?
There is an inverse relationship between the % of successful and failed campaigns. This makes sense, especially because there were no canceled Kickstarter campaigns for plays. The percentage of successful play campaigns was higher in the under $5000 goal range, as well as in the $35,000-$45,000 range. Plays with a goal over $45,000 had the highest percentage of failed campaigns and the lowest percentage of successful ones. 

### What are some limitations of this dataset?
1.	While we have more understanding of when to launch a Kickstarter campaign to raise money to produce a play, and what goal amounts are most likely to be achieved/successful, we don’t have as much qualitative information about the plays or the campaigns themselves. For example, it might be helpful to know about the design of successful campaigns - did they include photos, how did they catch people’s attention and “sell” the benefit of donating to the campaign? 
2.	We also don’t have information around specific regions, which I think would be especially helpful for the US campaigns. Are there certain states or regions of the US where Kickstarters for plays are more likely to get funded? 

### What are some other possible tables and/or graphs that we could create?
1.	If we could drill down to the state the campaign was launched in, we could make a graph showing the success rates by state to see if any stand out as more successful than others. 
2.	We could also make a chart to show the relationship between average backers and the outcomes of the plays, as well as average donation amount to understand how many backers Louise should try to source to fund her play. 
