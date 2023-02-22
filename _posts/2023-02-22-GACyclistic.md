---
title: Google Analytics Capstone- Cyclistic Bike Share
header:
  overlay_color: "#32333b"
  overlay_image: /assets/images/post1_2023-02-17/andreas-haimerl-cv8iKu2ONM-unsplash.jpg
  image_description: "Picture of bikes taken by Andreas Haimerl on Unsplash"
  show_overlay_excerpt: false
excerpt: This is a case study about Cyclistic bike share from the Coursera Google Analytics Capstone course. The goal of this project was to determine factors that differentiate annual members and casual bike riders.
date: February 22, 2023
toc: true
toc_sticky: true
tags:
  - Google Analytics
  - Tableau
  - Capstone
  - Data processing
  - Data analysis
  - Data Viz
---

This is a case study about Cyclistic bike share from the **Coursera Google Analytics Capstone course**. The goal of this project was to determine factors that differentiate annual members and casual bike riders. These factors are then used to develop a marketing campaign that aims to increase the membership conversion rate.

The tools I used for this project were **R and Tableau**. Check out the <a href="https://github.com/hjkissinger/Coursera-GA-Capstone/tree/main/R-scripts">R Script</a> to follow along or head to my <a href="https://public.tableau.com/views/GoogleAnalyticsCapstoneCyclisticBikeSharePTI/CyclisticBikeShareCaseStudy?:language=en-US&:display_count=n&:origin=viz_share_link">Tableau</a> viz story to see the end result!

# Scenario

The first quarter of 2020 just came to a close. The marketing team at Cyclistic, a Chicago bike share company, wants to develop a targeted marketing campaign that converts casual customers into members. You have access to historical bikeshare data of the past four quarters (2019 Q2/Q3/Q4 and 2020 Q1).

### Stakeholder Goal
> Cyclistic aims to increase its number of annual memberships by targeting casual members through a marketing campaign.

### Business Task
> Using historical data, determine key factors which differentiate casual riders from annual members.

# Data Descriptions

The descriptions below are based on Google's ROCCC analysis. Each description was given a rating of zero to five, _five meaning meets expectations_.

**Reliable:** _Rating_ 2/5 <br>
The data is located in an aws cloud warehouse in .zip files that are organized by financial quarter. There is currently no encrypted password or user permissions set for these files. _An encrypted password or user permissions should be added to the data files to protect the integrity and improve the security of the stakeholder’s data._

**Relevant:** _Rating_ 4/5 <br>
The data is relevant to the business problem. However, gender and birth year columns in the data are either missing or contain nulls. _It is recommended that the gender of members is added for a robust analysis on the demographics of Cyclistic Bikes’ customers._

**Original:** _Rating_ 5/5 <br>
The data is proprietary and collected from the original source.

**Comprehensive** _Rating_ 2/5 <br>
The data is organized by trip id and not customer id. This makes it difficult to determine the frequency of bike use per customer. _If the same customer makes multiple trips, this can introduce bias into the analysis._ 

**Current:** _Rating_ 5/5 <br>
The data is current to the case study setting (end of Q1 in 2020).

**Cited:** _Rating_ 5/5 <br>
The data is from a trustworthy source.

# Data Prep Tasks

* Set user permissions and/or encrypted file passwords
* Add gender and birth year to all datasets (if attainable)
* Collect or obtain customer ids to determine frequency of users' trips (if attainable)

# Data Processing

For the purpose of this case study, trip ids were counted as individual customers. Here are the steps I used to transform and clean my data in preparation for analysis: 

* Standardize column names
* Add a column to 2020 Q1 data for the calculated 'tripduration' 
* Select relevant columns
* Add column to designate quarter-year (ex. Q2_2019)
* Combine dataframes
* Separate DateTime column into Date and Time columns
* Check and change data structures to coorect data type
* Add month, date, year, day of week, and hour columns
* Drop extra date columns
* Remove duplicates and NAs
* Standardize usertypes to match stakeholder definitions 
* Remove bikes 'from HQ' and negative trip duration values

Not interested in the data cleaning R-documentation? Skip to [analysis R-Documentation](link here) or the [analysis summary](link here)!
