# Comprehensive Sales Analysis Dashboard for a Luxurious Chained-Brand Hotel

## Table of Contents

- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Findings](#findings)
- [Recommendations](#recommendations)

### Project Overview
---
This Power BI Dashboard project is intended to assist a chained-brand hotel conglomerate with its strategies for **customer acquisition and retention** as well as numerous methods **to increase revenue**. 

A comprehensive analysis of each sales transaction that took place between the years of **2015 and 2017** was taken as a basis in an effort to most effectively meet the project objectives described above.

<p align="center">
  <img src="https://github.com/OzzyGoylusun/Power-BI.-A-Luxurous-Hotel-Bookings-Dashboard/blob/main/Visuals/Hotel%20Logo.jpeg"
 alt="Hotel Logo"
 width=250>
</p>

In this respect, a two-paged interactive dashboard with slicers and filters was put together, including **critical KPIs, pie & donut charts, line & bar graphs** as well as **waterfall charts and a map graph** to highlight the YoY % growth rates and best performing countries thus far in terms of generating sales.

To be more specific, the first page of the dashboard includes a number of key metrics overall and also per each hotel category, such as:

- Average Duration of Stay, Daily Rate & Lead Time
- Polluted Conversion Rate (inc. Non-Refundable Bookings)
- Distribution of Market Segments and Conversion Channels

<p align="center">
  <img src="https://github.com/OzzyGoylusun/Power-BI.-A-Luxurous-Hotel-Bookings-Dashboard/blob/main/Visuals/Dashboard%201st%20Page.png"
 alt="Dashboard 1st Page"
 width=850>
</p>

The second page of the dashboard takes a more granular approach, zeroing on

- Cumulative Sum of All Sales
- Sales Figures of Countries and Agents responsible for bookings
- YoY % (i.e., Year-over-Year) and MoM % (i.e., Month-over-Month) Growth Rates

<p align="center">
  <img src="https://github.com/OzzyGoylusun/Power-BI.-A-Luxurous-Hotel-Bookings-Dashboard/blob/main/Visuals/Dashboard%202nd%20Page.png"
 alt="Dashboard 2nd Page"
 width=850>
</p>

### Data Sources

*Booking Transaction Data:* The dataset utilised for this analysis and visualisation work is called **hotel_bookings.xlsx**, containing very detailed information about each booking transaction.

### Tools

- Power BI Desktop - Data Manipulation, Analysis and Visualisation
  - [Download here](https://www.microsoft.com/en-us/download/details.aspx?id=58494)
- Excel - Data Manipulation
  - [Download here](https://www.microsoft.com/en-us/microsoft-365/excel)

### Data Preparation

In the initial data preparation phase, I performed the following tasks:

1. Inspecting the dataset at hand
2. Importing the dataset into the Power BI ecosystem
3. Undertaking a number of data manipulation tasks
4. Performing data modelling to ensure consistency between the actual and subsequent customised tables

### Exploratory Data Analysis

EDA involved exploring the transaction data to answer some key questions, including but not limited to:

- What is the overall sales trend over these three years?
- What are the yearly trends for average duration stay and average daily rate?
- How do the YoY and MoM % growth rates look?
- Which countries and travel agents performed the best in terms of attracting most number of guests during this period?

### Data Analysis

After investigating, importing and manipulating certain sections of the dataset, I needed to resort to writing various customised DAX measures that would enable me to calculate all sales YTD (i.e, year-to-date) and also PY (i.e., prior year) in order to demonstrate the YoY % growth rate, which was crucial to highlight potential fluctuations in sales figures between years as well as in certain seasons:

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

1. Approximately **97% of all guests** turn out to be **first timers**. While this figure may be rather appealing from a customer acquisition point of view, it runs the risk of leading to an alarming customer churn rate for the corporation in future, should it fail to convert them into loyal guests.
2. Customers tend to book their reservations roughly **100 days** earlier ahead of both summer and winter seasons.
3. Approximately **80% of all bookings** source from both offline and online channels of **external travel agents and tour operators** with which the firm cooperates.
4. As a chained-brand hotel group based in Europe, the majority of its guests have come from **Portugal,  Great Britain, France, Germany and Spain**.

### Recommendations

Based on the analysis above, I recommend the following actions:

- Invest in particular brand building and customer retention strategies to minimise the damage resulting from a potential high churn rate of the first timers.
- Align marketing activities a minimum of 120-150 days ahead of both the summer and winter seasons to bring in the highest number of guests possible to the hotel group.
- Begin creating and fostering the hotel group's own distribution channels of sales while strengthening the relationships with the company's all travel agents and tour operators.
- Consider concentrating more marketing efforts in the US, Canada and Australia to attract prospective customers, in an attempt to lead the brand to globally grow beyond Europe and to drive further sales.

### Limitations

As the dataset was based upon a static excel file, it is inherently deprived of any prospective data which can impact subsequent strategical and/or tactical decisions that the hotel conglomerate may choose to make.

### References

No references needed as part of this project.
