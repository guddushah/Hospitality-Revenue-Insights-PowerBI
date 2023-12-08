# AtliQ Grands Hospitality Revenue Insights

## Problem Statement
AtliQ Grands owns multiple five-star hotels across India. They have been in the hospitality industry for the past 20 years. Due to strategic moves from other competitors and ineffective decision-making in management, AtliQ Grands are losing its market share and revenue in the luxury/business hotels category. As a strategic move, the managing director of AtliQ Grands wanted to incorporate “Business and Data Intelligence” to regain their market share and revenue. However, they do not have an in-house data analytics team to provide them with these insights.

Their revenue management team had decided to hire a 3rd party service provider to provide them insights from their historical data.

### Task List
You are a data analyst who has been provided with sample data and a mock-up dashboard to work on the following task. You can download all relevant documents from the download section.

- Create the metrics according to the metric list.
- Create a dashboard according to the mock-up provided by stakeholders.
- Create relevant insights that are not provided in the metric list/mock-up dashboard

## About AtliQ Grands
#### Some good-to-know stats before starting the building dashboard.
- AtliQ Grands is a five stars hotel chain is operating in 4 cities (Hyderabad, Mumbai, Banglore, Delhi).
- It has 7 properties with branches across these 4 cities.
- The rooms in these properties are categorized into 4 types: Elite, Premium, Presidential, & Standard.
- There are 6 main platforms to book the rooms and some other platforms that are not as effective as others.

### Datasets provided by Codebasics
- **dim_date**
- **dim_hotels**
- **dim_rooms**
- **fact_bookings**
- **fact_aggregated_bookings**

### Key Metrics to include in the Report suggested by the stakeholder

#### Financial Stats
The financial stats added in this report are the typical metrics that are used only in the hospitality sector. This includes revenue, cancellations, room-level pricing etc.

Here is a list of these financial metrics used in the hospitality industry.
1. *Revenue* - a common metric used in every industry.
2. *RevPAR* - Revenue generated per available room.
   - RevPar = Total Revenue / Total Rooms available to Sell
   - Revpar = ADR * Occupancy %
3. *ADR* – Average Daily Rate is the average daily price per room.
   - ADR = Total Rooms Sold Revenue / Number of Rooms Sold

#### Performance Stats
The stats related to performance includes the hotel’s occupancy, cancellation %, room availability and many more.

Here is a list of performance metrics used in the hospitality industry.

1. *Occupancy %*
   - Occupancy % = Total Rooms Occupied / Total Rooms Available
2. *Cancellation %*
3. *SRN* (Sellable Room Nights)
   - SRN is the metric used for available rooms that can be sold. Example: If there are 100 rooms in a hotel and 20 rooms are not available for any XYZ reason, the SRN here is 80.
4. *DSRN* (Daily Sellable Room Nights)
5. *URN* (Utilized Room Nights)
   -URN are the nights utilized by the customers. This can be the checked-in nights. It is considered when the customer ends-up staying.
6. *DURN* (Daily Utilized Room Nights)
7. *BRN* (Booked Room Nights)
    - It is the sum of URN, Cancellation and customers who didn't stay even after bookings.
    - BRN = URN + Cancellation + No Show
8. *DBRN* (Daily Booked Room Nights)
9. *Realisation*
    - It refers to the number of customers bookings received against customers actually stayed 
    - Realisation = URN / BRN
10. *Avg Rating* – Average rating is the average rating given by a customer per booking.
11. *Day Type* – Day is the category of days in a week. Weekday and Weekend. Based on the feedback from stakeholder, we considered Friday and Saturday as weekend and weekdays from Sunday to Thurdsay.
12. *Booking Platforms* – Booking platforms are the modes that are used by customers to book rooms. These include AtliQ’s own booking platform and third-party platforms as well.
13. *Week Number* – Week number is the number of weeks in a year. 
14. *WoW* – Week on Week is the metric to compare the performance change over the week.

