# City of Baltimore Crime Data Ingestion Pipeline & Analysis from 2011-2016
* Baltimore Crime Data Ingestion & Analysis
  * Introduction
  * Project Description
  * Dataset Description
  * Technologies
  * Project Architecture
  * Tutorial
  * Pre-requisites

# Introduction
Baltimore is the most populous city in the U.S. state of Maryland, fourth most populous city in the Mid-Atlantic, as well as the 30th most populous city in the United States, with a population of 585,708 in 2020. Baltimore has a higher crime rate than similarly sized metro areas and the Baltimore's level of violent crime is much higher than the national average.

# Project Description
The project is related to crimes committed in Baltimore and to ask important questions such as The total number recorded? Number of crimes committed in each year? Where are the most crimes committed? Types of crimes committed? What type of weapons were used to committed these crimes? and What time were these crimes committed. The provided data will help discover the answers to these questions and more.

The key goals of the project are:

* develop a data ingestion pipeline that will use to transform the data and ingestion into a PostgreSQL database for the purpose of analysis
* build analytical dashboard that will make it easy to discern the trends and digest the insights.

# Dataset Description
The City of Baltimore Crime Data can be found [here](https://data.world/data-society/city-of-baltimore-crime-data) on the Data World website. It contains information about the crimes committed in Baltimore, Maryland, US.

The dataset includes the following columns:
* crimedate  
*	crimetime  
*	crimecode  
*	location 
*	description  
*	inside_outside 
*	weapon  
*	post  
*	district 
*	neighborhood 
*	location_1  
*	total_incidents 

# Technologies
We are going to use the following technologies for this project:

* Data Warehouse (DWH): PostgreSQL
* Transforming data: Pandas
* Data Visualization: Tableau

# Project architecture
The end-to-end data pipeline includes the next steps:

* import the dataset from into pandas;
* moving the data from the lake to a DWH;
* transforming the data in the DWH and preparing it for the dashboard;
* dashboard creating.

You can find the detailed information on the diagram below:


# Tutorial
This tutorial contains the instructions you need to follow to reproduce the project results and can be found here.

# Pre-requisites
* [Docker](https://www.docker.com/products/docker-desktop/))
* [Anaconda](https://www.anaconda.com/products/distribution)
* [VSCode](https://code.visualstudio.com/Download)


