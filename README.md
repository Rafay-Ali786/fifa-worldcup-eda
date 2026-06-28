⚽ FIFA World Cup EDA (1930–2022)

A complete Exploratory Data Analysis of FIFA World Cup history — covering 92 years of international football across 3 datasets and 3 notebooks. This project explores tournament history, FIFA rankings, and match-level data, with statistical hypothesis testing to validate the host nation advantage.


📁 Datasets Used

DatasetRowsColumnsDescriptionworld_cup.csv229Tournament-level data: host, champion, runner-up, top scorer, attendance per World Cupfifa_ranking_2022-10-06.csv2117FIFA team rankings as of 2022: rank, points, associationmatches_1930_2022.csv96444 → 23 (after cleaning)Match-level data: scores, rounds, teams, cards, penalties, attendance


📓 Notebooks

NotebookDatasetFocusWorld_cup_EDA.ipynbworld_cup.csvTournament history, champions, attendance trendsFifa_ranking_2022_EDA.ipynbfifa_ranking_2022-10-06.csvTeam rankings, points distribution, confederationsfifa_matches_1930_to_2022.ipynbmatches_1930_2022.csvMatch-level EDA, hypothesis testing, key findings


📊 EDA Breakdown

🏆 Notebook 1 — World Cup Tournament History


Basic exploration: shape, info, describe, missing values, duplicates
Total attendance trend by Year (line plot)
Most successful champions by title count
Top 5 World Cups by total attendance
Top 5 highest scoring top scorers in history
Most frequent runner-up teams


🌍 Notebook 2 — FIFA Rankings 2022


Basic exploration: shape, info, describe, missing values, duplicates
Top 10 teams by FIFA points
Teams count by confederation (association)
Distribution of FIFA points across all 211 teams
Correlation heatmap of numerical columns


⚽ Notebook 3 — Match-Level EDA (Main Notebook)

Data Cleaning


Dropped irrelevant columns (44 → 23 columns)
Filled event-based NaN values (cards, penalties, own goals) with 0


Feature Engineering


total_goals — sum of home and away goals per match
winner — accounts for penalty shootout results
goal_difference — absolute margin of victory
decade — extracted from Year for trend analysis



Note: These are EDA-level derived columns, not ML features. Proper feature engineering will be covered in the ML phase.



Univariate Analysis


Distribution of total goals per match
World Cup winners by title count
Top 10 teams by total appearances
Attendance distribution
Goal difference distribution


Bivariate Analysis


Average attendance by Year
Top 5 matches by highest attendance
Home vs Away goals comparison
Total goals per World Cup by year
Average goals by tournament round


Multivariate Analysis


Correlation heatmap of numerical columns
Top 10 highest scoring teams across all World Cups
Win rate by team (top 10)


Hypothesis Testing


Do host nations score significantly more goals than non-host teams?




H0: Host teams do not score more than non-host teams
H1: Host teams score more than non-host teams
Test: Independent samples t-test (one-sided)


Host Team Avg Goals:     2.10
Non-Host Team Avg Goals: 1.38
T-statistic:             4.5125
P-value:                 0.0000

→ Reject H0 — Host teams score significantly more than non-host teams


🏆 Key Findings


Host Nation Advantage is Statistically Proven
Host teams average 2.10 goals per match vs 1.38 for non-host teams. With a p-value of ~0.0000, this is not by chance. Crowd energy, zero travel fatigue, and home familiarity translate directly into goals.
Modern Football is More Defensive
The heatmap reveals a negative correlation between Year and total_goals. The open, high-scoring football of the 1950s (1954: 140 goals in just 26 matches) has given way to tactically disciplined modern systems.
Tournament Expansion Drove the Goal Surge, Not Better Attacking
Total goals jumped permanently after 1998 when the format expanded from 24 to 32 teams. The modern ceiling of ~170 goals per tournament is a result of more matches, not more attacking football.
The Home vs Away Gap Is Partly a Scheduling Bias
Actual host nations score 2.10 goals, but even non-host "home" teams score 1.75 vs away teams' 1.04. FIFA systematically assigns stronger, top-seeded teams to the home slot — making part of this gap a seeding bias, not pure home advantage.
World Cup Success Is Concentrated Among a Few Nations
Brazil, Germany, Argentina, and Italy dominate both appearances and goals scored. Every single World Cup winner has come from either Europe or South America — a historical duopoly in elite football infrastructure that other regions have yet to break.



🛠️ Tech Stack


Python
Pandas, NumPy
Matplotlib, Seaborn
SciPy (hypothesis testing)
