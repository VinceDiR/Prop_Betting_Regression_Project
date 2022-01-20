# Predicting Company Profit Margins using Publicly Available Data #
### By: Nate DiRenzo

<br></br>
## Goal:
The goal of this project is to assess the feasibility of using Crunchbase and Google Finance data to make an accurate prediction about company profitability using simple linear regression.
<br></br>
## Question/Need:
Venture Capitalists and market speculators are always looking for ways to assess an organization's potential profitability. If we can use historical data taken from Crunchbase to reliably predict an organization's profits post-IPO, venture capitalists could more readily identify long-term profitable organizations to invest in, and speculators could more confidently invest in these organizations once they are publicly traded.
<br></br>
## Data Description:
We will use two datasets to gather our features and target variables:
- Company information from Crunchbase as features, including total funding, number of rounds, number of employees, etc.
- Contemporary finncial information from Google Finance, such as annual profit, as targets.
<br></br>
## Tools:
- **Selenium** and **Beautiful Soup** for Web Scraping
- **Pandas** and **NumPy** for Data Ingestion, EDA
- **Seaborn** for Visualization
- **Scikit-learn** for regession analysis and model testing.
<br></br>
## MVP Goal:
Produce a baseline model using the most promising features from the Crunchbase data to predict the annual profits of companies in 2020.
