# ICC-Mens-ODI-Cricket-Players-Analysis-SQL-Project

## Project Overview

**Project Title**: ICC Cricket Players Analysis 

**Level**: Beginner

**Database**: Mens_ICC_ODI_info2

This project focuses on providing an extensive overview of cricket players who have represented their countries under the International Cricket Council (ICC). It aims to capture their career statistics, achievements, milestones, and contributions to the sport.

## Objectives

1.	**Comprehensive Profiles**: Develop detailed profiles of top ICC cricket players, including personal background, cricketing journey, and career highlights.
2.	**Statistical Analysis**: Compile and analyse career statistics such as runs scored, wickets taken, averages, strike rates, and records held.
3.	**Historical Insights**: Highlight the evolution of cricket through the contributions of iconic players across different eras.
4.	**Comparative Insights**: Facilitate comparisons between players across generations using key performance metrics.
5.	**Fan Engagement**: Provide engaging content for cricket enthusiasts, such as trivia, lesser-known facts, and memorable moments.
   
## Project structure

### 1.Database Setup

•	**Database Creation**: The project starts by creating named `Mens_ICC_ODI_info2`.

•	**Table Creation**: A table named `ODI_PLAYERS_INFO2` is created to store the players data. The table structure includes
Columns for Player_ID, Player_Name, Team_Name, Date_Of_Birth,Matches_Played,Runs_Scored,
Wickets,Double_Centuries,Centuries,Fiftys,Best_Score,ODI_Rank and Strike_rate.

```sql
CREATE TABLE ODI_PLAYERS_INFO2(
PLAYER_ID INT IDENTITY,
PLAYER_NAME NVARCHAR(80),
TEAM_NAME NVARCHAR(80),
MATCH_PLAYED INT,
AGE INT,
TOTAL_RUNS INT,
TOTAL_WICKETS INT,
BEST_WICKETS INT,
MAIDEN_OVERS INT,
ECONOMY_RATE DECIMAL(3,2),
STRIKE_RATE DECIMAL(5,2),
CENTURIES INT,
FIFTYS INT,
BEST_SCORE INT,
ODI_RANK INT,
PLAYER_ROLE NVARCHAR(80),
DOUBLE_CENTURIES INT
);
```

 ### 2.Data Exploration
 
•	**Players Record Count**: determine the total number of records in the dataset.

•	**Players count**: Find out how many unique players in the dataset.

•	**Best Score**: Identify best score player name in the dataset.

### pending

### 3.Data Analysis & Findings
The following SQL queries were developed to answer specific players questions:

1. **who make Most double hundrads in ODI format**:
```sql
SELECT PLAYER_NAME,DOUBLE_CENTURIES FROM ODI_PLAYERS_INFO2 
WHERE DOUBLE_CENTURIES > 1;
```

2.	Calculate the runs each player:
```sql
SELECT PLAYER_NAME,TOTAL_RUNS FROM ODI_PLAYERS_INFO2 
ORDER BY TOTAL_RUNS;
```
3.	Find the each player best average of runs in ODIs:
```sql
SELECT PLAYER_NAME,AVG(TOTAL_RUNS) AS  AVERAGE_OF_RUNS_IN_ODI 
FROM ODI_PLAYERS_INFO2
GROUP BY PLAYER_NAME;
```

4.	Identify the player name with highest runs in ODIs
 ```sql
 SELECT  MAX(TOTAL_RUNS)AS HIGHT_RUNS_IN_ODI FROM ODI_PLAYERS_INFO2;

SELECT PLAYER_NAME,MAX(TOTAL_RUNS) FROM ODI_PLAYERS_INFO2
GROUP BY PLAYER_NAME ;
``` 
5.	Show the team with players who have scored double hundrades in ODIs:
```sql
SELECT TEAM_NAME,PLAYER_NAME,DOUBLE_CENTURIES 
FROM ODI_PLAYERS_INFO2
WHERE DOUBLE_CENTURIES > 1;
```   
6.	Retrive the details of players with the highest wickets in ODIs formats:
 ```sql
 SELECT PLAYER_NAME ,MAX(TOTAL_WICKETS) AS HIGHEST_WICKETS_IN_ODI 
FROM ODI_PLAYERS_INFO2
GROUP BY PLAYER_NAME;
SELECT PLAYER_NAME,MAX(TOTAL_WICKETS)
FROM ODI_PLAYERS_INFO2
WHERE PLAYER_ROLE = 'bowler';
``` 
7.	Identify the player with the lowest economy in ODIs matches:
```sql
SELECT PLAYER_NAME,ECONOMY_RATE 
FROM ODI_PLAYERS_INFO2 
WHERE ECONOMY_RATE < 5.00;
```
8.	Identify above 5 wickets taker in ODI matches:
```sql
SELECT PLAYER_NAME,BEST_WICKETS 
FROM ODI_PLAYERS_INFO2 
WHERE BEST_WICKETS > 5;
```
9.	Find the team name and player name with highest centuries in ODIs:
 ```sql
 SELECT TEAM_NAME,PLAYER_NAME,MAX(CENTURIES) AS HIGHEST_CENTURIES
FROM ODI_PLAYERS_INFO2
GROUP BY TEAM_NAME,PLAYER_NAME;
```
10.	Find player name who palyed most matches in ODIs:
 ```sql
  SELECT PLAYER_NAME,MATCH_PLAYED 
FROM ODI_PLAYERS_INFO2 
WHERE MATCH_PLAYED > 150;
```
## Findings Player Performance Analysis:
1.**Top performs in ODI format**: 
•	Highest runs score in ODI format.
•	Most wickets taken in each format.

2.**consistancy metrics**:
•	Players with the highest batting average or strike rate.
•	Bowlers with the best bowling average or economy rates.

3.**Record breakers**:
•	Players with the highest individual runs scores in ODI matches.
•	Who get 5 wickets or above taken wickets in ODI formats.

 ## Reports:
•	**Players summary**: A detailed  report summarizing  total matches,players total runs and cricket performance.

•	**Trend analysis**: insight into runs score across the matches.

•	**Match insights** : Report on best ODI batsmen and unique batsmen runs score per matches.

## Conclusion:
The analysis of ICC cricket players highlights key performances, trends, and contributions across formats like Tests, ODIs, and T20s. It identifies top players, evaluates consistency, and explores team dynamics over time. These insights support data-driven decisions in player selection, strategy, and fan engagement. Expanding the study to include predictive analytics and domestic leagues offers opportunities for deeper exploration.

**How to use**:

1.**clone the Repository**: Clone this project repository from GitHub.

2.**Set Up the Database**: Run the SQL scripts provided in the database_setup.sql file to create and populate the database.

3.**Run the Queries**: Use the SQL queries provided in the analysis_queries.sql file to perform your analysis.

4.**Explore and Modify**:Feel free to modify the queries to explore different aspect of the dataset or answer
Additional business questions.




























































