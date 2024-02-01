# Employee Presence Analysis

## Overview

This project is designed to analyze and gain insights into employee presence metrics, focusing on key indicators such as overall presence percentage, work-from-home (WFH) percentage, and sick leave (SL) percentage. The analysis includes detailed breakdowns of days-wise presence, days-wise WFH, and days-wise SL percentages. The entire data processing pipeline is implemented using Microsoft Power Query with a significant emphasis on Data Analysis Expressions (DAX) functions.

![image](https://github.com/BalaKrishnan1807/PowerBI_projects/assets/154660199/1b89c965-dc89-47b9-a431-eb89e3772a41)


[Overall Metrics](#Overall-Metrics)

[Days-Wise Metrics](#Days-Wise-Metrics)

## Key Metrics

### 1. Overall Metrics

- **Overall Presence Percentage (%):** The percentage of total working days an employee is present.
- **Work-From-Home Percentage (%):** The percentage of total working days an employee works remotely.
- **Sick Leave Percentage (%):** The percentage of total working days an employee takes sick leave.

  And some other tables and visualization to support the insight needed.

   ![image](https://github.com/BalaKrishnan1807/PowerBI_projects/assets/154660199/da0ea32b-8089-46b9-b4a1-148db857b78a)

### 2. Days-Wise Metrics

- **Days-Wise Presence Percentage (%):** The presence percentage on a day-to-day basis.
- **Days-Wise WFH Percentage (%):** The WFH percentage on a day-to-day basis.
- **Days-Wise SL Percentage (%):** The SL percentage on a day-to-day basis.

![image](https://github.com/BalaKrishnan1807/PowerBI_projects/assets/154660199/68e2a0f3-d398-473d-9a6c-3cdf7eff795d)
![image](https://github.com/BalaKrishnan1807/PowerBI_projects/assets/154660199/f6051622-790a-4525-a382-a59e7350510f)
![image](https://github.com/BalaKrishnan1807/PowerBI_projects/assets/154660199/c8e85abe-0d08-484b-8ff4-6912e217d527)


## Data Processing Details

### 1. Data Cleaning and Transformation

- **Data Source:** Utilized [Attendance Sheet 2022-2023_Masked.xlxs].
- **Power Query:** Employed Power Query for efficient data cleaning and transformation.
- **DAX Functions:** Leveraged a variety of DAX functions for precise calculations and metric derivations.

### 2. Calculations Using DAX Functions

- **Overall Presence Percentage Calculation:**
  ```DAX
  Presence % = DIVIDE([Present Days],[Total Working Days],0)
  ```
- **WFH Percentage:**
   ```DAX
   WFH % = DIVIDE([WFH Days],[Present Days],0)
    ```
- **SL Percentage:**
 ```DAX
 SL % = DIVIDE([SL Days],[Total Working Days],0)
 ```
- **Total Working Days:**
  ```DAX
   Total Working Days = 
   VAR totalworkingdays = COUNT('Final Data'[Value]) 
   VAR nonworkingdays = CALCULATE(COUNT('Final Data'[Value]),'Final Data'[Value] in {"WO","HO"})
   return
   totalworkingdays - nonworkingdays
  ```


And used **SUM()** function to get the number of WFH days and SL days

## Usage

1. Install [Microsoft Power BI](https://powerbi.microsoft.com/).


## Conclusion

In conclusion, the analysis of employee presence metrics reveals distinct patterns, notably higher Sick Leave (SL) percentages on Mondays and increased Work-From-Home (WFH) tendencies on Fridays. The elevated SL on Mondays suggests a potential need for targeted well-being initiatives to address the start-of-the-week absenteeism. Conversely, the higher WFH on Fridays indicates a prevalent desire for flexibility towards the week's end, suggesting the consideration of formalized flexible work policies. Recognizing these patterns provides an opportunity to implement strategic interventions, fostering a healthier work environment, improving employee satisfaction, and potentially boosting overall productivity. Continuous monitoring and employee feedback through surveys will be crucial for refining policies and ensuring adaptability to evolving work patterns and preferences.


## Contributors

- [R.Bala krishnan]



