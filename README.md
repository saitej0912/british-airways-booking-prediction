# British Airways Customer Booking Prediction

![Status](https://img.shields.io/badge/Status-Completed-brightgreen.svg)
![Python](https://img.shields.io/badge/Python-3.11-blue.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)

## 📌 Project Overview

This project was completed as part of the **British Airways Data Science Job Simulation on Forage**. The objective was to analyze customer booking behavior and build a predictive machine learning model to understand factors influencing purchasing decisions.

**Key Achievement:** Built a Random Forest model achieving **86% accuracy** in predicting customer booking behavior, with **purchase lead time identified as the strongest predictor** of booking success.

---

## 📊 Dataset Summary

| Property           | Details                                  |
|--------------------|------------------------------------------|
| **Total Records**   | 50,000                                   |
| **Total Features**  | 14                                       |
| **Target Variable** | booking_complete (Binary: 0 or 1)        |
| **Missing Values**  | 0 (complete dataset)                      |
| **Class Distribution** | 85% non-bookers, 15% bookers           |

### Features Breakdown

**Numeric Features (8):**
- `num_passengers`: Number of passengers in booking
- `purchase_lead`: Days between purchase and departure
- `length_of_stay`: Duration of stay at destination
- `flight_hour`: Hour of flight departure (0-23)
- `flight_duration`: Total flight duration in hours
- `wants_extra_baggage`: Extra baggage purchased (1/0)
- `wants_preferred_seat`: Preferred seat purchased (1/0)
- `wants_in_flight_meals`: In-flight meals purchased (1/0)

**Categorical Features (5):**
- `sales_channel`: Channel of booking (Internet, Mobile)
- `trip_type`: Type of trip (RoundTrip, CircleTrip, OneWay)
- `flight_day`: Day of week (Mon-Sun)
- `route`: Flight route (799 unique routes)
- `booking_origin`: Customer location (104 unique countries/regions)

---

## 🎯 Key Findings

### Model Performance

| Metric           | Non-Bookers | Bookers | Overall           |
|------------------|-------------|---------|-------------------|
| **Precision**    | 0.86        | 0.63    | 0.83 (weighted)   |
| **Recall**       | 0.99        | 0.09    | 0.86 (accuracy)   |
| **F1-Score**     | 0.92        | 0.16    | 0.81 (weighted)   |

**Cross-Validation Results (5-Fold):**
- Mean Accuracy: **0.8615**
- Standard Deviation: **±0.0007**
- **Conclusion:** Model performs consistently across all folds with no overfitting

### Confusion Matrix

           Predicted: No    Predicted: Yes
Actual: No 8,422 82
Actual: Yes 1,359 137

**Interpretation:**
- ✓ Correctly identified non-bookers: **8,422** (high specificity)
- ✗ Missed actual bookers: **1,359** (low sensitivity - class imbalance issue)
- Only **137 of 1,496** actual bookers were correctly identified

---

## 🔝 Top Predictive Features

### Feature Importance Ranking (Top 10)

| Rank | Feature              | Importance | Insight                                  |
|-------|---------------------|------------|------------------------------------------|
| 1     | `purchase_lead_log`  | 0.133      | Most important: When far in advance customer books |
| 2     | `purchase_lead`      | 0.131      | Raw purchase lead time also significant  |
| 3     | `route_freq`         | 0.124      | Route popularity matters                  |
| 4     | `flight_hour`        | 0.110      | Departure time influences decisions      |
| 5     | `booking_origin_freq`| 0.100      | Geographic frequency patterns             |
| 6     | `length_of_stay_log` | 0.074      | Transformed stay duration                 |
| 7     | `length_of_stay`     | 0.073      | Raw stay duration                         |
| 8     | `flight_duration`    | 0.068      | Flight length matters                     |
| 9     | `num_passengers`     | 0.040      | Group size has lower impact                |
| 10    | `wants_in_flight_meals` | 0.019   | Add-on purchases minimal effect           |

### Business Insights

- Purchase lead time is the strongest predictor — when customers book matters more than who they are.
- Routing patterns, flight timing also play important roles.
- Add-ons like baggage, meals have minimal predictive impact.
- Model is highly accurate at identifying non-bookers but performs poorly on booking recall due to class imbalance.

---

## 🛠 Methodology & Approach

1. Exploratory Data Analysis (EDA) on 50,000 records.
2. Data preprocessing with encoding and log transformations.
3. Random Forest model development with default params.
4. Evaluation using precision, recall, F1 score, cross-validation.
5. Feature importance extraction to interpret drivers.

---

## 💡 Business Recommendations

- Focus marketing on early purchase lead times with incentives.
- Optimize spend on popular routes and flight times.
- Improve model using SMOTE, class weighting, and advanced algorithms.

---

## 📁 Project Structure

british-airways-booking-prediction/
├── data/
│ └── customer_booking.csv
├── notebooks/
│ └── analysis.ipynb
├── visualizations/
│ ├── feature_importance.png
│ └── distribution_plots.png
├── presentation/
│ └── Predicting_Customer_Booking_Behavior.pptx
├── README.md
├── requirements.txt
└── .gitignore

---

## 🚀 Getting Started

### Installation

git clone https://github.com/saitej0912/british-airways-booking-prediction.git
cd british-airways-booking-prediction
pip install -r requirements.txt
jupyter notebook

text

---

## 👤 Author

**VEMAPURAM SANJEEVI SAI TEJESWAR REDDY (saitej0912)**

- 📧 sanjeevisaitejeswarreddy@gmail.com
- 💼 [LinkedIn](https://www.linkedin.com/in/sai-tejeswar-20a866156/)
- 🐙 [GitHub](https://github.com/saitej0912)

---

## 📄 License

This project is licensed under the MIT License.

---

## 🙏 Acknowledgments

This project was completed as part of the British Airways Data Science Job Simulation on Forage.  
Thanks to the Open Source community for the Python libraries.

---

