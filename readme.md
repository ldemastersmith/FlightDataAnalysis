# Flight Data Analysis
## by Luke DeMaster-Smith


## Dataset

* In this investigation, I chose a dataset of U.S. flight data that was [provided by the American Statistical Association](http://stat-computing.org/dataexpo/2009/the-data.html) and originally came from the U.S. Bureau of Transportation Statistics.

* The dataset was quite large:
  * A single year (2008) has 7 million flights and each flight has 29 associated data fields of data.
  * There are 22 years worth of data.
  * Given the size of the dataset (and the constraints of my computer), I chose to focus my investigation on flight delays during the most recent year of data, 2008. 


## Summary of Findings

  * I assessed many of the 29 parameters against Arrival Delay, ultimately arriving at the following variables of particular interest:
    * Weather Delay
    * Destination
    * Airline
    * Day / Week of Year

My initial goal was to assess which features best predict (or correlate to) the length of arrival and flight delays. When starting the investigation, I was hoping to find that some variable (such as departure time) that had a surprisingly strong correlation with arrival and departure delay. Upon exploring the data however, I found that arrival and departure delays actually had very weak correlations with non-delay variables.

After creating a correlation heat map, I noticed that the correlation of arrival and departure delays with weather delays changes noticeably (from approximately 0.29 to approximately 0.74) when there happens to be a non-zero weather delay. Although an R^2 value of 0.74 is not extremely strong, I found the change in that R^2 value to be quite interesting. Since weather is a function of time and location, I also chose to look at the destination, airline, and day of year for each flight. After creating multiple calendar and scatter plots of this data, I ultimately concluded that these variables were some of the more influential parameters associated with arrival and departure delays in 2008.

While I did not come to a deterministic model to estimate arrival and departure delays (since even this subset of parameters is quite large and has many permutations), I did observe a number of interesting cycles and trends within the data. Some of the these include:
 * Weather / Arrival / Departure delays appear to be longer over the holidays (go figure), but also in February and early summer, which I did not expect.
 * Some airports have reliably long delays (such as O'Hare), while others (such as SFO) are prone to large changes in delay length.
 * If you want to avoid long delays, try to travel during the fall.


## Key Insights for Presentation

For the presentation, I chose to focus on just arrival delays and to not discuss departure delays. I did this based on feedback I received from an independent reviewer, and because I did not want to complicate the takeaways of the analysis with a surplus of charts.

With that in mind, I stated the presentation by introducing the arrival delay and weather delay variables. I then introduce the top 10 airlines and destinations to set the stage for why my later charts ended up focusing on things like American Airlines and Dallas/Fort Worth.

Once all the variables of key interest have been introduced, I then provide a heat map to explore how weather delay "interacts" with the day of year. I do this to set the stage for the plot type that I found to be the most insightful - calendar plots of arrival delay.

For the final round of plots, I introduce calendar plots of median arrival delay. I find these to be especially insightful once they are filtered by various additional variables, such as destination or airline. When creating these plots, I made sure to select a diverging color palette so that any negative arrival delay (i.e., early flights) would show up as a distinctly different color.

The most notable change I made to any plots upon putting tem in the slide deck was to create side-by-side distribution plots for the arrival and weather delay distributions. I also made sure to plot the weather delay, destination, and airline plots in different colors to make it clear that the reader was viewing a different variable each time.