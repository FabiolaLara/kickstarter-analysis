# Kickstarting with Excel

## Overview of Project
> In this project, we have a datasheet(worksheet) which contains information about the fundraising recolected from diferents countries 
in order to invest in diferent campaigns.
We will analyze the relationship between the amount goal and the launched date of the campaigns, the number of campaigns launched in different years and months, so we could realize wich ones were success, failed or canceled.

### Purpose
> Throught the worksheet provided we have to use somo tools in excel in order to get the enough data to accomplish an analysis for the campaigns.
## Analysis and Challenges
To analyse this worksheet, was neccesary to add some columns with some information, so we would be able to get the charts required.

To start with, I had to add a new colum called "date created conversion", where a value was converted to a regular date due the "lauched_date" column provided was in Unix timestamp form, in this case we use the **formula**:=(((J2/60)/60)/24)+DATE(1970,1,1), where "J2" is the column where the Unixstamp is located, the rest of the values are constants values, then, another colum was created and called: "year", to extract the year of the date converted, we use the next formula:[Year()](https://support.microsoft.com/en-us/office/year-function-c64f017a-1354-490d-981f-578e8ec8d3b9?ui=en-us&rs=en-us&ad=us).
Another requrement was to extract the "month" of the regular date, for this case as the chart required asked for the month in text form, we converted the date directly into a text with the next formula: [text](https://support.microsoft.com/en-us/office/text-function-20d5ac4d-7b94-49fd-bb38-93d29371225c).Following with this analysis using the "Category and Subcategory" column, we add two columns called: "parent category" and "subcategory", we will fill them by separating the "Category and Subcategory" values into the two columns mentioned already. The way we do this is: In the tool bar choose Text to column icon,--> "A converter text to columns wizard will appears", Inside the "Converter Text to columns Wizard":
  * Select "Delimited" and click "Next."
  * Uncheck the "Tab" box and check "Other."
  * Place a backslash ( / ) in the box, then click "Next."
  * Select "Text" from the "Column data format."
  * Click "Finish."
Continuing with the rest of the analysis, we create the corresponding pivot tables to show the requiered information.
To create them, we choose: Insert --> Pivot Table --> Select the data range to use --> Nex worksheet --> OK. Once it was created, we can select the fields to be filtered and create the table requiered, finally we create a graph by choosing: Insert menu --> chart. I must say that we can modify the characteristics of the graph by taping double click in the bar chart, a format chart window will appear to change the format of the chart. 

`Note`
Learn more about the use of [Unix timestamps]: (https://websiteseochecker.com/blog/what-is-timestamp/).

`More Help`[TimestampConverter](https://www.epochconverter.com)
### Analysis of Outcomes Based on Launch Date
![Theater Outcomes By Launch Date](/assets/images/Theater_Outcomes_vs_Launch.png)
In this line graph we can observe how values are represented according to the total number of campaigns in the different months in the periods of the years showed in the previous graph. For this graph were taken only the succesful, canceled and failed fields and it also specifies the "parent category" as theater, denoting that the shape is similar to a bell shape, although there is a representative difference between the succesful and failed campaigns both show an increment at the beggining, then a peak in May month where also both suffered a drop fall, showing the month of "May" as their highest point througt the line graph.
### Analysis of Outcomes Based on Goals
> ![Outcomes Based on Goals](/assets/images/Outcomes_vs_Goals.png#gh-light-mode-only)
At first glance we can observe there is a considered variability in the line graph, we can see that ranges were created or classes knowed in an statistic term, the tarjet for these ranges is to classified the "outcomes" fields according the amount goal with an wide class of about $5000 for each range. We can see that the highest points are represented when the amount in a range was the second lowest, on the other hand the second highest point is where the amount is one of the highest, wich is in the nine range. The behaviour in this line graph is similar to a mirror due that, while the "succesful" projects follow their line, the "failed" project are showed in the opposite side of that line, we have to say that this effect gets a lap in ranges seven and eleven, were we can conclude that that bigger range was not enought to mantein the project alive.
### Challenges and Difficulties Encountered
> My Challenges
To start with: I had some troubles in converting the date to obtain the month, given that It was un "Unix format", then I realized I had to use ths formula: =(((J2088/60)/60)/24)+DATE(1970,1,1).
Secondly: To convert a number month in text, was also difficult, because the position of values in the date cells had and specific order, so when you want to apply "month" function it displays wire numbers, so I had to change the order of the date so excell could recognize the position of the month ans extract it. 
Third: This challenge still being a challenge until now, today 31/march/2022. The third line graph can not shows any value for the "canceled projects", I don´t know why, but after applyng the formula to sort the information with the requiered paramethers doesn´t display the values. There are "canceled" projects in some differents ranges, but they just aren´t display, I have worked and spent time a lot. 
## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?
1.  The amount of campaigns on december were almmost the same, which give us almost the 50% of certainty in our projects.
2.  For some unknow reason there were any canceled campaigns on October.
- What can you conclude about the Outcomes based on Goals?
I could say that the average for these projects are in the main half of the stablished goal, mainly the projects could have a hight success if the range is before the median goal.
- What are some limitations of this dataset?
I could say that the "name" field is not suitable to manage data due there are many simbols and unnecessary brakets which could difficulty to filter any oher information.
- What are some other possible tables and/or graphs that we could create?
There are some possibilities, one is sorting by Country, so we could realize about likes and dislikes for people, also we could have an idea what kind of people live there (adults, childs, teens, etc).
Another is sorting by the currency  given that we could realize if there is a signig¡ficant difference in our goal, then we could reduce maybe some costs in order to have more successful.
Another is sorting by backers_count so we could know who are the most representaive in our projects and could have an influence in the public in order to make campaings more successful.
