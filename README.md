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

#### Datasets in the Database
- dim_date.csv
- dim_hotels.csv
- dim_rooms.csv
- fact_bookings.csv
- fact_aggregated_bookings.csv

#### Key Metrics for Hospitality Domain
1. Occupancy %
   - Occupancy % = Total Rooms Occupied / Total Rooms Available
2. RevPar (Revenue Per Available Rooms)
   - RevPar = Total Revenue / Total Rooms available to Sell
   - Revpar = ADR * Occupancy %
3. ADR (Average Daily Rate)
   - ADR = Total Rooms Sold Revenue / Number of Rooms Sold
4. SRN (Sellable Room Nights)
5. DSRN (Daily Sellable Room Nights)
6. URN (Utilized Room Nights)
7. BRN (Booked Room Nights)
   - BRN = URN + Cancellation + No Show
8. Realisation
   - Realisation = URN / BRN



