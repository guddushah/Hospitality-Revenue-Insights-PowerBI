# AtliQ Grands Hospitality Revenue Insights

## Problem Statement
AtliQ Grands owns multiple five-star hotels across India. They have been in the hospitality industry for the past 20 years. Due to strategic moves from other competitors and ineffective decision-making in management, AtliQ Grands are losing its market share and revenue in the luxury/business hotels category. As a strategic move, the managing director of AtliQ Grands wanted to incorporate “Business and Data Intelligence” to regain their market share and revenue. However, they do not have an in-house data analytics team to provide them with these insights.

Their revenue management team had decided to hire a 3rd party service provider to provide them insights from their historical data.

### Task List
You are a data analyst who has been provided with sample data and a mock-up dashboard to work on the following task. You can download all relevant documents from the download section.

- Create the metrics according to the metric list.
- Create a dashboard according to the mock-up provided by stakeholders.
- Create relevant insights that are not provided in the metric list/mock-up dashboard

#### Mock-up Dashboard
![mock up dashboard_atliq grands](https://github.com/guddushah/Hospitality-Revenue-Insights-PowerBI/assets/40028193/b3b98f28-d005-4a32-936d-df907014fd36)

#### Datasets provided by Codebasics
- dim_date.csv
- dim_hotels.csv
- dim_rooms.csv
- fact_bookings.csv
- fact_aggregated_bookings.csv 


#### Steps for building the Dashboard
- Imported all the data in Power BI
- Performed Data Transformation using Power Query
- Then, established relationship between the tables, obtained STAR Schema in Data Model View.
- Created calculated columns and measures using DAX (Data Analysis Expression)
- Started creating Dashboard

#### Data Model Created

![model](https://github.com/guddushah/Hospitality-Revenue-Insights-PowerBI/assets/40028193/5ee1946e-7e9d-4e9e-b51d-3967b14b3a30)

#### Dashboard Created

![hdb1](https://github.com/guddushah/Hospitality-Revenue-Insights-PowerBI/assets/40028193/93484401-fad4-4012-8d67-f7f1c22a463e)

![hdd2](https://github.com/guddushah/Hospitality-Revenue-Insights-PowerBI/assets/40028193/81ceb150-a856-4095-963d-72c0ad04d695)

Using all the information and data provided by the stakeholders, I analyzed and created this report. This report shows metrics that will help solve the problems faced by AtliQ Grands’s management in generating good revenue.

#### Key Metrics to include in the Report

##### Financial Stats
The financial stats added in this report are the typical metrics that are used only in the hospitality sector. This includes revenue, cancellations, room-level pricing etc.

Here is a list of these financial metrics used in the hospitality industry.
- Revenue - a common metric used in every industry.
- RevPAR - Revenue generated per available room.
   - RevPar = Total Revenue / Total Rooms available to Sell
   - Revpar = ADR * Occupancy %
- ADR – Average Daily Rate is the average daily price per room.
   - ADR = Total Rooms Sold Revenue / Number of Rooms Sold

##### Performance
The stats related to performance includes the hotel’s occupancy, cancellation %, room availability and many more.

Here is a list of performance metrics used in the hospitality industry.

These are the main financial statistics that we need to look at micro to macro level.
1. Occupancy %
   - Occupancy % = Total Rooms Occupied / Total Rooms Available
2. Cancellation %
3. SRN (Sellable Room Nights)
4. DSRN (Daily Sellable Room Nights)
5. URN (Utilized Room Nights)
6. DURN (Daily Utilized Room Nights)
7. BRN (Booked Room Nights)
    - BRN = URN + Cancellation + No Show
8. DBRN (Daily Booked Room Nights)
9. Realisation
    - Realisation = URN / BRN



#### Key Insights obtained from the Dashboard









