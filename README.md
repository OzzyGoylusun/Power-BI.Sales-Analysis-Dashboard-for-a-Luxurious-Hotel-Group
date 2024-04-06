# Comprehensive Sales Analysis Dashboard for a Luxurious Chained-Brand Hotel

## Table of Contents

- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Findings](#findings)
- [Recommendations](#recommendations)


### Project Overview
---
This Power BI Dashboard project is intended to assist a chained-brand hotel conglomerate with its strategies for customer acquisition and retention as well as numerous methods to increase revenue. A comprehensive analysis of each sales transaction that took place between the years of **2015 and 2017** was undertaken in an effort to most effectively meet the project objectives.

<p align="center">
  <img src="https://github.com/OzzyGoylusun/Power-BI.-A-Luxurous-Hotel-Bookings-Dashboard/blob/main/Visuals/Hotel%20Logo.jpeg"
 alt="Hotel Logo"
 width=250>
</p>

In this respect, a two-paged interactive dashboard with slicers and filters was put together, including **critical KPIs, pie/donut charts, line graphs** as well as **a map graph** to highlight the best performing countries thus far in terms of sales.

The first page of the dashboard includes a number of key metrics per hotel category, such as:

- Average Duration of Stay, Daily Rate & Lead Time
- Polluted Conversion Rate (inc. Non-Refundable Bookings)
- Distribution of Market Segments and Conversion Channels

<p align="center">
  <img src="https://github.com/OzzyGoylusun/Power-BI.-A-Luxurous-Hotel-Bookings-Dashboard/blob/main/Visuals/Dashboard%201st%20Page.png"
 alt="Dashboard 1st Page"
 width=850>
</p>

The second page of the dashboard takes a more granular approach, zeroing on

- Cumulative Sum
- The sales figures from the angle of countries and agents responsible for bookings
- YoY % and MoM % Growth Rates

<p align="left">
  <img src="https://github.com/OzzyGoylusun/Power-BI.-A-Luxurous-Hotel-Bookings-Dashboard/blob/main/Visuals/Dashboard%202nd%20Page.png"
 alt="Dashboard 2nd Page"
 width=850>
</p>

### Data Sources

Booking Transaction Data: The dataset utilised for this analysis and visualisation piece is hotel_bookings.xlsx, containing detailed information about each booking transaction.

### Tools

- Power BI Desktop - Data Manipulation, Analysis and Visualisation
  - [Download here](https://www.microsoft.com/en-us/download/details.aspx?id=58494)
- Excel - Data Manipulation
  - [Download here](https://microsoft.com)

### Data Preparation

In the initial data preparation phase, I performed the following tasks:

1. Inspecting and investigating the dataset
2. Importing of the dataset into the Power BI ecosystem
3. A number of data manipulation tasks
4. Data modelling to ensure consistency between the actual and customised table

### Exploratory Data Analysis

EDA involved exploring the commercial data to answer some key questions, including but not limited to:

- What is the overall sales trend over these three years?
- What are the yearly trends for average duration stay and daily rate?
- How do the YoY (i.e., Year-over-Year) and MoM % growth rates look?
- Which countries and travel agents performed the best in terms of attracting most number of guests during this period and also each year?


### Data Analysis

After investigating, importing and manipulating certain sections of the dataset, I decided to write a customised DAX function that would enable to calculate all sales YTD (i.e, year-to-date) and PY (i.e., prior year) in order to demonstrate YoY %, which was crucial to highlight potential fluctuations in sales figures in years as well as in certain seasons:

```dax
Sales YTD = 
VAR MaxYear = YEAR(MAX('Calendar'[Date]))
RETURN 
CALCULATE(
    [Total Sales], 
    VALUE('Calendar'[Year]) = MaxYear
)
```

```dax
YoY % = DIVIDE([Sales YTD]-[Sales PY], [Sales PY], 0)
```

### Findings

The critical analysis results are summarised as follows:

1. Approximately **97% of all guests** turn out to be **first timers**. While this figure may be rather appealing from a customer acquisition point of view, it runs the risk of leading to an alarming customer churn rate for the corporation, should it fail to convert them into loyal guests.
2. Customers tend to book reservations roughly **100 days** earlier toward both summer and winter seasons.
3. Approximately **80% of all bookings** derive from **travel agents and tour operators**, instead of the hotel's own channels.
4. As a chained-brand hotel group based in Europe, the majority of its guests have come from **Portugal,  Great Britain, France, Germany and Spain.**


### Recommendations

Based on the analysis, I recommend the following actions:

- Invest in brand building and particular customer retention strategies to minimise the damage resulting from a potential high churn rate.
- Time and align specific marketing activities 100 days ahead of both summer and winter seasons to appeal and hence bring in the maximum number of guests possible to the hotel group.
- Further promote relationships with the company's all travel agents and tour operators.
- Concentrate more marketing efforts in the US, Canada and Australia to attract prospective customers, in an attempt to lead the brand to globally grow beyond Europe and drive further sales.

  
### Limitations

As the dataset was based upon a static file, it is inherently deprived of any prospective data which might impact subsequent strategical and/or tactical decisions that the hotel conglomerate may undertake.

### References

No references needed as part of this project.
