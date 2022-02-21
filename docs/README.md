---
layout: page
title: Our travel through datas
description: >
  Here you should be able to find everything you need to know to accomplish the most common tasks when blogging with Hydejack.
hide_description: true
sitemap: false
---
0. this unordered seed list will be replaced by toc as unordered list
{:toc}

**It is Raining Cats and Dogs, what do you think about going out?** 


Did you ever sit a minute and start thinking about how the world keeps moving and how
nothing can stop it?

 **Scary, isn't it?** 
 
{:.note}

Movement has raised the interest of many authors for centuries. For instance, Sapiens, a book by Yuval Noah Harari traces the development
of our species from the pre-historic age until now. It is interesting to see how much 
of a role mobility played in how we developed as a species and how the world was shaped.

We can today trace when humans came to inhabit certain places or moved to new islands by
looking at when certain megafauna went extinct. These animals who had slow reproductive
cycles and never encountered and learned to fear humans were quickly decimated as humans
spread. Fast forward to today, the digital age and widespread adoption of cell phone 
technology mean we are able to study our history more quickly and with higher resolution
than ever before. 

The authors of the paper **Friendship Mobility: User Movement in Location-Based Social Networks** questioned how and why do we move? The paper focuses on three main aspects of human mobility: geographic movement, temporal dynamics, and the social network, based on two datasets which looks at all the check-ins made by the users of two Social Network: "Gowalla" and "Bright kite " A second dataset allowed them to connect the network of friends.
To help you with an overview, let us show you on a  world map where those users live! 
Don't hesitate to play with it. 

**Note that by turning the map really fast and stopping at once you may find your next place of vacation. If you want to make this trip with the team, [let us know !](mailto:le_mec_cool96@hotmail.ch) We will love to!**
{:.note title="Cool tips"}
{%include user_by_country.html%}{:.lead width="800" height="500" loading="lazy"}

\
The authors explored different aspects of the human movement dynamics such as *traveling 
to friends’ homes, the influence of friends on human mobility, and temporal and 
geographic (high frequency) periodicity of individuals’ movement*. They also found that our movement is
influenced by non-uniform population density. In addition, models for periodic and 
social mobility of people are proposed. To discover all about the results of their 
research, we encourage you to click on **"Where it's started"** on the cover page to satisfy
your thirst for knowledge.

We felt there were important questions worth understanding by extending the temporal 
dynamics portion of the paper. While the authors of the paper looked into hourly and 
weekly mobility trends we want to widen this time frame to look at how people move over 
months and years. With lengthening the time horizon we also wanted to broaden the 
external factors that we are looking at to see how mobility behaves with respect to 
other parameters ( such as temperature variance and holiday ). As such additive data 
is not available for different countries (in a homogeneous fashion), it encourages us 
again to restrict our dataset to only the United States for our analysis. 


Then, let's zoom a bit on our chosen country to understand how user's are distributed 
and clustered between cities.


{%include testhouse-of-user2.html%}{:.lead width="800" height="500" loading="lazy"}




**Let's now deep into this analysis !**

We start by first looking at a natural way to understand time, seasons. There are many things that differ between them including weather,
temperature, holidays. So, it will be a good starting point to our story.

## Seasons:

We are always aware of the season we are in. From the amount of daylight, to the temperature, to the holidays there are subtle shifts all around
us that let us know the time of year. Our first question was to see if the season we are in affected mobility. This question was meant to be a
starting point and we hoped to dig deeper into weather and holidays which are an innate part of the differences between seasons. 
 
In order to analyze differences in mobility, we have to determine a statistic that we want to stand in as a proxy for mobility in order
to determine if there are differences between groups. One statistic we calculated was looking at how far a check-in is 
from a user's home location. We decided to take this measure and for each user calculated their average distance from home by day. 
If this measure is lower it means that a user did not move on average that day as far from her home. 
If the measure is higher it means that the user on average moved further from home. 
If the user was on a long-distance trip then this average would be very high over the duration of the trip. 
 
Our next step was to split our data into different seasonal groups and to look at
 their probability distribution functions.



If there is a clear separation here then we have some evidence that there are differences between the seasons. 
![seasons](..\assets\img\seasons_pdf.png){:.lead width="800" height="500" loading="lazy"}
Comparaison between seasons.
{:.figcaption}

We show how the average temperature changes by season as well as the precipitation.



## Average temperature by season plot


![temperature](..\assets\img\season_temp_new.png){:.lead width="800" height="500" loading="lazy"}
The average seasonal precipitation level over the USA. Data taken from averaging the daily gridded data
{:.figcaption}


## Average rain by season


![rain](..\assets\img\season_pr_new.png){:.lead width="800" height="500" loading="lazy"}
The average seasonal precipitation level over the USA. Data taken from averaging the daily gridded data.
{:.figcaption}


| Spring          |Holidays    | Count            | Summer         | Holidays                                                   |Count      | Autumn        | Holidays                                | Count           | Winter     | Holidays                                                                         | Count |
|-----------------|------------|:----------------:|----------------|:----------------------------------------------------------:|:---------:|---------------|:---------------------------------------:|:---------------:|------------|:--------------------------------------------------------------------------------:|:-----:|
| Spring 2008     |Memorial Day| 1                | Summer 2008    | Independence Day, Labor Day                                |2          | Autumn 2008   |Columbus Day, Veterans Day, Thanksgiving | 3               | Winter 2008| Christmas Day, New Year's Day, Martin Luther King Jr. Day, Washington's Birthday |4      | 
| Spring 2009     |Memorial Day| 1                | Summer 2009    | Independence Day (Observed), Independence Day, Labor Day   |3          | Autumn 2009   | Columbus Day, Veterans Day, Thanksgiving| 3               | Winter 2009| Christmas Day, New Year's Day, Martin Luther King Jr. Day, Washington's Birthday |4      |
| Spring 2010     |Memorial Day| 1                | Summer 2010    | Independence Day (Observed), Independence Day, Labor Day   |3          | Autumn 2010   | Columbus Day                            | 1               |            |                                                                                  |       | 
|=================|============|==================|================|============================================================|===========|===============|=========================================|=================|============|==================================================================================|=======|
{:.fine.scroll-table}


