# umn_fantasy_soccer
Key question to answer: Can we predict the standings (ranking) of a team based on prior player experience?

We started with a dataset of seasons 2007 to 2018 of Major League Soccer (MLS). The dataset included team-specific data, such as overall standings (1st place, 2nd place, etc.), points (55, 53, etc.), wins and losses. It also included player-specific data, such as what team they played on each year. From this data, we debated what insight we could gain from our analysis. We looked at several different options:
    
    1.	Predicting team standings based on a chosen group of players
    2.	Predicting the best group of players based on historical performance (an “All Star” team)
    3.	Predicting number of points a team might score based on past performance

In the end, we decided to predict team standings, or overall ranking for the year, based on our dataset. Our approach was to establish vectors to feed into a One-Hot Encode machine learning model. Each vector consisted of one team per season, and described the makeup of that team (which players are on the team). 

We fed the vectors into the model and discovered that the accuracy was extremely low, meaning we were unable to predict the standing of a team with any accuracy. MORE INPUT HERE

We also used Tableau to analyze our dataset and identify other ways to work with the data. Our visualizations are built on answering two questions:

    1.	How do players move from team-to-team throughout various seasons? We wanted to see the variability of team assignments and how players transition throughout the league. This was a way to visually represent how highly varied our vectors were for our model.

    2.	How do teams tend to compensate their players, and how does that relates to their standing each season? This view allowed us to compare the highest ranked teams across the seasons, and account for the “skewness” of the total compensation distribution. An example of the contrast in the seasons was 2008 where the distribution was fairly equal, the highest paid player earned $433k, and the skew was fairly low (not a drastically steep trend line). Compare this with 2010 where the highest paid player on the highest ranked team earned $6.1M and the skew is much higher.

Our conclusion ... MORE INFO HERE

Tools used:
-	Javascript for website creation
-	Pandas for data structuring
-	One-Hot Encode for modeling the data
-	Tableau for data visualization
-	Keras / Scikit-Learn for machine learning
    - Linear regression
    - Categorical data exploration
    - Classification
    - Deep learning neural network
