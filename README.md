# Project-Analysis

## Business Request & User Stories
The business request for this project was created by the user himself. By deciding on a business to analyze (exercise data) the following user story was derived.



## Data Collection & Table Structures
The necessary data were collected and structured in Excel files. The exercise data was organized as a fact table and date & activity were organized as dimension tables for filtering data.



A - FACT_ Exercise :

Exercise data were recorded every single date and the focus was on amount of steps. The date column is used to connect to the date dimension and Activity_FK is used to connect to the activity dimension.

![fact](https://user-images.githubusercontent.com/55878755/219371890-49ca639f-0245-4554-b04e-8b4a526922f6.png)

Following steps were done in Power BI to transform this table to be ready for analysis purposes:

  1-Promoted row so that the data so that the first row was used as headers.
  2-Removed unnecessary columns.
  3-Changed column to have the correct type (date, numbers etc.) for later use in calculations.

![power query](https://user-images.githubusercontent.com/55878755/219372437-152a8988-ff33-4bc2-b61e-6837950ec82b.png)


B - DIM_Activity :

DIM_Activity describes two different types of activities: Walking and running. On some days walking was chosen as a preferred activity time, and other days running were performed. Some minor data issues in this table was later cleaned up and corrected.

![dim 1](https://user-images.githubusercontent.com/55878755/219372764-54f89977-b2c4-4dac-8464-a34c10cb84f8.png)

Following steps were done in Power BI to transform this table to be ready for analysis purposes:

![power query2](https://user-images.githubusercontent.com/55878755/219375823-845418ba-49a0-42b1-a575-5ed59c846764.png)

  1-Promoted row so that the data so that the first row was used.
  2-Renamed necessary columns to give better business friendly names.
  3-Capitalized each for in the description column for improved data quality.


C- DIM_Date :

The DIM_Date dimension is based on a simple table with dates, where date was used to derive several new fields which would be used in the exercise analysis dashboard:

Promoted row so that the data so that the first row was used.
Changed the column to DateType
Inserted several new columns based on the date.

![power query3](https://user-images.githubusercontent.com/55878755/219376443-73e86826-1461-48c8-94ee-1f396e97c01a.png)

## Data Model
Below is a screenshot of the data model after cleansed and prepared tables were read into Power BI.

We can see that the FACT table is connected to two dimension tables with the correct relationship established (1 to *) between dimension and fact tables.

![data model](https://user-images.githubusercontent.com/55878755/219376713-dd3aa487-53bb-4e78-bdcb-4953f1ae16b0.png)


## Calculations : DAX
The following calculations were created in the Power BI reports using DAX (Data Analysis Expressions). To lessen the extent of coding, the re-use of measures (measure branching) was emphasized:

Average Steps – This is a simple AVERAGE function around the Steps column:

![d1](https://user-images.githubusercontent.com/55878755/219378700-b9c80f75-809d-4d52-bbb7-6593fcefcf2e.png)

Total Steps – This is a simple SUM function around the Steps column:

![d2](https://user-images.githubusercontent.com/55878755/219378771-9318e2a2-2d54-4113-a02c-21062b4baea5.png)

Steps (Running) – This is a calculation to isolate the Total Steps measure by filtering it by the “Running Activity”:

![d3](https://user-images.githubusercontent.com/55878755/219378837-5945bc3d-a958-49ce-b144-6fcf888ae611.png)

Steps (Walking) – This is a calculation to isolate the Total Steps measure by filtering it by the “Walking Activity”:

![d4](https://user-images.githubusercontent.com/55878755/219378825-ad34f794-aa52-4a86-a072-43a3cd34f0bd.png)

Running % of Total – Here we are using two measures from before to find the % of steps that were done by running:

![d5](https://user-images.githubusercontent.com/55878755/219378828-e6df4a69-2d80-432d-aab3-3d3a41835a8e.png)

Walking % of Total – Here we are using two measures from before to find the % of steps that were done by walking:

![d6](https://user-images.githubusercontent.com/55878755/219378832-27a696c5-0f61-44d2-b89e-5658391ff3e9.png)

Total Steps (Cumulative) – Here we are re-using the Total Steps measure and using different functions to cumulatively calculate the total steps:

![d7](https://user-images.githubusercontent.com/55878755/219378833-dc22be9d-2f7b-472f-a20d-2284ddfd2ef1.png)


Week Over Week % Change Steps – Here we are using the Total Steps measure and using different functions, with variables, to calculate the Week over Week % Change of Steps:

![d8](https://user-images.githubusercontent.com/55878755/219378835-4c290cd8-1ef8-4d44-81a4-2c45f5111e05.png)


## Analysis Dashboard
The finish report consists of two different dashboards. One is more of a basic version, while the second version contains more advanced visualizations. To enable these visualizations the calculation language DAX (Data Analysis Expressions) were used.
