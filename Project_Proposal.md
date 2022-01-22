# Informing NBA Betting Strategy Using Linear Regression #
### By: Nate DiRenzo

<br></br>
## Statement of Need:
In recent years, sports betting has exploded in popularity. Rarely are the odds offered on a particular wage a true reflection of the probability of that event happening, but rather they are an attempt by bookkeepers to 'balance the action' on both sides of a wager such that a profit is made regardless of outcome. Bettors therefore need alternative means of predicting a given proposition's outcome beyond the consensus odds being offered. In this project, we will explore the viability of predicting the results of points-based proposition wagers in the NBA. A proposition wager is a wager on an event that is independent of the game's result (e.g. Player X will score above or below 30 points). Using a combination of player and opposing team statistics, as well as Vegas betting metrics for a given proposition, we will attempt predict player performance, and use those predictions to inform our betting strategy.
<br></br>
## Goal:
The goal of this project is to assess the viability of using linear regression to predict player scoring performance in an NBA game, and how those predictions fare against publicly available betting lines from the past, and real-world wagers for upcoming NBA games.
<br></br>
## Data Description:
We will use two datasets to gather our features and target variables:
- Betting information taken from [BettingPros.com](https://www.bettingpros.com/nba/picks/prop-bets/)
- Player/Team Statistics from [basketball-reference.com](https://www.basketball-reference.com/)
<br></br>
## Tools:
- **Selenium** and **Beautiful Soup** for Web Scraping
- **Pandas** and **NumPy** for Data Ingestion, EDA
- **Seaborn** for Visualization
- **Scikit-learn** for regession analysis and model testing.
<br></br>
## MVP Goal:
Produce a baseline model using all of the features available, as well as testing metrics to inform further iterations. 
