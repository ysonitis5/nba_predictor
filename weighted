import pandas as pd
from sklearn.linear_model import LinearRegression
from sklearn.model_selection import train_test_split
from sklearn.metrics import mean_absolute_error
import numpy as np
import points as pts
import warnings

# Ignore the warning about invalid feature names
warnings.filterwarnings("ignore", category=UserWarning, module="sklearn")

# Load the data
df_home = pd.read_csv('home.csv', encoding='latin1')
df_away = pd.read_csv('away.csv', encoding='latin1')

# print(df_home.columns)
# Concatenate the two DataFrames into a single DataFrame
df = pd.concat([df_home, df_away])
# Find rows that contain infinite values
mask = df.isin([np.inf, -np.inf]).any(axis=1)

# Remove rows that contain infinite values
df = df[~mask]

# Find rows that contain missing values
mask = df.isnull().any(axis=1)

# Remove rows that contain missing values
df = df[~mask]

# Select the features and target
X = df[['eFG%', 'FTA', 'TOV%', 'OREB%',
       'OppeFG%', 'OFTA', 'OppTOV%', 'OppOREB%', 'OffRtg', 'DefRtg', 'PACE']]
y = df['Winning Percentage']


# Train the model
model = LinearRegression()
model.fit(X, y)


team_a = 'Cleveland Cavaliers'
team_h = 'Portland Trail Blazers'


h_points = pts.predict_home_points(team_h)
a_points = pts.predict_away_points(team_a)

def predict_game(away_team, home_team, h_points, a_points):
    # Extract the stats for the home team and the away team
    home_stats = df_home[df_home['Team'] == home_team]
    away_stats = df_away[df_away['Team'] == away_team]

    # Select the features for both teams
    X_home = home_stats[['eFG%', 'FTA', 'TOV%', 'OREB%',
       'OppeFG%', 'OFTA', 'OppTOV%', 'OppOREB%', 'OffRtg', 'DefRtg', 'PACE']]
    X_away = away_stats[['eFG%', 'FTA', 'TOV%', 'OREB%',
       'OppeFG%', 'OFTA', 'OppTOV%', 'OppOREB%', 'OffRtg', 'DefRtg', 'PACE']]

    # Use the model to make predictions for both teams
    home_prediction = model.predict(X_home)
    away_prediction = model.predict(X_away)

    # print(home_prediction, away_prediction)

    # Calculate the predicted margin of victory
    predicted_margin_of_victory = home_prediction - away_prediction

    point_spread_home = (home_prediction * h_points) - (away_prediction * a_points)
    point_spread_away = (away_prediction * a_points) - (home_prediction * h_points)




    # Print the predicted margin of victory
    # print(f"Predicted margins of victory: home: {point_spread_home} points ; away: {point_spread_away} points")

    # Compare the predictions to determine which team is more likely to win
    if home_prediction > away_prediction:

        return f"The {home_team} are more likely to win. By {point_spread_home}."
    else:

        return f"The {away_team} are more likely to win. By {point_spread_away}."


result = predict_game(team_a, team_h, h_points, a_points)
print(result) # The Miami Heat are more likely to win.

