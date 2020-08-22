# Fantasy Soccer
Final project for DATA visualization and analytics certification at University of Minnesota

## Key question to answer
Can we predict the standings (ranking) of a team based on prior player experience?

## Solution
We started with a dataset of seasons 2007 to 2018 of Major League Soccer (MLS). The dataset included team-specific data, such as overall standings (1st place, 2nd place, etc.), points (55, 53, etc.), wins and losses. It also included player-specific data, such as what team they played on each year. From this data, we debated what insight we could gain from our analysis. We looked at several different options:
    
    1.	Predicting team standings based on a chosen group of players
    2.	Predicting the best group of players based on historical performance (an “All Star” team)
    3.	Predicting number of points a team might score based on past performance

In the end, we decided to predict team standings, or overall ranking for the year, based on our dataset. Our approach was to establish vectors to feed into a machine learning model. Each vector consisted of one team per season, and described the makeup of that team (which players are on the team). We encoded all players of MLS using `LabelEncoder` from `SKLearn` and composed the input vectors as sparse vectors of one-hot encoding. Then we fed these sparse vectors into a deep neural network to predict standings.

We fed the vectors into the model and discovered that the accuracy was extremely low, meaning we were unable to predict the standing of a team with any accuracy. We consistently were getting `mean_absolute_error` of about 4.84 on the validation subset. Where `mean_absolute_error` is basically an average of how much our prediction missed the actual standing of a particular team in a particular season. For the reference the standings vary from 1 to 23.

To evaluate the accuracy of our model we ran a baseline. We "predicted" the standings with `Numpy`'s random number generator and calculated the `mean_absolute_error` of this kind of "prediction" and compared it to our 4.84. The random predictor got the `mean_absolute_error` somewhat around 7.0, depending on the randomness of its nature. This indicated a slightly better performance of our deep model than a pure luck.

We also ran a simple multi-variable linear regression model as a baseline. Surprisingly the linear regression performed better than our DNN model. Its `mean_absolute_error` was 4.45 against our 4.84. Not very big difference but our deep learning model was clearly worse than a basic linear regression.

Another approach that we tried was encode the standings too and predict their probabilities. So instead of a single neuron on the output we built a model with 23 output nodes with loss function `categorical_crossentropy`. This model couldn't even learn properly - it's validation loss diverged from the training loss from the very beginning and was growing each `epoch`.

We also used `Tableau` to analyze our dataset and identify other ways to work with the data. Our visualizations are built on answering two questions:

    1.	How do players move from team-to-team throughout various seasons? We wanted to see the variability of team assignments and how players transition throughout the league. This was a way to visually represent how highly varied our vectors were for our model.

    2.	How do teams tend to compensate their players, and how does that relates to their standing each season? This view allowed us to compare the highest ranked teams across the seasons, and account for the “skewness” of the total compensation distribution. An example of the contrast in the seasons was 2008 where the distribution was fairly equal, the highest paid player earned $433k, and the skew was fairly low (not a drastically steep trend line). Compare this with 2010 where the highest paid player on the highest ranked team earned $6.1M and the skew is much higher.

## Our conclusion
Six thousand players playing 11 seasons in twenty or so teams in the past don't give us enough input to predict future. The dataset is too small to account for all the variables in a complex and dynamic system such as Major League Soccer. We definitely need a lot more data to at least see if the model could find any correlations between the input data and the outcome.

## Tools used:
-	Javascript for website creation
-	Pandas and Numpy for data structuring
-	LabelEncoder for shaping the input data
-	Tableau for data visualization
-	Keras / Scikit-Learn for machine learning
    - Linear regression
    - Categorical data exploration
    - Classification
    - Deep neural network

## Authors
- Josh Peterson
- Karim Darbaki
- Mikhail Kyraha
