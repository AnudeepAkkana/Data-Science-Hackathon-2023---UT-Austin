# Energy A.I. Hackathon 2023

## Hosts: [Prof. Michael Pyrcz](https://twitter.com/GeostatsGuy) and [Prof. John T. Foster](https://twitter.com/johntfoster)

### Architects: [Elnara Rustamzade](https://www.linkedin.com/in/elnara-rustamzade-779396162/) and [Ruoyu Wang](https://www.linkedin.com/in/ruoyu-wang1)

### Home Department Chair and Hackathon Supporter: [Prof. Jon Olson](https://twitter.com/ProfJEOlson)

### Sponsors: [ComboCurve Inc.](https://www.combocurve.com/), [Pioneer Oil Company Inc.](https://pioneeroil.net/), [Chevron](https://www.chevron.com) and [Baker Hughes](https://www.bakerhughes.com/)

### Coordination and Student Engagement: Gabby Banales, Trevor Oxley, Samantha Rabinowitz and Stacia Miller

___

### Energy A.I. Hackathon 2023 Problem Description 

**Goal**: Develop a data analytics and machine learning workflow in Python to:

* prediction / classification **"fail" or "not fail" within 30 days** for 40 artificial lift Electronic Submersible Pumps
 
#### Background

In order to prevent the production loss caused by Electronic Submersible Pump (ESP) failures in artificial lift operations, we challenge the Energy A.I. Hackathon 2023 teams of The University of Texas at Austin to build a data-driven model to detect when an ESP is within 30 days of failure.

This will require:

* data analysis and evaluation of multiple data sources and a variety of features
* feature engineering including feature selection, feature transformations and feature imputation to address missing data
* integration of domain expertise at every step
* selection, training and tuning robust machine learning prediction models  

Your model will be applied to support preventative maintenance by identifying ESPs within 30 days of failure for inspection and repair.  
___

### Available Data Files Inventory

You have the following available data:

#### Well / ESP Data

* **[wellData.csv](wellData.csv)** - data on 166 unique ESPs installed on 146 wells. All ESPs not in the [solution.csv](solution.csv) are assumed to have failed.

The features include:

* **AL_Bottom_Depth (ft)** - the depth at which an ESP is positioned in the well
* **ESP_Pump_Stages** - the number of impellers that impart a pressure rise to the fluid
* **DLS_Critical (degree/100ft)** - critical dogleg severity; until a dog-leg reaches this threshold value, no drill stem fatigue damage occurs
* **ESP_Motor_Frequency_Rating (Hz)** - rated frequency of the motor
* **ESP_Motor_Current_Rating (A)** - rated current of the motor
* **ESP_Motor_Voltage_Rating (V)** - rated voltage of the motor
* **DLS_at_Set_Depth (degree/100ft)** - dogleg severity at the depth of the ESP
* **Failure_Type** -  ESP failure type; can be "electrical", "pump", or "tubing"
* **Failure_Type_Detail** - detailed ESP failure type; can be "motor", "penetrator", "stage", etc
* **Status** -  ESP status; can be either "failed", "active", or missing. Missing status indicates that an ESP is a test case

#### Daily Data

* **[dailyData.csv](dailyData.csv)** - dynamic data collected daily. For each well, there will be a row of data for each day that the ESP is installed.

The features include:

* **OIL (bbl)** - oil production 
* **GAS (SCF)** - gas production
* **WATER (bbl)** - water production
* **DOWN_TIME_HOURS** - the amount of time the well was shut for per day
* **Oil_Intake (bbl)** - the amount of oil that enters the system
* **Water_Intake (bbl)** - the amount of water that enters the system
* **Gas_Intake (SCF)** - the amount of gas that enters the system
* **Liquid_Intake (bbl)** - the amount of liquid that enters the system
* **Gas_Saturation_at_Intake** - ratio of the amount of gas entering the system to the total volume
* **Gas_Saturation_at_Discharge** - ratio of the amount of gas leaving the system to the total volume
* **Gas_Separator_Efficiency** - ratio of the reduced volume of free gas to the volume before entering the separator
* **Pump_Delta_Pressure (psi)** - the difference between discharge and intake pressure
* **Power_Ratio** - ratio of pump power to drive power
* **Power_Difference (psi)** - the difference between drive and pump power

#### Problem Set

* **[solution.csv](solution.csv)** - a list of the ESPs that each group must predict if they will fail in 30 days. Note, these ESPs in the daily data have not failed yet.

The features include:

* **Well_ID** - anonymized, unique well indicator
* **AL_Key** - artificial lift key, unique index ESP, e.g., ESP_1 1st ESP in well, ESP_2 2nd ESP in well
* **Fail in 30 days** - hackathon solution to be entered by the team, 1 = WILL fail in 30 days, 0 = WILL NOT fail in 30 days 

Comments: 

* all the well names are anonymized (replaced with simple indices).
* NaN in the file indicate missing data.
* the source of the data is confidential. Do not attempt to determine the source of the data.

___

### Required Hackathon Submissions

By January 22 at 12:00 noon each team must submit:

* **Solution Table** - a .csv file with your predictions for the **test cases** using the template given in [solution.csv](solution.csv) in this directory.

    * the file must be named `solution.csv` with final values in a commit and then pushed to Github for automated scoring.


* **Python Workflow and Associated Files** - committed to this repository with the workflow as a Jupyter Notebook `.ipynb` file along with all data files required to reproduce your team's solutions. The submitted workflow Jupyter Notebook should follow the format of the provided template [Hackathon_ProjectTemplate](https://github.com/PGEHackathon/resources/blob/main/Hackathon_ProjectTemplate.ipynb) for enhanced workflow communication and code readibility.

    * the file must be named `xxxx.ipynb` and pushed to GitHub for review and scoring (for code readability) by the hackathon architects, where **xxxx** is your team name.


* **Presentation** - a PowerPoint slide deck .PPTX file for your team's final presentation to our judges. The submitted presentation should follow the format of the provided example presentation [Hackathon_PresentationTemplate](https://github.com/PGEHackathon/resources/blob/master/Hackathon_PresentationTemplate.pptx).

    * the file must be named `xxxx.pptx` and pushed to GitHub for review by the judges, where **xxxx** is your team name.

The Workflow, and Presentation templates are in the [PGEHackathon/resources](https://github.com/PGEHackathon/resources) repository. Use the [solution.csv](solution.csv) file (in this directory) to record your solution.
