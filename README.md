# Clustering-and-Classifying-NBA-Player-Roles
Objective: Investigate whether physical and demographic profiles (Height, Weight, Age, Position) can predict a player's role on the court.
Approach: Instead of using subjective labels, we let the data determine natural player groupings based on actual performance stats.

## Data Collection & Preprocessing:
### 1. Data Source:
#### Official NBA Stats (2024-25 Season).
#### Type: Real-world player statistics.
#### Scale: 659 raw entries → 550 unique players after cleaning.

### 2. Key Preprocessing Steps:
#### *Unit Standardization*: Converted Height to numerical metric units(cm).
#### *Handling Traded Players*:
**Problem: Players traded mid-season appear multiple times.**
**Solution: Sorted by Games Played (GP) and kept only the record with the most games to ensure statistical significance.**
#### Dara Quality: Remove rows with missing values

## Stage 1: K-Mean Clustering:
#### Features selected: 
#### Points Per Game (PTS) → Scoring Ability
#### Rebounds Per Game (REB) → Interior/Defense Presence
#### Assists Per Game (AST) → Playmaking Ability
#### These variables represent the core dimensions of basketball impact.

## Stage 2: Decision Tree:
#### Features used: 'Height', 'Weight', 'Age', 'Pos_code'.

## Stage 3: Random Forest:
### Key takeaways: 
#### Weight is the most important feature
#### Age and Height also strongly contribute to the model 
#### Pos_code plays a smaller role

## Stage 4: KNN:
### Main Question: Can simple traits like height, weight, age, position, and team help us predict a player’s data-defined role?

#### K = 3 gave the best performance for our model.
#### Overall accuracy ≈ 36% → moderate but not strong
#### Players with similar builds can still have very different roles.
#### Confirms that body profile alone cannot define a player type.

## Model Conclusion:
### KNN Accuracy：           0.35757575757575756
### Decision Tree Accuracy：  0.42424242424242425
### Random Forest Accuracy：  0.44242424242424244

#### Random Forest performed the best overall, showing more stable predictions
#### The decision tree did slightly worse but was still better than KNN
#### KNN struggled the most, meaning physical traits alone are not strong predictors
#### All models show limited accuracy, confirming that player roles cannot be determined only by body profile

## Project outcomes:
#### Basic physical traits (height, weight, age, position, team) do not fully define a player’s role
#### Players with similar builds can develop completely different playstyles
#### Physical data gives early hints, but skills, coaching, and opportunity shape real success
#### Shows the uncertainty in predicting roles based only on appearance
#### Highlights why teams must rely on scouting, analytics, and player development




