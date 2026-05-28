How NBA Player Archetypes Predict Career Longevity

Overview
Basketball was actually what got me into statistics in the first place. I was the statistician for my high schools team. This project is a bit of a homecoming. Using NBA player data spanning multiple decades, I wanted to explore whether players naturally fall into distinct archetypes based on their performance stats, and whether those archetypes can tell us anything meaningful about how long a player's career lasts.

The Question
Do NBA players cluster into meaningful archetypes based on their stats, and can we use those archetypes to predict career longevity?

Data Source
NBA Players dataset from Kaggle, containing season-by-season performance data for 2,551 unique players across multiple decades. Dataset includes points, rebounds, assists, usage rate, true shooting percentage, and more. https://www.kaggle.com/datasets/justinas/nba-players-data/data

Methodology
Since the raw data had one row per player per season, I first collapsed it down to one row per player by averaging their stats across their career. I then used K-Means clustering to group players into archetypes based on their performance profiles. To determine the number of clusters I used the elbow method, which plots how much variance is explained as you add more clusters and looks for the point of diminishing returns. Based on the results and basketball intuition I settled on 5 clusters. After naming the archetypes I ran a linear regression using archetype as the predictor and seasons played as the outcome variable to quantify how much each archetype predicts career longevity.

Player Archetypes
The clustering identified 5 distinct player types:

Playmakers — primary ball handlers with high assists and usage
Primary Bigs — high scoring, high rebounding frontcourt players
Wing Role Players — versatile but moderate contributors across the board
Backup Bigs — physical presence without significant offensive output
Fringe Players — minimal contributions across all categories

Key Findings

Playmakers average 9.03 seasons while Primary Bigs average 8.79, both roughly twice the career length of role players.
Wing Role Players and Backup Bigs average around 3.9 seasons each, suggesting that generic role players are largely interchangeable and replaceable regardless of position.
Fringe Players average just 1.35 seasons.
Archetype alone explains about 30% of the variation in career length (R-squared = 0.298), which is meaningful given how many other factors influence a player's career.
The central finding is that elite specialization in any role predicts career survival. It matters less whether you score or rebound, and more whether you do something at an elite level.

Tools Used
Python, Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn, Jupyter Notebook
