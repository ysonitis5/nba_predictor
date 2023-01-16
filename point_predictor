import pandas as pd
from sklearn.linear_model import LinearRegression
import warnings

# Ignore the warning about invalid feature names
warnings.filterwarnings("ignore", category=UserWarning, module="sklearn")

# Load the data from the score.csv file
df_score_home = pd.read_csv('score_home.csv')
df_score_away = pd.read_csv('score_away.csv')

# Select the features that we want to use to predict the number of points
X = df_score_home[['FGM', '3PointsMade', 'FTM']]

# Select the target variable (the number of points)
y = df_score_home['PTS']

# Create a Linear Regression model
model = LinearRegression()

# Fit the model to the training data
model.fit(X, y)

# Use the model to predict the number of points for a given set of feature values
def predict_points(fgm, three_points_made, ftm):
    x = [[fgm, three_points_made, ftm]]
    return model.predict(x)[0]


def predict_home_points(team_name):
    team_stats = df_score_home[df_score_home['Team'] == team_name]

    if team_stats.empty:
        return f'{team_name} not found in the data.'

    PTS = team_stats.loc[team_stats.index[0], 'PTS']
    FGM = team_stats.loc[team_stats.index[0], 'FGM']
    ThreePointsMade = team_stats.loc[team_stats.index[0], '3PointsMade']
    FTM = team_stats.loc[team_stats.index[0], 'FTM']

    predicted_points = predict_points(FGM, ThreePointsMade, FTM)

    return predicted_points

def predict_away_points(team_name):
    team_stats = df_score_away[df_score_away['Team'] == team_name]

    if team_stats.empty:
        return f'{team_name} not found in the data.'

    PTS = team_stats.loc[team_stats.index[0], 'PTS']
    FGM = team_stats.loc[team_stats.index[0], 'FGM']
    ThreePointsMade = team_stats.loc[team_stats.index[0], '3PointsMade']
    FTM = team_stats.loc[team_stats.index[0], 'FTM']

    predicted_points = predict_points(FGM, ThreePointsMade, FTM)

    return predicted_points

team_a = 'Cleveland Cavaliers'
team_h = 'Portland Trail Blazers'

home = predict_home_points(team_h)
away = predict_away_points(team_a)

total = home + away


print(f'Total: {total}')
print(f'{team_a}: {away}')
print(f'{team_h}: {home}')
