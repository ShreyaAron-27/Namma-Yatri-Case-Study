# Namma-Yatri-Case-Study

## 1. Project Objective
Namma Yatri aims to enhance operational efficiency, improve ride experience, and optimize resources based on demand and customer behaviour in Bengaluru. This study uses Tableau to analyses key metrics and visualize actionable insights.  
________________________________________
## 2. Data Preparation
Tables Used:
-	Trips
-	Trip_Details
-	Assembly
-	Payment
-	Duration
### Relationships (Not Joins):
-	Trips.tripid = Trip_Details.tripid
-	Trips.faremethod = Payment.id
-	Trips.duration = Duration.id
-	Trips.loc_from = Assembly.ID
### Checks:
-	Null values handled
-	Field types validated
________________________________________
## 3. KPIs Created
KPI	Logic	Chart Type
Total Trips	COUNTD(tripid)	KPI card
Total Fare	SUM(fare)	KPI card
Total Distance	SUM(distance)	KPI card
Fare per Km	SUM(fare) / SUM(distance)	KPI card
________________________________________
## 4. Analysis & Visualizations
### A. Demand & Revenue Trends
- Trip Demand by Hour: Line chart using Duration.duration
- Revenue by Hour: SUM(fare) grouped by duration  
### B. Conversion Analysis
-	Quote Conversion Rate by Hour: SUM(end_ride) / SUM(searches_got_quotes)
-	Trip Funnel: Stages: Searches → Estimates → Quotes → Not Cancelled → Completed
### C. Customer Behaviour
-	Cancellation Rate: Using 1 - customer_not_cancelled and 1 - driver_not_cancelled
-	Payment Preference: Bar chart using Payment.method (from Payment table)
### D. Geographic Patterns
-	Zone vs Time: Assembly vs Duration, colored by COUNTD(tripid)
-	Top Zones by Trip Count and Revenue: Bar charts sorted descending
________________________________________
## 5. Dashboard Structure
-	Top Section: KPIs (horizontal layout)
-	Middle Section: Demand, Revenue, Conversion, Cancellation
-	Bottom Section: Heatmap and zone-level insights
-	Filters: Duration, Assembly, Payment method applied dashboard-wide
________________________________________
 ## 6. Key Insights
-	Evening and morning hours see highest ride demand and revenue.
-	Customer cancellations are more frequent than driver cancellations.
-	Wallets and UPI are the most preferred payment modes.
-	Zones like MG Road and Whitefield generate highest trip volume.
________________________________________
## 7. Recommendations
### Operational:
- Increase driver allocation during 8–10 AM & 6–9 PM
- Focus on reducing customer cancellations via smoother UX
### Marketing:
- Target promotions in high-demand zones
- Offer loyalty benefits for digital payment users