### Filters Used
1. **Filter by Properties** - Looking into properties or room class can drill down the problems and challenges faced by hotels. Example: Ratings will help in improving the standards of the room. Availability will help in providing more rooms with the category in high demand.
2. **Filter by City** - This filter helps in knowing the market value of AtilQ.
3. **Filter by Status** - This helps in knowing the revenues generated from the customers who actually checked in.
4. **Filter by Platforms** - Choosing booking platforms provides insights to the marketing team to target accordingly. Also, improving AtliQ’s own platforms for generating direct revenue.
5. **Filter by Month** - To measure monthly performance.
6. **Filter by Week** - To view each week’s performance.

### Mock-up Dashboard
![mock up dashboard_atliq grands](https://github.com/guddushah/Hospitality-Revenue-Insights-PowerBI/assets/40028193/b3b98f28-d005-4a32-936d-df907014fd36)

### Steps taken to build Dashboard
- Imported all the data in Power BI
- Performed Data Transformation using Power Query
- Then, established relationship between the tables, obtained STAR Schema in Data Model View.
- Created calculated columns and measures using DAX (Data Analysis Expression)
- Started building Dashboard

### Data Transformation

#### Created calculated columns in dim_date table
1. Used DAX formula to derive week number from the corresponding date       
- wn = WEEKNUM(dim_date[date])
2. Used DAX formula to derive day type          
- day type =           
 Var wkd = WEEKDAY(dim_date[date],1)        
 return     
 IF(     
  wkd>5,"Weekend","Weekday")     

### Data Model Created

![model](https://github.com/guddushah/Hospitality-Revenue-Insights-PowerBI/assets/40028193/5ee1946e-7e9d-4e9e-b51d-3967b14b3a30)

### Dashboard Created

![pic1](https://github.com/guddushah/Hospitality-Revenue-Insights-PowerBI/assets/40028193/a22cb69c-989e-4c50-919d-ccd52d46502e)

![pic2](https://github.com/guddushah/Hospitality-Revenue-Insights-PowerBI/assets/40028193/6ec77722-a31f-4ff7-8c5e-9ad654c6704f)

#### View Dashboard here 
https://app.powerbi.com/view?r=eyJrIjoiNjZiYTFiMmEtOTNlYy00NjU0LTliNmYtMmM0NWE1N2ZhMTQ3IiwidCI6Ijc5OWU3OTRjLTllYWMtNGUxZi05ZjY0LTE0ODhjYjMyMjRlNiJ9&pageName=ReportSectiondc8143957199bb15912d

Using all the information and data provided by the stakeholders, I analyzed and created this report. This report shows metrics that will help solve the problems faced by AtliQ Grands’s management in generating good revenue.

### Key Insights obtained from the Dashboard

### Key Measures Created
1. **Revenue**
- Revenue = SUM(fact_bookings[revenue_realized])
2. **Total Bookings**
- Total Bookings = COUNT(fact_bookings[booking_id])
3. **Total Capacity**
- Total Capacity = SUM(fact_aggregated_bookings[capacity])
4. **Total Succesful Bookings**
- Total Succesful Bookings = SUM(fact_aggregated_bookings[successful_bookings])
5. **Occupancy %**
- Occupancy % = DIVIDE([Total Succesful Bookings],[Total Capacity],0)
6. **Average Rating**
- Average Rating = AVERAGE(fact_bookings[ratings_given])
7. **No of days**.
- No of days = DATEDIFF(MIN(dim_date[date]),MAX(dim_date[date]),DAY) +1
8. **Total cancelled bookings**
- Total cancelled bookings = CALCULATE([Total Bookings],fact_bookings[booking_status]="Cancelled")
9. **Cancellation %**
- Cancellation % = DIVIDE([Total cancelled bookings],[Total Bookings])
10. **Total Checked Out**
- Total Checked Out = CALCULATE([Total Bookings],fact_bookings[booking_status]="Checked Out")
11. **Total no show bookings**
- Total no show bookings = CALCULATE([Total Bookings],fact_bookings[booking_status]="No Show")
12. **No Show rate %**
- No Show rate % = DIVIDE([Total no show bookings],[Total Bookings])
13. **Booking % by Platform**
- Booking % by Platform = DIVIDE([Total Bookings],               
  CALCULATE([Total Bookings],               
  ALL(fact_bookings[booking_platform])))*100
14. **Booking % by Room class**
- Booking % by Room class = DIVIDE([Total Bookings],                
  CALCULATE([Total Bookings],               
  ALL(dim_rooms[room_class])             
  ))*100
15.**ADR**
- ADR = DIVIDE( [Revenue], [Total Bookings],0)
16.**Realisation %**
- Realisation % = 1- ([Cancellation %]+[No Show rate %])
17. **RevPAR**
- RevPAR = DIVIDE([Revenue],[Total Capacity])
18. **DBRN**
- DBRN = DIVIDE([Total Bookings], [No of days])
19. **DSRN**
- DSRN = DIVIDE([Total Capacity], [No of days])
20. **DURN**
- DURN = DIVIDE([Total Checked Out],[No of days])
21. **Revenue WoW change %**
- Revenue WoW change % =                  
Var selv = IF(HASONEFILTER(dim_date[wn]),SELECTEDVALUE(dim_date[wn]),MAX(dim_date[wn]))               
var revcw = CALCULATE([Revenue],dim_date[wn]= selv)            
var revpw =  CALCULATE([Revenue],FILTER(ALL(dim_date),dim_date[wn]= selv-1))               
return             
DIVIDE(revcw,revpw,0)-1                   
22. **Occupancy WoW change %**
- Occupancy WoW change % =                            
Var selv = IF(HASONEFILTER(dim_date[wn]),SELECTEDVALUE(dim_date[wn]),MAX(dim_date[wn]))                       
var revcw = CALCULATE([Occupancy %],dim_date[wn]= selv)                         
var revpw =  CALCULATE([Occupancy %],FILTER(ALL(dim_date),dim_date[wn]= selv-1))                    
return             
DIVIDE(revcw,revpw,0)-1           
23. **ADR WoW change %**
- ADR WoW change % =                       
Var selv = IF(HASONEFILTER(dim_date[wn]),SELECTEDVALUE(dim_date[wn]),MAX(dim_date[wn]))                      
var revcw = CALCULATE([ADR],dim_date[wn]= selv)                  
var revpw =  CALCULATE([ADR],FILTER(ALL(dim_date),dim_date[wn]= selv-1))                   
return                 
DIVIDE(revcw,revpw,0)-1                 
24. **Revpar WoW change %**
- Revpar WoW change % =                   
Var selv = IF(HASONEFILTER(dim_date[wn]),SELECTEDVALUE(dim_date[wn]),MAX(dim_date[wn]))                   
var revcw = CALCULATE([RevPAR],dim_date[wn]= selv)                 
var revpw =  CALCULATE([RevPAR],FILTER(ALL(dim_date),dim_date[wn]= selv-1))                         
return                
DIVIDE(revcw,revpw,0)-1                   
25. **Realisation WoW change %**
- Realisation WoW change % =                            
Var selv = IF(HASONEFILTER(dim_date[wn]),SELECTEDVALUE(dim_date[wn]),MAX(dim_date[wn]))                     
var revcw = CALCULATE([Realisation %],dim_date[wn]= selv)                           
var revpw =  CALCULATE([Realisation %],FILTER(ALL(dim_date),dim_date[wn]= selv-1))                       
return                     
DIVIDE(revcw,revpw,0)-1                        
17. **DSRN WoW change %**
- DSRN WoW change % =                        
Var selv = IF(HASONEFILTER(dim_date[wn]),SELECTEDVALUE(dim_date[wn]),MAX(dim_date[wn]))                     
var revcw = CALCULATE([DSRN],dim_date[wn]= selv)                        
var revpw =  CALCULATE([DSRN],FILTER(ALL(dim_date),dim_date[wn]= selv-1))                       
return                    
DIVIDE(revcw,revpw,0)-1                    











