---
layout: post
title: Optimizing home-work distance in Paris
description: ""
modified: 2013-05-31
tags: [subway, metro, paris, optimisation]
image:
  feature: abstract-2.jpg
---

When I first arrived in Paris I was daunted by the median commuting duration of its habitant to work. It used to be around 20 minutes in 2004 and slipped to 35 minutes in 2014 according to the INSEE.
Often people refers to the distance there is between their workplace and their home, however that does not correlate with the time spent.

Knowing where my workplace would be, I tried to optimize the closest possible living locations in term of duration.


The solution written in Python consisted of:

+ For each principal workplace locations (I defined 14 of them)
+ Define an approximately 10km by 10km grid with GPS coordinate around Paris with a resolution so as to parse the result under a week
* Fetch adresses for each $HOME GPS coordinates using Google Maps
* Ask the subway company RATP for the distance between the workplace and $HOME adresses within the server limits and fetch the results using BeautifulSoup
* Generate a heatmap

The process took around 3 days without getting my IP banned.

Here is an example of the heatmap for people working in the south west of Paris:
![](images/paris3.png "Heatmap example")

Limits of this approach:

* It only reflects the state of the commuting network on a particular date. The analysis should be expanded over a year with off-peak and peak hours.
* Does not take into account the confort of the ride
* Will I be able to get a seat?
* Is this subway line clean?
* Does not take into account the frequency of problem. Some metro lines are known to be less efficient than others, but the metro company RATP is reluctant to disclose data on this subject.
* Does not take into account other means of transportation such as bike sharing system, foldable bikes, etc..

Findings:
- As I thought the shortest distance does not correlate to the shortest duration. You can see that if someone works in the west @La Défense and lives close to the Gare de Lyon RER subway station, it can take 23 minutes for 10,97 km (6,82 mi). On the other hand someone living in Levallois can take 45 minutes for a 2,5 km (1,55 mi) commute.

You can see this on the La Défense heatmap:
![](images/paris2.png "La Defense heatmap")

In the end I managed to find a place less than 5 minutes away from the office.
The estimated gain over a year is approximately **5 days**, when going 5/7 days to the office and going out downtown once a week compared to the average commuting time.

![Optimizing home-work distance project](images/paris1.png "The project.")


[You can access the project in French](https://dl.dropboxusercontent.com/u/10657425/OptimizingWorkplace/index.html)
