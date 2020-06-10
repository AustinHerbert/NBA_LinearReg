# NBA : Why Isn't My Team making the Playoffs?

### * *Model explained ~ 94% of actual wins per team with a 3-win standard deviation compared to 7.5 with raw data!*

## Wins to Make Playoffs Based on past 32 NBA Season 
- The avg team wins ~49 games
- 50% of Playoff teams fall inbetween 42 & 56 wins
![win_boxplot](https://user-images.githubusercontent.com/64975026/84214634-8feae980-aa89-11ea-9368-b1dd59a550e7.png)

Teams should strive for winning 56 games or more in a season to statistically rely on making the Playoffs. Teams that started off slow can infer from this data that is 42 games is within striking distance, they still have a decent statistical chance of making the Playoffs.

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
## What can Teams take away from this anaysis?

#### *Convert 2PT Atempts efficiently*
    - This is obvious, but if team brought up a shot chart they could dive deeper and see what number of far 2PT 
    shot should be eliminated. Main focus here is to establish which areas to focus on.
#### *Sharing the Ball to Score*
    - Typically teams want superstars, but if that Free Agent is known to have low assist, might want to head 
    another direction. Again, deeper dive into this for individual team, I would look to see the assit totals 
    for the team based on if said player was on the floor.
#### *Outscoring by Wide Margin*
    - This is the most obvious, if you score more than the other team by a wide margin means you are going to 
    win games. Deeper look into this might suggest team can stay focus and speaks to pyshcology of said team. 
    Also, look into if when the largest margin occur and take a closer look.
    
## Surprising Data!

#### *Offensive Rebounds*
    - "Traditional" thought is more offensive rebounds lead to more points, but that in this case 
    doesn't appear to show in the data.
#### *Turnover Differential* 
    - "Traditional" thought is win the turnover battle, win the game. Data suggest otherwise. One reason 
    could be that not every BLK turns into a turnover.
#### *3P%*
    - "Traditional" thought is 3's are worth more than 2's so if you shot a higher % the result would 
    be positivly correlated.
    

