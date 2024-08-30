# Contact Center Analytics Project

## Overview

This project focuses on analyzing key performance metrics within a contact center, specifically targeting areas crucial for Workforce Management (WFM). Metrics such as Average Handle Time (AHT), service level adherence, and call reasons are analyzed to optimize agent skill routing between chat and inbound queues. The goal is to provide actionable insights for improving service levels and ensuring they are met at each interval of the day.

## Table of Contents

- [Project Overview](#overview)
- [Objectives](#objectives)
- [Value and Distinction](#value-and-distinction)
- [Data Generation](#data-generation)
- [Installation](#installation)
- [Usage](#usage)
- [Analysis Plan](#analysis-plan)
- [Visualizations and Reporting](#visualizations-and-reporting)
- [Insights and Recommendations](#insights-and-recommendations)
- [Limitations](#limitations)
- [Conclusion](#conclusion)
- [Future Work](#future-work)
- [Acknowledgements](#acknowledgements)
- [Contact](#contact)

## Objectives

- Analyze how AHT relates to call-in reasons or case issues over time.
- Make data-supported decisions in agent skill routing between chat and inbound queues.
- Gather insights for service level (SL) improvements to ensure targets are met at each interval of the day.
- Develop interactive visualizations and reports using Power BI to present the findings.

## Value and Distinction

This project is distinct because it focuses on the specific needs of WFM teams rather than general contact center metrics. By analyzing how sentiment and customer satisfaction (CSAT) impact AHT and SLAs over time, this project provides actionable insights that directly influence operational efficiency and agent performance.

Key distinctions include:

- **Targeted Analysis for WFM:** Tailored to the needs of WFM, focusing on agent performance and scheduling optimization.
- **Data-Driven Insights:** Utilizes advanced data cleaning, analysis, and visualization techniques to ensure relevant and actionable insights.
- **Practical Application:** The analysis aligns with operational goals, making it useful for real-time decision-making.

## Data Generation

The project involves generating synthetic data to simulate contact center operations. The following tables are created to support the analysis:

1. **Interactions Table:** Contains details about each interaction, including AHT, call reason, and channel.
2. **Queue Metrics Table:** Includes data on service levels, wait times, and abandonment rates.
3. **Service Level Metrics Table:** Tracks SL adherence over time.

### Data Generation Script

A custom script is used to generate the synthetic data, simulating realistic contact center operations. [Link to script](path/to/script).

## Installation

To set up this project locally, follow these steps:

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/Dante4Data/contact-center-analytics.git
   cd contact-center-analytics
   ```

2. **Install Dependencies:**

   If the project has any dependencies, such as Python packages, they will be listed in a `requirements.txt` file. Install them using:

   ```bash
   pip install -r requirements.txt
   ```

3. **Set Up the Environment:**

   Follow any additional instructions provided for environment setup.

## Usage

To use the tools and scripts included in this project:

1. **Data Import:**
   - Import the dataset into your preferred analysis tool (e.g., Excel, Power BI).

2. **Running the Analysis:**
   - Follow the instructions provided in the analysis plan to execute the analysis scripts.

3. **Viewing the Results:**
   - The results will be visualized using Power BI dashboards and Excel charts.

## Analysis Plan

### AHT Analysis

- **Grouping and Visualization:** Group AHT by call reason and visualize changes over time (monthly, daily, hourly).
- **Comparison Across Interaction Types:** Compare AHT for different interaction types (e.g., Chat, Inbound-Member, Inbound-All).

### Service Level Analysis

- **Performance Assessment:** Assess service level performance over time and identify intervals with low adherence.
- **Improvement Suggestions:** Based on the findings, suggest targeted improvements.

## Visualizations and Reporting

Using Power BI, the following visualizations are created:

- **AHT Trends:** Time series graphs showing AHT by call reason, interaction type, and agent.
- **Service Level Performance:** Dashboards showing service level adherence and areas for improvement.

### Power BI Functionalities

Examples of DAX formulas used:

- **Total Calls:**
    ```DAX
    Total Calls = COUNT('Call Center (Cleaned)'[id])
    ```

- **Total Call Duration in Hrs:**
    ```DAX
    Total Call Duration (Hrs) = [Total Call Duration (Min)]/60
    ```

- **Response Time Percentage:**
    ```DAX
    Response Time Percentage = 
    VAR WithinSLA = SUMX(
        'Call Center (Cleaned)',
        IF([response_time] = "Within SLA", 1, 0)
    )
    VAR AboveSLA = SUMX(
        'Call Center (Cleaned)',
        IF([response_time] = "Above SLA", 1, 0)
    )
    VAR TotalCalls = COUNTROWS('Call Center (Cleaned)')
    RETURN 
        DIVIDE(
            WithinSLA + AboveSLA,
            TotalCalls
        )
    ```

### Excel Functionalities

- **Pivot Tables:** Create pivot tables to summarize data and identify trends.
- **Charts:** Use Excel charts to visualize insights.
- **Formulas:** Utilize formulas such as `SUMIF` and `AVERAGEIF` for condition-based calculations.

## Insights and Recommendations

### Insights

- **AHT by Call Reason:** Identify high AHT call reasons and target them for process improvements.
- **Service Level Performance:** Pinpoint intervals with low adherence and investigate underlying causes.
- **Queue Metrics:** Analyze high wait times and abandonment rates to optimize staffing and improve customer satisfaction.

### Recommendations

- **Agent Training:** Provide targeted training for agents with high AHT or low performance metrics.
- **Staffing Adjustments:** Adjust staffing levels during peak intervals to meet SL targets.
- **Process Improvements:** Streamline processes for call reasons with high AHT to reduce handle times.

## Limitations

- **Synthetic Data:** Based on synthetic data, which may not fully capture real-world complexities.
- **Tool Access:** Limited access to advanced analytics tools may restrict the depth of analysis.
- **Generalization:** Insights and recommendations may require adaptation for real-world scenarios.

## Conclusion

This project provides a comprehensive analysis of contact center performance, focusing on AHT, interaction duration, and service level adherence. The insights gained will help optimize agent skill routing and improve service levels, ensuring customer satisfaction.

## Future Work

- **Real-time Data Analysis:** Integrate real-time data analysis for more dynamic decision-making.
- **Advanced Analytics:** Implement machine learning models to predict interaction volumes and required staffing levels.
- **Expanded Metrics:** Include additional metrics such as agent adherence and schedule efficiency.

## Acknowledgements

Special thanks to Dash BPO South Africa for the opportunity to develop and showcase my analytical skills.

## Contact

For questions or collaboration, please reach out:

- **Email:** dante4data@example.com
- **LinkedIn:** [Thando Vilakazi](https://www.linkedin.com/in/thando-vilakazi/)
```

### Key Enhancements:
1. **Structured Layout:** Added a clear Table of Contents to improve navigation.
2. **Value and Distinction:** Highlighted why your project is unique and valuable for WFM teams.
3. **Installation & Usage:** Provided clear steps for setting up and using the project.
4. **Future Work:** Included a section for potential future improvements.
5. **Contact Information:** Added a contact section to encourage collaboration and feedback.

You can further tailor this template as your project evolves. If you have any more sections to refine or additional content to add, feel free to ask!
