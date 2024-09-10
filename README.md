# Workforce Call Analytics Project

## Overview

This project focuses on analyzing key performance metrics within a contact center, specifically targeting areas crucial for Workforce Management (WFM). Metrics such as Average Handle Time (AHT), service level adherence, call reasons, and sentiments are analyzed to optimize agent skill routing between chat and inbound queues. The goal is to provide actionable insights for improving service levels and ensuring they are met daily.

## Table of Contents

- [Overview](#overview)
- [Objectives](#objectives)
- [Value and Application](#value-and-application)
- [How the Data Was Colloected](#how-the-data-was-collected)
- [How to Run he Project](#how-to-run-the-project)
- [Dataset](#dataset)
- [Data Cleaning and Preparation](#data-cleaning-and-preparation)
- [Analysis Plan](#analysis-plan)
  - [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
  - [Statistical Analysis](#statistical-analysis)
- [Power BI Functionalities](#power-bi-functionalities)
- [Excel Functionalities](#excel-functionalities)
- [Insights and Recommendations](#insights-and-recommendations)
  - [Insights](#insights)
  - [Recommendations](#recommendations)
- [Limitations](#limitations)
- [Skills Showcased](#skills-showcased)
- [Future Work](#future-work)
- [Acknowledgements](#acknowledgements)
- [Contact](#contact)

## Objectives

The goal of this project is to analyze the performance of a call center company with multiple branches by exploring relationships between various factors, such as sentiment, response time, call duration, and communication channels. The analysis focuses on identifying any significant factors that may influence call center performance and customer satisfaction.

Specific objectives include:

- **Channel Performance Comparison**: Compare performance across different channels (Call Center, Chatbot, Web, Email).
- **AHT and Total Productive Time Analysis**: Analyze how Average Handle Time and total productive time vary by day and call reasons.
- **Sentiment Correlation**: Explore whether longer or shorter calls tend to correlate with more positive or negative sentiments.
- **Call Duration Distribution**: Determine the distribution of productive time through call reasons for each contact channel.
- **Interaction Duration vs. Channel**: Determine whether there's a relationship between interaction duration and channel.
- **Peak Days Identification**: Identify peak days to optimize staffing and scheduling.

## Value and Application

This project is distinct because it focuses on the specific needs of WFM teams from call data. By analyzing how sentiment and customer satisfaction (CSAT) relate to AHT and SLAs over time across channels of contact, this project provides actionable insights that directly influence operational efficiency and agent performance.

### **How the Data Was Collected** 

The dataset used for this project was sourced from Kaggle, a platform offering a wide variety of open-source datasets. The dataset focuses on call center interactions, providing information such as call sentiment, call duration, customer satisfaction (CSAT), communication channel, and response time category. The fields were chosen to analyze performance metrics relevant to workforce management and contact center efficiency. 

### **How to Run the Project** 

  

#### **Requirements** 

To run and reproduce this project, the following tools are required: 

- **Excel**: Used for initial data cleaning, pivot tables, and visualization. 

- **Power BI**: Used for advanced visualizations, reporting, and dashboard creation. 

- **Python (Optional)**: To further analyze data or automate processes (if needed). 

- **Kaggle account**: To download the dataset. 

  

#### **Steps to Run the Project** 

1. **Data Preparation**: 

   - Download the dataset from Kaggle. [Link to Dataset](https://www.kaggle.com/) 

   - Load the dataset into Excel for cleaning. Remove unnecessary fields like `Customer Name`, `State`, and `City`. 

   - Format the `Timestamp` field and ensure data consistency, such as handling missing `CSAT` values by ignoring them. 

  

2. **Exploratory Data Analysis**: 

   - Open the cleaned Excel file and create pivot tables for metrics like **Average Call Duration**, **Sum of Duration**, and **Sentiment Distribution**. 

   - Use Excel's functions and formulas (e.g., `AVERAGEIF`, `COUNT`) to calculate these metrics. 

  

3. **Power BI Visualizations**: 

   - Load the cleaned data into Power BI. 

   - Create visuals to showcase insights such as the distribution of call durations, customer sentiment across channels, and service level adherence. 

   - Use DAX formulas to calculate metrics such as **Response Time Percentage** and **Total Call Duration in Hours** (examples provided in the README). 


4. **Statistical Analysis**: 

   - Perform Chi-Square and ANOVA tests to check relationships between categorical variables like **Sentiment** and **Channel**, and continuous variables like **Call Duration**. 

   - Interpret the p-values to understand if there are statistically significant relationships. 

Given that the data was collected externally, it may not perfectly reflect real-world conditions specific to our company, but it provides a strong foundation for similar analyses in a real-world setting. 

Key distinctions include:

- **Targeted Analysis for WFM**: Tailored to the needs of WFM, focusing on channel performance and scheduling optimization.
- **Data-Driven Insights**: Utilizes advanced data cleaning, statistical analysis, and visualization techniques to ensure relevant and actionable insights.
- **Versatile Methodology**: Demonstrates methods to determine sentiment distribution by channel of contact, providing a versatile analysis methodology that can be recreated with larger datasets.
- **Practical Application**: The analysis aligns with operational goals, making it useful for real-time decision-making.

## Dataset

The dataset used includes the following fields:

- **ID**: Unique identifier for each interaction.
- **Sentiment**: Customer sentiment (e.g., Positive, Neutral, Negative).
- **Timestamp**: Date of the interaction (without time).
- **C_SAT**: Customer satisfaction score (with some missing values).
- **Reason**: Reason for the customer's contact (e.g., Billing, Technical Support).
- **Channel**: Communication channel used (e.g., Call Center, Chatbot, Web, Email).
- **Call Duration in Minutes**: Length of the call in minutes.
- **Call Center**: The specific call center handling the interaction.
- **Response Time Category**: Classification of response time (Above SLA, Within SLA, Below SLA).

## Data Cleaning and Preparation

The following steps were taken to prepare the data for analysis:

- **Removed Irrelevant Fields**: Excluded fields like `Customer Name`, `State`, and `City` as they were irrelevant to the analysis focus.
- **Handled Duplicates**: Removed duplicate records to ensure data integrity.
- **Formatted Timestamp**: Adjusted the `Timestamp` field using locale settings in Power Query to ensure consistency.
- **Added Helper Columns**:
  - **Weekday**: Extracted the day of the week from the `Timestamp`.
  - **Week Number**: Calculated the week number for time-based analysis.
  - **Call Duration Category**: Categorized calls as 'Below Average', 'Average', or 'Above Average' based on call duration.

## Analysis Plan

### Exploratory Data Analysis (EDA)

- **Descriptive Statistics**: Calculated key metrics such as Average Duration, Average CSAT, Sum of Duration, and Count of ID.
- **Pivot Tables and Charts**: Created pivot tables and charts to show the distribution of these metrics by sentiments, reasons, channels, and response time categories.
- **Volume and Handle Time Analysis**:
  - Analyzed call volumes and handle times across days of the week to identify peak days.
  - Explored the distribution of interaction reasons and their impact on AHT.
- **Sentiment Analysis**:
  - Investigated the relationship between sentiment and call duration.
  - Determined the distribution of sentiments across different channels and call reasons.

### Statistical Analysis

#### Chi-Square Test of Independence

Performed Chi-Square tests to investigate whether certain categorical variables were related:

1. **Sentiment vs. Channel**:
   - **Objective**: To determine if customer sentiment significantly differs across communication channels.
   - **Findings**: P-value ≥ 0.05, indicating no statistically significant relationship between sentiment and channel.

2. **Response Time Category vs. Channel**:
   - **Objective**: To explore if the proportion of calls within SLA differed between communication channels.
   - **Findings**: P-value ≥ 0.05, indicating no statistically significant relationship between response time category and channel.

#### ANOVA Test: Call Duration vs. Channel

- **Objective**: To analyze whether there are significant differences in call durations across different communication channels.
- **Findings**: P-value ≥ 0.05, indicating no statistically significant difference in the average call duration across the various communication channels.

## Power BI Functionalities

Utilized Power BI to create interactive visualizations and dashboards. Examples of DAX formulas used:

- **Total Calls**:

  ```DAX
  Total Calls = COUNT('Call Center (Cleaned)'[ID])
  ```

- **Total Call Duration in Hours**:

  ```DAX
  Total Call Duration (Hrs) = SUM('Call Center (Cleaned)'[Call Duration in Minutes]) / 60
  ```

- **Average Call Duration**:

  ```DAX
  Average Call Duration = AVERAGE('Call Center (Cleaned)'[Call Duration in Minutes])
  ```

- **Response Time Percentage**:

  ```DAX
  Response Time Percentage = 
  VAR WithinSLA = COUNTROWS(FILTER('Call Center (Cleaned)', 'Call Center (Cleaned)'[Response Time Category] = "Within SLA"))
  VAR TotalCalls = COUNTROWS('Call Center (Cleaned)')
  RETURN DIVIDE(WithinSLA, TotalCalls, 0)
  ```

### Visualizations Created

1. **Call Duration Trends**: Line charts visualizing how call duration changes across weekdays.
2. **SLA Adherence by Channel**: Bar charts showing SLA adherence across different communication channels.
3. **AHT by Reason and Sentiment**: Tables displaying the relationship between AHT and call reasons, segmented by sentiment.
4. **Sentiment Distribution**: Pie charts and bar graphs illustrating the distribution of sentiments across channels and reasons.

## Excel Functionalities

- **Pivot Tables**: Created to summarize data and identify trends.
- **Charts**: Used Excel charts to visualize insights, including bar charts, line graphs, and pie charts.
- **Formulas**: Utilized formulas such as `SUMIF`, `AVERAGEIF`, and `COUNTIF` for condition-based calculations.

## Insights and Recommendations

### Insights

1. **Volume and Handle Time Analysis**:
   - Interactions offered increase towards the weekend, peaking on Thursdays and Fridays.
   - The highest number of calls are related to "Billing"; "Payments" have the least.
   - Average handle time ranges between 23 to 25 minutes across all channels, with emails having a slightly higher AHT.
   - No significant difference in call durations across channels (ANOVA test result).

2. **Sentiment Analysis**:
   - A large portion of interactions have negative sentiments across all channels.
   - "Billing" is the interaction reason with the most negative sentiments on all channels.
   - No significant relationship between sentiment and channel (Chi-Square test result).

3. **Correlation of Sentiments and Call Duration**:
   - Interactions with longer durations tend to have negative or very negative sentiments and lower average CSAT scores.
   - Training focused on de-escalation techniques may help improve sentiments and reduce call durations.

### Recommendations

1. **Agent Training**:
   - Schedule training sessions focused on de-escalation techniques to handle negative sentiments.
   - Provide targeted training for agents handling "Billing" inquiries to reduce AHT.

2. **Staffing Adjustments**:
   - Adjust staffing levels during peak days (Thursdays and Fridays) to meet SL targets.
   - Allocate more resources to channels or call reasons with higher volumes of negative sentiments.

3. **Process Improvements**:
   - Streamline processes for call reasons with high AHT to reduce handle times.
   - Explore quick email response strategies for cases that are not typical to reduce AHT in emails.

4. **Sentiment Monitoring**:
   - Implement sentiment analysis tools for real-time monitoring to proactively address customer concerns.

## Limitations

- **Dataset Constraints**: The analysis is based on a specific dataset, which may not fully capture real-world complexities.
- **Missing Values**: Some fields, such as CSAT, contain missing values that were ignored, which may affect the analysis.
- **Generalization**: Insights and recommendations may require adaptation when applied to different organizations or datasets.

## Skills Showcased

1. **Data Cleaning and Preparation**:
   - Removed irrelevant columns and handled missing values.
   - Created helper columns to enhance analysis capabilities.

2. **Exploratory Data Analysis (EDA)**:
   - Used pivot tables and charts in Excel to uncover patterns and trends.
   - Investigated relationships between key performance indicators and various factors.

3. **Statistical Analysis**:
   - Conducted Chi-Square tests to examine relationships between categorical variables.
   - Performed ANOVA tests to compare means across different groups.

4. **Data Visualization**:
   - Developed interactive dashboards and visualizations in Power BI.
   - Utilized Excel charts to present data insights effectively.

5. **Statistical Interpretation**:
   - Interpreted p-values and statistical test results to make data-driven conclusions.

## Future Work

- **Real-time Data Analysis**: Integrate real-time data streams for more dynamic decision-making.
- **Advanced Analytics**: Implement machine learning models to predict interaction volumes and required staffing levels.
- **Expanded Metrics**: Include additional metrics such as agent adherence, schedule efficiency, and first-call resolution.
- **Customer Segmentation**: Analyze performance metrics across different customer segments for targeted strategies.

## Acknowledgements

Special thanks to Dash BPO South Africa for the opportunity to develop and showcase my analytical skills.

## Contact

For questions or collaboration, please reach out:

- **Email**: dante4data@example.com
- **LinkedIn**: [Thando Vilakazi](https://www.linkedin.com/in/thando-vilakazi/)

---
