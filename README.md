a3-otelford-gagnemaw
===============

## Team Members

1. Grace Telford otelford@uw.edu
2. Will Gagne-Maynard gagnemaw@uw.edu

## Visualizing Trends in Bike Share Usage

This visualization aims to answer the question: when are people using the Bay Area bike share? 

The graphic shows the number of riders along the top 10 most used routes in the Bay Area binned by different units of time: (1) hour of the day, (2) day of the week, and (3) month of the year. The buttons allow the user to switch between these three views. The user can scroll over each line to see the start and end points of the route. Clicking on the line changes its color, which persists through transitions between the different views so that the user can explore the different trends for a given interesting route.

We used the first six months of data from the [Bay Area Bike Share](http://www.bayareabikeshare.com/datachallenge). Our visualization uses the start and end points of all the bike trips during that time, as well as the start and end times of those trips.

## Running Instructions

View the visualization on our [GitHub Pages site](http://cse512-15s.github.io/a3-otelford-gagnemaw/).

Alternatively, download this repository and run `python -m SimpleHTTPServer 9000` and access this from [http://localhost:9000/](http://localhost:9000/).

## Story Board

We are catering to users who are interested in how ride share usage varies as a function of time. To facilitate data exploration, we want to allow the user to look at the number of rides broken down by different units of time: time of day, day of the week, and season (perhaps weather too). We will use bike share data from the San Francisco Bay Area.

Our initial plan for this visualization is to create line graphs of number of riders vs. some unit of time using different group by commands. We will include toggles so that the user can choose which unit of time they are interested in. The total number of riders vs. time across all stations will be shown, as well as the number of riders for the top ~10 most popular routes (defined as start point/end point pair). The lines will be highlighted as the user scrolls over each, and some additional information/statistics will be shown as text (providing "details on demand").

We chose a line graph because this is a natural way of presenting temporal data. The highlighting allows a user to focus on any interesting trend that jumps out at them, and this combined with the "details on demand" facilitates data exploration.

If we achieve this goal early enough, we will then expand our visualization to include data from Washington, D.C. and Boston. The user can then compare trends across different cities (which may be particularly interesting in the case of seasonal trends).

Our story board diagram can be viewed [here](Storyboard.pdf?raw=true).


### Changes between Storyboard and the Final Implementation

Our final visualization allows the user to look at the number of rides vs. hour of the day, day of the week, and month of the year (rather than season). We ended up just using the first six months of data, so it didn't make sense to look at season. 

We decided to only display the number of rides along the top 10 most popular routes. If we included the total number of riders, that line would lie so far above the lines for individual routes that the plots would look strange. We also decided to only show the name of the route on scroll over, rather than additional statistics, for the sake of clarity.

We added the ability to change the line color by clicking on a line. The color change persists through transitions so that the user can explore trends with different units of time for a given interesting route.

There was not enough time for us to expand to a comparison across cities.


## Development Process

We first downloaded, explored, and cleaned our dataset. Static versions of the graphs we envisioned were made and .tsv files containing the actual data we wanted to plot were generated. Will led this effort.

Next, we both had to work through some JavaScript/D3 tutorials to get a feel for these tools. We were both new to web development. Using tutorials as a starting point, we each made line charts that changed the line style on mouseover.

Will created a visualization that showed number of rides vs. hour for the 10 most popular routes and displayed the name of the route on mouseover.

Grace then added the buttons and ability to change the view between the three different datasets (breakdowns vs. different units of time).

Will added the capability to click the line to change color and have that color persist.

Grace took the lead on the writeup and organization.

All of this, including working through D3 tutorials, took roughly 50-70 hours (25-35 hours each). Getting familiar with D3 was of course time consuming. Figuring out how to bind each new dataset to the lines when a button is pressed took a lot of time; it turned out to be a syntax issue that was not obvious from web resources and it took a lot of fiddling to figure this out.
