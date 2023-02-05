# A Surf-Focused Weather Analysis

## Overview
### Purpose and Background
This served as an introductory example for using SQLite and SQLalchemy to process real data and perform practical analyses. My task was to find the best month to open a surf shop in Hawaii. By analyzing historic temperature data from nine active weather stations in the area, a statistically-fortified decision was made possible for the business owner. For this mini-project, the task was simiplified to detmermining the better month out of June and December to open the shop.

### Method and Results
In the starter-file, hawaii.sqlite, the *'measurement'* table contained the columns: id, station, date, prcp, and tobs. These abbreviations describe columns for **row index**, **station id** where row data was collected, **date** on which row data was collected, **precipitation data* in inches**, and **observed temperature** data in Farenheit. The *'station'* table contained the columns: id, station, name, latitude, longitude, and elevation. The names of each station used in this analysis are listed below:

<p align="center">
  <img width=auto height="500" src=images/station_names.png>
  </p>

I started by creating a SQLite database engine to store the hawaii.sqlite database. I then reflected the engine onto an automapped SQLite "schema" to store the relationships and classes of the database. Then I created two table references, "Measurement" and "Station". I then created a session object to make changes to these tables using SQL-like or class-based queries.

#### Deliverable 1: June Analysis

To create a summary of all historical data collected by all weather stations in previous years, I created a query selecting the **tobs** column of the **Measurement** table (*Measurement.tobs*). I filtered the output to only return temperature data on the same row as data values containing the month of June. I then transformed the resulting extraction to a list, and from this list, a dataframe.

<p align="center">
  <img width=auto height="500" src=images/june_summary.png>
  </p>
  
- 1700 data point were collected in -previous Junes.
- The June temperature data ranges from 65˚F to 85˚F, has a mean of 75.94˚F, and has a standard deviation of 3.26˚F.

#### Deliverable 2: Eligible Employees for the Mentorship Program

For this task I repeated the step from D2, only I changed the filter month to December.

<p align="center">
  <img width=auto height="500" src=images/dec_summary.png>
  </p>
  
- 1517 data points were collected in previous Decembers.
- The December temperature data ranges from 65˚F to 83˚F, has a mean of 75.94˚F, and has a standard deviation of 3.26˚F.

### Conclusion
Based on the table in Deliverable 2, it appears as though a litle over 72,000 positions will need to be filled in the years to come. This is a lot of employees to train, but luckily there are quite a few mentor-eligible employees for most position types. I made the following table to display this:

<p align="center">
  <img width=auto height="500" src=Resources/Images/mentor_counts.png>
  </p>
  
So now we know just how many potential mentors exist in each area of the company, and since it's pretty easy to see that these numbers don't add up to 72,000 we'll need another table to better visualize the vacancy-mentor disparity. I went ahead and made one using the previous table and the **retiring_titles** table from Deliverable 2:

<p align="center">
  <img width=auto height="500" src=Resources/Images/ratio.png>
  </p>
  
Now we're talking. Not only do we now see that there are zero potential mentors for mangement positions, we can easily see which positions will provide the largest mentor pools for new employees based on the position-mentor ratio. It's not looking good for the senior engineer mentors. This may push hiring managers to temporarily seek engineers with more experience than what has been required in the past. Fortunately, there will only two management vacancies to fill!
