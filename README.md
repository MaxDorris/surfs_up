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

#### Deliverable 2: December Analysis

For this task I repeated the steps from D2, only I changed the filtering month to December.

<p align="center">
  <img width=auto height="500" src=images/dec_summary.png>
  </p>
  
- 1517 data points were collected in previous Decembers.
- The December temperature data ranges from 56˚F to 83˚F, has a mean of 71.04˚F, and has a standard deviation of 3.75˚F.

### Conclusion
It appears as though June is the better month to open based on temperature data alone. I personally prefer surfing in hotter weather, and I believe this is the majority-held preference. I also prefer to surf when there is zero chance of being struck by lightning. Assuming that this preference is also held by a majority of surfers and that lightning has a greater chance of striking when it rains, I'll make two other queries that focus on precipitation data for these months to see if the choice in opening month is still obvious.

<p align="center">
  <img width=auto height="500" src=images/June_prcp_summary.png>
  </p>

<p align="center">
  <img width=auto height="500" src=images/Dec_prcp_summary.png>
  </p>

It seems as though rain is not a major inhibitor in either month. Hawaii experienced less total rain in previous June than Decemeber months. However, hurricane season in Hawaii falls between the months of June to November. This small piece of information renders this entire analysis slightly pointless because a surf shop's opening day should probably be at the start of a season without hurricanes, though we still managed to use SQLite and SQLalchemy to process a database without the need for the PostgreSQL interface! :)
