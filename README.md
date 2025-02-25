# Predictive Machinery Analysis Using Machine Learning

## Overview
Predictive maintenance is crucial for businesses that rely on machinery. It helps prevent unanticipated breakdowns by monitoring machine status and predicting failures before they occur. This project focuses on analyzing a manufacturing process where machine failures can happen due to various reasons. The goal is to identify contributing factors and predict failures accurately.

## Problem Definition
This project aims to answer the following key questions through data analytics:
- What factors contribute to machine failure?
- How can we predict when a machine is likely to fail?
- Which failure mode is the most likely to occur?

## Data Sources
The dataset used in this project is provided by Stephan Matzka, School of Engineering - Technology and Life, Hochschule für Technik und Wirtschaft Berlin. It is publicly available at:
[AI4I 2020 Predictive Maintenance Dataset](https://archive.ics.uci.edu/dataset/601/ai4i+2020+predictive+maintenance+dataset)

## Data Description
The dataset consists of 10,000 records with 14 features, including:
- **UID:** Unique identifier (1 to 10,000)
- **Product ID:** Quality variant (L = Low, M = Medium, H = High) with a serial number
- **Air Temperature [K]:** Normalized with a standard deviation of 2 K around 300 K
- **Process Temperature [K]:** Normalized with a standard deviation of 1 K, added to air temperature plus 10 K
- **Rotational Speed [rpm]:** Derived from power and overlaid with noise
- **Torque [Nm]:** Normally distributed around 40 Nm (std dev = 10 Nm)
- **Tool Wear [min]:** Accumulates wear based on product quality (H/M/L = 5/3/2 minutes per process)
- **Machine Failure Label:** Binary indicator (1 = failure, 0 = normal operation)

## Failure Modes
Machine failure consists of five independent failure types:
1. **Tool Wear Failure (TWF):** Occurs between 200-240 mins of tool usage (120 instances in dataset)
2. **Heat Dissipation Failure (HDF):** Happens when the air-to-process temperature difference is below 8.6 K and rotational speed is below 1380 rpm (115 instances)
3. **Power Failure (PWF):** Occurs when power output (torque * speed) is below 3500 W or above 9000 W (95 instances)
4. **Overstrain Failure (OSF):** If tool wear * torque exceeds predefined limits based on product quality (98 instances)
5. **Random Failures (RNF):** Each process has a 0.1% failure probability, occurring randomly (5 instances)

A machine failure is recorded if at least one of these conditions is met.

## Methodology
The following steps outline the project workflow:
1. **Data Collection** – Obtain and organize raw dataset
2. **Data Exploration & Processing** – Clean, visualize, and understand dataset characteristics
3. **Dimensionality Reduction & Feature Selection** – Select important features for modeling
4. **Exploratory Data Analysis (EDA)** – Identify trends and correlations in data
5. **Model Selection & Training** – Compare multiple machine learning models for failure prediction
6. **Model Performance Evaluation** – Assess accuracy, precision, recall, and F1-score
7. **Performance Visualization** – Plot results to interpret model effectiveness

## Conclusion
This project aims to leverage machine learning to enhance predictive maintenance, reducing unexpected breakdowns and improving machine efficiency. By analyzing historical data, we can gain insights into failure patterns and take proactive measures to prevent downtime.

## License
This project is for educational and research purposes only. Refer to the dataset source for licensing details.

---

### Contributors
- [tejashwini-vemavarapu]

For any inquiries or contributions, feel free to reach out.

