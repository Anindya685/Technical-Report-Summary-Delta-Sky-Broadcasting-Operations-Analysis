Technical Report Summary: Delta Sky Broadcasting Operations Analysis
Overview
This project presents a comprehensive technical report analyzing and optimizing key field operations for Delta Sky Broadcasting's new satellite TV installations. My work focuses on enhancing efficiency and reducing costs across five critical operational areas: call-centre demand forecasting, inventory management for satellite boxes, engineer job allocation, and engineer vehicle servicing and maintenance. By applying various analytical models and simulation techniques, I've identified actionable insights and provided data-driven recommendations to streamline operations and ensure timely service delivery as subscription volumes grow.

Why This Project is Relevant
In today's competitive service industry, optimizing field operations is crucial for customer satisfaction and cost efficiency. For a broadcasting company like Delta Sky, ensuring timely installations and efficient resource management directly impacts customer retention and profitability. This report provides a practical framework for improving operational components, leading to tangible benefits in service quality and financial performance.

Research Objectives
This report addresses the following key operational components and objectives:

Investigating New Subscription Call Demand: Decomposing historical call-centre data to identify underlying patterns, trends, and seasonal rhythms.

Forecasting New Subscription Call Demand: Comparing and evaluating different seasonal forecasting methodologies (Seasonal Naïve, Seasonal Average, Seasonal Exponential Smoothing) to predict future call volumes accurately.

Optimizing New Subscription Installation Inventory: Simulating a continuous-review (s,Q) inventory policy to minimize holding, ordering, and backorder costs for satellite boxes.

Optimizing Engineer Job Allocation: Formulating and solving a binary linear assignment problem to minimize travel distances for field engineers across installation jobs.

Analysing Engineer Vehicle Servicing and Maintenance: Modelling the queuing system for Saturday vehicle servicing operations using a discrete-event simulation (M/M/2 queuing system) to evaluate mechanic utilization and vehicle wait times.

Methodology
I adopted a rigorous, data-driven approach, leveraging various quantitative methods to analyse and optimize Delta Sky Broadcasting's operations.

Data Sources and Features
Call-centre data: Eight weeks of daily call volumes for new subscriptions (May 1 to June 25, 2023).

Inventory parameters: Daily box demand, opening inventory, reorder point (s), order quantity (Q), holding cost (h), fixed ordering cost (K), and backorder penalty (p).

Engineer allocation data: Mileage matrix between engineers and installation jobs.

Vehicle servicing data: Inter-arrival times and service durations for vehicles.

Data Pre-processing
My data pre-processing involved several crucial steps to prepare the raw data for analysis:

Exploratory Data Analysis (EDA): I began by inspecting the daily call volumes, identifying patterns through centred moving averages and extracting median daily profiles.

Data Cleaning: No missing values were detected in the datasets used for the different analyses.

Data Transformation: For call demand analysis, I used an additive classical model (X 
t
​
 =T 
t
​
 +S 
t
​
 +e 
t
​
 ) to decompose daily call volumes, which was appropriate given the constant amplitude of seasonal swings.

Seasonal Isolation: I subtracted the Centred Moving Average (CMA) from each observation to produce detrended residuals, which were then arranged into a seasonal matrix to derive weekday seasonal components.

Data Processing/Analysis/ Methods used
I employed a multi-faceted approach, combining time series analysis, simulation, and optimization techniques:

Time Series Analysis: For call demand, I used an additive classical model (X 
t
​
 =T 
t
​
 +S 
t
​
 +e 
t
​
 ), centred moving averages (CMA), and seasonal isolation to understand demand patterns.

Forecasting: I implemented and compared Seasonal Naïve (SN), Seasonal Average (SA), and Seasonal Exponential Smoothing (SES) models, evaluating their performance using Mean Error (ME), Mean Absolute Error (MAE), and Root Mean Squared Error (RMSE) for both in-sample and out-of-sample periods.

Inventory Simulation: A seven-day Monte Carlo simulation was built in Excel to model the (s,Q) inventory policy (s=2, Q=10), incorporating probabilistic demand generation and cost calculations (holding, ordering, and backorder costs).

