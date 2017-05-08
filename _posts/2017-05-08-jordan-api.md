---
layout: post
title:  "Vermont State Police Traffic Fatalities (2010-Present)"
date:   2017-05-08
author: David Jordan
---

For my data set I looked at the data set of [Vermont State Police Traffic Fatalities (2010-Present)](https://docs.google.com/spreadsheets/d/1KATnZ17Ksh2poIOcTH1x6MU2R9KmTRGPidLs5mkGgok/edit?usp=sharing).

The first piece of information I wanted to figure out was how the fatalities are spread across the days of the week. After realizing that I was having such a difficult time because the API field name for day and year are flipped in the original dataset, I finally found that the query "https://data.vermont.gov/resource/j2mj-z2ji.json?$group=year&$select=year, count(*) as total&$order=total"

This showed that Sunday was by far the most common day for fatalities with 66, 150 percent more than the next most common days, Friday and Saturday.
