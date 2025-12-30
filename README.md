# Reducing Uncertainty: Predicting Hotel Booking Cancellations

This project analyzes hotel booking data to identify customer cancellation patterns and predict the likelihood of cancellations using machine learning models. By quantifying booking uncertainty, the project aims to help hotel operators mitigate revenue erosion and optimize operational efficiency.

## Team Members (Group A)

* Abhinav Mahajan 


* Peter Ngo 


* Joel John 


* Babatunde Olasupo 


* Akshaya Reddy 



## The Problem: The High Cost of Uncertainty

Cancellations pose a significant threat to hotel profitability due to several factors:

* 
**Revenue Erosion**: Hotels operate on thin 5-15% margins. A cancelled room is a perishable asset that expires with $0 value.


* 
**Operational Chaos**: Labor typically accounts for 30-40% of operating expenses. Overstaffing occurs when rosters are built on non-actualized occupancy.


* 
**Revenue Pressure**: Last-minute cancellations often require aggressive discounting to fill rooms, which reduces the Average Daily Rate (ADR).



## Dataset Overview

* 
**Source**: The dataset contains booking information for a city hotel and a resort hotel.


* 
**Original Scope**: 119,390 total bookings.


* 
**Project Focus**: A final cleaned dataset of 76,730 records specifically for the **City Hotel**.


* 
**Features**: 21 features covering the complete booking lifecycle, including lead time, guest profiles, pricing, and distribution channels.



## Project Approach

The analysis was conducted using **R Programming** and followed a structured data science workflow:

1. **Data Cleaning & EDA**:
* Identified and removed 2,576 extreme lead-time outliers to normalize the distribution.


* Treated the data as cross-sectional by removing date-specific columns like year and month.




2. **Feature Engineering**:
* Created binned lead-time variables (e.g., L30, L60, L240+).


* Developed binary indicators for guest characteristics such as "is_repeated_guest" and "deposit_commitment".




3. **Machine Learning Modeling**:
* 
**Logistic Regression**: Used for its probabilistic nature and explainability to identify key "levers" of cancellation.


* 
**Decision Tree (rpart)**: Used to capture complex, non-linear patterns and create rule-based segmentation.





## Model Performance

Both models demonstrated high reliability in predicting cancellations:

| Metric | Logistic Regression 

 | Decision Tree 

 |
| --- | --- | --- |
| **Accuracy** | 77.34% | 76.29% |
| **True Negative Rate (Specificity)** | 87.21% | 88.12% |
| **True Positive Rate (Sensitivity)** | 63.23% | 58.96% |

## Strategic Insights & Recommendations

### Key Findings

* 
**The Lead Time Trap**: Bookings made more than 3 months in advance are highly unstable and should be risk-adjusted in forecasts.


* 
**Customer Engagement**: Any special request (e.g., a crib or high floor) drastically lowers the risk of cancellation as the guest has mentally "checked in".


* 
**Market Segment Risk**: The "Groups" segment is the primary source of volatility (61% cancellation rate), while "Direct" bookings are highly stable.



### Turning Data into Revenue

1. 
**Risk-Adjusted Pricing**: Charge a premium for flexibility on high-lead-time bookings.


2. 
**Dynamic Rostering**: Schedule housekeeping based on "Predicted Occupancy" rather than just bookings to save ~10% in labor costs.


3. 
**The "Nudge" Campaign**: Implement automated emails to high-risk guests 10 days prior to arrival to confirm intent or free up inventory early.



## Tools Used

* 
**Language**: R 


* 
**Key Libraries**: `tidyverse`, `dplyr`, `ggplot2`, `rpart`, `rpart.plot`