These are two areas that we are going to dive into deeper into the next section of the report. 


## Weather
As the days colder do we also slow down? As they heat up do we speed up?
 With modern technology we are capable of handling the hottest of days and coldest
 of nights. But the weather still can make planes stop, can still cause huge traffic
 jams, and can generally disrupt how we move. 
 
In this section we take a look into the weather's impact on mobility in the United States. For climate data we have the daily precipitation level and temperature over the USA. We tie that data to the home location of their houses taking the time component of the check-ins and that data is appended to the data corresponding to each check-in.
This first graph is exploratory and shows in color the current average temperature by region over the selected period. The height of the bars represents the average for that area of the statistic that we introduced above. (average distance from home by user by day) You can use this to look at temperature and distance traveled in the United States and explore the data yourself!


<iframe src="..\assets\plots\coolplot.html" width="100%" height="600px"></iframe>


We also take a more rigorous treatment of the data by splitting our data into groups and applying a statistical test to tell us if there is a significant difference between the groups. 
We also take another step in limiting all check-ins to be within 100km of the users house.
 The reason behind this is that users who are further from this are likely to be outside of the impact of the weather that we are trying to measure. 
We took two passes at the data. The first pass we look at precipitation and the second we look at temperature. 
For precipitation we made two groups, days with rain and days without rain. 

For temperature the groups we denote as cold (below 17 degrees C), 
lukewarm (between 17 and 26 degrees celsius) and hot (greater than 26 degrees C) 
using the maximum temperature of that day. 
Graphical comparisons between each group don't tell us much 
because we have so much data, clustered around a small area, but in this case even smaller differences between groups can be statistically significant. Note the means and the medians in the two tables below. The results were similar for both Brightkite and Gowalla. 

**Precipitation Table :**

|Data Set           |rainy(mean, median)[km] |not rainy(mean, median)[km] |
|:-----------------:|:----------------------:|:--------------------------:|
| Brightkite        |   (8.2829, 3.0248)     |    (8.5633, 3.1356)        |
| Gowalla           |   (9.5227, 4.5285)     |    (10.067, 4.7001)        |
|===================|========================|============================|


**Temperature Table :**

|Data Set           | hot(mean, median) [km] | lukewarm(mean, median)[km]|   cold(mean, median) [km] |
|:-----------------:|:----------------------:|:-------------------------:|:-------------------------:|
| Brightkite        |   (8.4078, 3.1913)     |    (8.6586, 3.1796)       |    (8.2795, 2.9133)       |
| Gowalla           |   (9.9271, 5.0069)     |    (10.218, 4.7242)       |    (9.4917, 4.1819)       |
|===================|========================|===========================|===========================|


We make use of the Kruskal–Wallis nonparametric test and it tells us that there is a significant difference between the groups in both Gowalla and Brightkite. We applied this test to the mean values. This tells us that when it rains people are likely to travel less on average. Also when it is a moderate temperature people are likely to travel more on average than when it is hot or cold. Lastly, when it is brrrrrr! Cold outside, people travel the least on average.

## Holiday
The main hypothesis we want to examine is that do holidays affect the movement 
pattern and if so how? For instance, it is expected that people tend to have 
longer trips from their houses during holiday affected days as they might travel 
to new and unusual places.

For analyzing the influence of the holidays on movement we have put days into two 
categories: 

* Holidays and two days after and before that as the days which are affected by the holiday
* Dates that are at least two days far from holiday (non affected by holidays).

For this end, we have plotted the weekly average of the traveled distance of users
 on each day for weeks over the timespan that Brightkite and Gowalla was used.
 There we can visually observe a match between most of the rises in the mean 
 traveled distances and the incidence of holidays (green vertical shades). 
 To verify this observation, we carried out proper statistical tests (considering non-normal distribution of the data)
 and double checked our speculation (the influence of holiday on travel metrics such mean distance traveled) with Kruskal–Wallis test.

![holiday](..\assets\img\holiday.png){:.lead width="800" height="500" loading="lazy"}


# Conclusion
The insane amount of data that the recent electronic revolution has enabled us to 
lay our hands allows us to do things beyond our imagination, one of which is 
obtaining a better understanding of human movement patterns. 

Here we tried to study how external temporal parameters over yearly periods affect the mobility patterns. Our first attempt divides years into seasons, however here we could not detect huge differences between the movement metrics we have for different seasons. We then decided to have a more thorough look at the data inside each season considering what distinguishes seasons such as distribution of holidays, temperature, and precipitation levels.
This closer look helped us understand how each of the aforementioned parameters 
impact the mobility pattern. We observed shorter means of trips on rainy days. 
On cold days, we had smaller trip length on average. 

In addition, as expected, holidays make the length of trips longer which means people tend to get out of 
their usual movement pattern. Surprisingly, the reason for not detecting significant
 difference between for example summer and winter might lie right here that the higher
 density of holidays in winter compensates the damping effect of weather on 
 movement patterns in winter. Nevertheless, we have investigated those parameters 
 and proved that external parameters such as climate status and being holiday or 
 not have an impact on movement patterns. 
 
 Such conclusions and the extent of such impact can be a great help for companies such Uber and Lyft or even airlines to 
 adjust their supply to the demands to improve their services.


