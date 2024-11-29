# ICC Men's T20 Cricket World Cup 2022 - Data Analytics

## Table of Contents:
- [Problem Statement](#problem-statement)
- [Data Source](#data-source)
- [Data Collection](#data-collection)
- [Data Transformation](#data-transformation)
- [Data Modelling](#data-modelling)
- [Data Analysis Expression (DAX)](#data-analysis-expression-dax)
- [Reports](#reports)
- [Tools, Software, and Libraries](#tools-software-and-libraries)
- [References](#references)

## Problem Statement
This project develops a **Power BI Dashboard** that provides insights into the performance of players in the **ICC Men’s T20 World Cup 2022**. The dashboard enables users to review individual performances and select the **Best 11 Players** of the tournament, based on key metrics and predefined performance criteria.

![Dashboard Overview](Images/Dashboard%20Overview.png)
*Screenshot 1: Overview of the Power BI Dashboard showing player analysis.*

## Data Source
The data for this project was gathered from multiple sources:
- **Match and Tournament Information**: [ESPN CricInfo](https://www.espncricinfo.com/)
- **Player Performance Data**: Collected via **BrightData** (formerly Luminati)

## Data Collection
Data was collected through **web scraping** using the **Beautiful Soup** Python library. The collected data was stored in **JSON** format and later converted into **CSV files** using **Jupyter Notebook** for further analysis in **Power BI**.

## Data Transformation
The raw data underwent extensive cleaning and transformation with the **Pandas** library to ensure quality and consistency:
- Player name corrections
- Handling missing values
- Linking match IDs

After transformation, the data was prepared using the **Power Query Editor** in Power BI for easy integration into the dashboard.

## Data Modelling
The data was connected based on primary keys like **Team ID** and **Match ID**. A variety of **measures**, **calculated columns**, and **parameters** were created using **DAX** to enable detailed analysis and insights.

## Data Analysis Expression (DAX)
Key DAX measures used in the project include:

- **Total Runs**: `SUM(t20_batting_summary[runs])`
- **Batting Average**: `DIVIDE([Total Runs], [Total Innings Dismissed], 0)`
- **Strike Rate**: `DIVIDE([Total Runs], [Total Balls Faced], 0) * 100`
- **Economy Rate**: `DIVIDE([Runs Conceded], ([Balls Bowled] / 6), 0)`
- **Bowling Average**: `DIVIDE([Runs Conceded], [Wickets], 0)`
- **Dot Ball Percentage**: `DIVIDE(SUM(t20_bowling_summary[zeros]), SUM(t20_bowling_summary[balls]), 0)`

Other measures such as **Boundary Percentage**, **Batting Position**, and **Player Selection** enable dynamic filtering and more engaging visualizations.

## Reports
The dashboard includes the following key reports to visualize player performances and assist in team selection:

- **Player Analysis**
- **Openers**
- **Middle Order**
- **Finishers**
- **All-rounders**
- **Specialist Fast Bowlers**
- **Final Best 11 Players**

![Player Analysis Report](images/Player%20Analysis%20Report.png)
*Screenshot 2: Player Analysis Report showing top-performing players.*

Each report offers comparative views to help users analyze performance metrics for effective player selection.

## Tools, Software, and Libraries
This project was built using the following technologies:

- **Jupyter Notebook** - For data preprocessing
- **Python** - For web scraping and data manipulation
- **Pandas** - For data transformation
- **Beautiful Soup** - For web scraping
- **Power BI** - For data visualization
- **Power Query Editor** - For data transformation in Power BI
- **Anaconda** - For managing Python environment

## References
- [CodeBasics - Web Scraping and Data Science Courses](https://codebasics.io/courses)
- [Official ICC T20 World Cup 2022 Website](https://2022.t20worldcup.com/)
- [ESPN CricInfo - ICC Men’s T20 World Cup 2022 Stats](https://stats.espncricinfo.com/ci/engine/records/team/match_results.html?id=14450;type=tournament)
- [Match Scorecard - Namibia vs Sri Lanka](https://www.espncricinfo.com/series/icc-men-s-t20-world-cup-2022-23-1298134/namibia-vs-sri-lanka-1st-match-first-round-group-a-1298135/full-scorecard)
- [BrightData (formerly Luminati) - Data Collection Tools](https://brightdata.com/)

![Final Best 11 Report](Images/Final%20Best%2011%20Report.png) 
*Screenshot 3: Final Best 11 Players report with top-performing players selected.*
