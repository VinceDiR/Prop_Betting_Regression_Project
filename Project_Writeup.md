# Predicting NBA Scoring Performances
Nate DiRenzo

## Abstract
The goal of this project was to assess the viability of using linear regression models to accurately predict NBA scoring performances, and by extension inform a long-term, profitable betting strategy. To do this, I looked at contemporary betting lines for individual players' alongside recent game data to predict scoring in an upcoming game. I engineered a number of large number of interaction features, and used LassoCV to identify the most predictive. I then evaluated models created with that feature subset to determine which would perform best, and assessed the practical performance of the optimal model against the most recent betting projections and scoring performances.

## Design
This project came about for a few reasons:
1. Since 2018, sports betting has absolutely exploded in the United States: $52 Billion was legally wagered in 2021 alone. Not only is sports betting a massive industry, but a cultural phenomenon. 
2. There is a wealth of statistics and metrics, and information on NBA players and games publicly available, and NBA teams, fron offices, and fans value on sophisticated data alaysis
3. I am a huge NBA fan! Go Sixers!

## Data
- The betting dataset includes ~10,000 rows of Points proposition bets scraped from [BettingPros](https://www.bettingpros.com/nba/picks/prop-bets/) since the beginning of the 2021-2022 season on October 19, 2021.
- The player game logs contain ~15,000 rows of player-level game statistics taken from [Stathead](https://stathead.com/basketball/pgl_finder.cgi?request=1&lg_id=NBA&order_by=date_game&match=game&season_start=1&year_max=2022&is_playoffs=N&season_end=-1&order_by_asc=1&age_min=0&age_max=99&year_min=2022&offset=15000) since the beginning of the 2021-2022 season on October 19, 2021.
- The team game logs contain ~1,500 rows of team-level game statistics taken from [Stathead](https://stathead.com/basketball/tgl_finder.cgi?request=1&lg_id=NBA&order_by=date_game&match=game&is_playoffs=N&year_max=2022&order_by_asc=1&team_seed_cmp=gt&opp_seed_cmp=gt&year_min=2022&offset=1300)
## Algorithms

*Feature Engineering*
1. Merge player/team data and calculate derived features such as days rest, rolling 2PA, rolling opponent points.
2. Merge player/team data with betting data and align previous game statistics with current game betting information.
3. Encode binary and categorical variables such as team, opponent, position, home/away.
4. Use LassoCV to identify most salient features from 150+
5. Try PolynomialFeatures(degrees=2) to produce higher accuracy
*Models*
  
LassoCV, Linear Regression, Polynomial Regression, and ElasticNet were used before settling on Linear Regression as the model with strongest cross-validation performance, predictive power, and relative lack of complexity. LassoCV feature selection informed the choice of which features made it into the final Linear Regression model.

*Model Evaluation and Selection*
  
The dataset was broken into 60/20/20 Train, Validation, and Test split for each model. Models were then trained and scored on the training data, and scored again on validation data. By comparing these two scores we determined if a given model was under/overfitting, and by comparing validation scores across models we were able to determine the optimal model to use.

By virtue of its robust performance, relative low coplexity, and high interpretability, simple linear regression was chosen as the optimal model.

**Final Linear Regression Validation Scores:**
   - R2: .46
   - Mean Absolute Error: 4.71
   - Root Mean Squared Error: 4.96

**Final Linear Regression Test Scores** 
   - R2: .45
   - Mean Absolute Error: 4.72 
   - Root Mean Squared Error: 6.04

## Tools
- Numpy and Pandas for data manipulation
- FuzzyWuzzy and Unidecode for merging
- Scikit-learn for modeling
- Matplotlib and Seaborn for plotting

## Communication
A summary of this project's findings have been provided in the [PDF](https://github.com/NateDiR/Prop_Betting_Regression_Project/blob/main/NBA%20Linear%20Regression%20Presentation.pdf) included in this repo. In addition, [Step 1](https://github.com/NateDiR/Prop_Betting_Regression_Project/blob/main/Web%20Scraping%20Script%20(Step%201).ipynb), [Step 2](https://github.com/NateDiR/Prop_Betting_Regression_Project/blob/main/Merging%20Player%20%2B%20Team%20Stats%20(Step%202).ipynb), [Step 3](https://github.com/NateDiR/Prop_Betting_Regression_Project/blob/main/Feature%20Engineering%20and%20Merge%20Player%20%2B%20Team%20Stats%20with%20Betting%20Data%20(Step%203).ipynb), [Step 4](https://github.com/NateDiR/Prop_Betting_Regression_Project/blob/main/Modeling%20%2B%20Scoring%20(Step%204).ipynb) of the data collection and modelling pipeline are available for public use. Last, [a blog post](https://medium.com/@NathanielDiRenzo) outlining the project in more detail will be produced in the future.
