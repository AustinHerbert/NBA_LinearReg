# NBA : Why Isn't My Team making the Playoffs?
###### * Additional Model Results are added at the bottom 

### *Model explained ~ 94% of actual wins per team with a 3-win standard deviation compared to 7.5 with raw data!*

## Wins to Make Playoffs Based on Past 32 NBA Season 
- The avg team wins ~49 games
- 50% of Playoff teams fall inbetween 42 & 56 wins
![win_boxplot](https://user-images.githubusercontent.com/64975026/84214634-8feae980-aa89-11ea-9368-b1dd59a550e7.png)

Teams should strive for winning 56 games or more in a season to statistically rely on making the Playoffs. Teams that started off slow, can infer that if 42 games is within striking distance, they still have a decent statistical chance of making the Playoffs.

# Exploratory Data Analysis: Determine How to Get Wins 
## New Features
- 2pt % = make/attempts
- 3pt% = make/attempts
- FT % = make/attempts
- RB Ratio = offensive/defensive
- Assist to PTS = assits/pts
- TO diff = (blk + stl) - TO
- Pt diff = pts - opp pts


![Scatter](https://user-images.githubusercontent.com/64975026/84214633-8eb9bc80-aa89-11ea-842f-8f2398f64c9d.png)


# Conclusions:

### Interpreting the coefficients:
#### *Remember these features have very different units*
        - Example: Increasing 1 unit of shooting % is much harder than scoring one more point.

- Holding all other features fixed, a 1 unit increase in **2P%** is associated with an **increase of ~8.4% of a win**.
- Holding all other features fixed, a 1 unit increase in **AST%** is associated with an **increase of ~12% of a win**.
- Holding all other features fixed, a 1 unit increase in **PTS_DIFF** is associated with an **increase of ~3% of a win**.

##### *ONE Win could be the difference between 2nd season and going home early!*

## New Features Linear Regression Model
![lm](https://user-images.githubusercontent.com/64975026/84214631-8eb9bc80-aa89-11ea-8e1b-276368c4c858.png)
# What can Teams Take Away from this Anaysis?

#### *Convert 2PT Atempts efficiently*
    - This is obvious, but if team brought up a shot chart they could dive deeper into this feature that has known
    statistical relevance. Ananlze past games to eliminate low individual 2PT shots.
#### *Assist to Total Points Matters*
    - Typically teams want a superstar, but if that Free Agent is known to have low assists, might want to head 
    another direction. Again, deeper dive, I would look to see the assist totals from prior team based on if said 
    player was on the floor or off the floor.
#### *Outscoring by Wide Margin*
    - This is the most obvious, if you score more points than the other team by a wide margin that means you are 
    going to win games. Deeper look into this might suggest that a team can stay focused and speaks to pyshcology 
    of said team. Also, look into when the largest margin occur & why.
    
## Surprising Data!

#### *Offensive Rebounds*
    - "Traditional" thought is more offensive rebounds lead to more scoring chances, but in this case,
    doesn't appear to show in the data.
#### *Turnover Differential* 
    - "Traditional" thought is win the turnover battle, win the game. Data suggest otherwise. Edge case for 
    this stat could be that not every BLK turns into a turnover.
#### *3P%*
    - "Traditional" thought is 3 pointers are worth more than 2 pointers, therefore if you shot a higher 3% the 
    result would be positivly correlated to wins. This feature had a NEGATIVE correlation with wins.
    
# Cross-Verified Results

## *Logistic Regression Model*

###  *Model Predicted 91% of Teams Correctly Based on NBA_Feat from Above*

              precision    recall  f1-score   support

           0       0.92      0.88      0.90        97
           1       0.90      0.94      0.92       119

    accuracy                           0.91       216

###### * I took out wins as a feature because I felt like that would make it to easy for the algo to determine if a team made the playoffs since we already establish a rough estimate on how many wins it takes. 

## *Random Forest Model*
###  *Model Predicted 92% of Teams Correctly Based on NBA_Feat increasing Log Reg model*

              precision    recall  f1-score   support

           0       0.92      0.89      0.91        97
           1       0.91      0.94      0.93       119

    accuracy                           0.92       216
 
