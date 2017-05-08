---
layout: post
title:  "Vermont State Police Traffic Fatalities (2010-Present)"
date:   2017-05-08
author: David Jordan
---

For my data set I looked at the data set of [Vermont State Police Traffic Fatalities (2010-Present)](https://docs.google.com/spreadsheets/d/1KATnZ17Ksh2poIOcTH1x6MU2R9KmTRGPidLs5mkGgok/edit?usp=sharing).

The first piece of information I wanted to figure out was how the fatalities are spread across the days of the week. After realizing that I was having such a difficult time because the API field name for day and year are flipped in the original dataset, I finally found that the query "https://data.vermont.gov/resource/j2mj-z2ji.json?$group=year&$select=year, count(*) as total" produced data in the form I was looking for.

This showed that Sunday was by far the most common day for fatalities with 66, 150 percent more than the next most common days, Friday and Saturday.

The next piece of information I looked at was the road conditions at the time of the crash. For this I used "https://data.vermont.gov/resource/j2mj-z2ji.json?$group=conditions&$select=conditions, count(*) as total" which shows that at the vast majority of crashes took place at a time when the authorities had labeled the road conditions as "good." 215 crashed took place in "good" conditions, compared to 53 in "slick."

Using the query "https://data.vermont.gov/resource/j2mj-z2ji.json?$group=role&$select=role, count(*) as total&$order=role" showed that the vast majority of fatalities were drivers at the time with 208, followed by passengers at 60, pedestrians at 15 and bicycles at 4.

Lastly, I wanted to use the $where parameter to look at some of the data broken down by age of the driver. Because people under 25 are usually considered to be more reckless drivers I broke the data out by under 25 to look at the role during the fatality. I used the query "https://data.vermont.gov/resource/j2mj-z2ji.json?$select=role, age&$where=age < 25 AND role = 'Driver'" to break down by age and to find only those who were within that age group and driving at the time of their death.

In all, there were 44 people who met these two conditions. The youngest person was 16.7 at the time of their crash. In total, drivers between 16.7 and 25 represented 15.3 percent of all traffic fatalities and over 21.1 percent of all driver fatalities. I was curious how this compares with the general population. In all Vermont is an older state in terms of population, and census data shows that 13.7 percent of the population fell in this age group during the last census, so they are disproportionately prone to fatal accidents. 