Optimization (Linear Programming): For engineer allocation, I formulated a binary linear assignment problem to minimize total travel mileage for engineers across installation jobs and used Excel Solver with the Simplex LP engine to find optimal solutions.

Queuing Simulation: A discrete-event simulation in Excel was constructed to model an M/M/2 queuing system for vehicle servicing, generating inter-arrival and service times from Exponential distributions and evaluating performance metrics such as wait times and mechanic utilization.

Technologies Used
Microsoft Excel: The primary tool used for data analysis, time series calculations, Monte Carlo simulations, and solving linear programming problems (via Solver).

Statistical Concepts: Time Series Decomposition, Forecasting Models (SN, SA, SES), Monte Carlo Simulation, Linear Programming, Queuing Theory (M/M/2 model).

Key Findings
New Subscription Call Demand
Identified a pronounced weekly seasonal pattern with midweek peaks and weekend troughs, superimposed on a gradual upward trend in June.

A significant uplift in calls was observed following an early-June marketing push.

Forecasting New Subscription Call Demand
Seasonal Exponential Smoothing (SES) showed the best in-sample performance (lowest MAE and RMSE).

Seasonal Average (SA) demonstrated superior out-of-sample accuracy and robustness, making it the preferred model for operational deployment.

New Subscription Installation: Inventory Simulation
The current (s,Q)=(2,10) inventory policy incurs high ordering costs, dominating total inventory expenses.

No backorders occurred in the simulated run, suggesting adequate stock levels for the observed demand.

Engineer Job Allocation
By applying a binary linear assignment model, total engineer travel distance was reduced by 14% (from 28 to 27 miles in a sample set) compared to the manual approach.

This optimization approach is computationally scalable and offers significant long-term savings in fuel costs and vehicle depreciation.

Engineer Vehicle Servicing and Maintenance
The M/M/2 queuing system simulation indicated minimal average wait times (0.19 minutes) per vehicle and balanced mechanic utilization (63-66%).

Occasional brief queues were observed, particularly during demand surges.

Recommendations
Based on these findings, I propose the following integrated recommendations for Delta Sky Broadcasting:

Demand Forecasting:

Implement the Seasonal Average (SA) method for new-subscription call demand forecasting due to its robust out-of-sample performance and operational simplicity.

Incorporate the weekly seasonal component and allow for discrete level shifts in all short-term forecasts.

Inventory Management:

Increase safety stock: Raise the reorder point (s) to 3 to significantly halve stock-out probability with minimal holding cost penalty.

Integrate the seven-day demand forecast into a dynamic s calculation for optimized safety stock.

Consolidate orders across nearby hubs to amortize fixed ordering costs.

Automate replenishment: Embed the (s,Q) logic in the ERP system for automatic purchase orders.

Conduct quarterly reruns of the Monte Carlo model with updated parameters to ensure alignment with evolving demand.

Engineer Job Allocation:

Implement the LP-based assignment algorithm as the standard dispatch tool, allowing call centre staff to generate optimal assignments.

Incorporate fairness constraints (e.g., caps on hours, mileage) to maintain equity among engineers.

Automate the assignment process to push optimal assignments directly to engineers' mobile applications.

Monitor key performance indicators (miles per installation, response time) to track improvements.

Engineer Vehicle Servicing and Maintenance:

Conduct multiple replications and extend the simulation horizon to estimate wait-time percentiles and service level distributions more robustly.

Refine the service time distribution to capture complex repair variability more accurately.

Consider implementing an "express-lane" for vehicles with short predicted service times.

Institute staggered break scheduling to ensure continuous mechanic coverage.

Integrate real booking data to enable dynamic staffing adjustments based on empirical arrival patterns.

By adopting these integrated improvements, Delta Sky can expect to achieve significant reductions in operational costs, stabilize installation lead times, enhance engineer satisfaction, and ensure prompt vehicle readiness, ultimately supporting business growth and service excellence.

