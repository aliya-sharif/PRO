# Portfolio Optimisation with Monte Carlo Simulation
This is a self-directed project, that finds the best stocks to hold in a portfolio, using Monte Carlo simulation to investigate the risk/return trade-off and compares that to the exact optimal portfolio found by numerical optimisation. 

# Overview:
In a set of stocks, there is a trade-off between expected return and risk (volatility). This project:
1. Downloads real historical price data for a set of stocks (Apple, Microsoft, Amazon and Google)
2. Randomly generates thousands of possible portfolios and measures the expected return, risk and Sharpe ratio.
3. Solves for the exact portfolio with the highest possible Sharpe ratio using scipy.optimize, and compares it to the best portfolio found by the Monte Carlo search.
4. Plots the efficient frontier.

![Efficient frontier](random_portfolios.png)
When run the program should:
- Show the stocks’ historical prices and daily returns
- Show the annualised return for each stock
- Find the covariance matrix (how much each pair of stock moves together)
- Find the best portfolio by doing a random search (trying 5,000 random portfolios)
- Find the exact best portfolio using numerical optimisation
- Produce a chart comparing all 5,000 simulated portfolios

# Key Concepts:
- Expected portfolio return: the weighted average of each stocks’ average return
- Portfolio risk (volatility): the chance investments will lose value or fail. Depends on the covariance which is why combing stocks that move at the same rate reduces risk compared to the risk individual stock has alone.
- Monte Carlo search: random search gives good approximate answer, making it easier to visualise and understand
- Exact optimisation: guarantees finding the exact answer, (scipy.optimize using SLSQP algorithm) without relying on luck or estimates.

# Limitations:
- Ignores costs and tax
- It cant’t predict future portfolio optimisation as it assumes the future returns/risk will be the same as the historical returns/risk

# Used:
- Python
- NumPy
- pandas
- Matplotlib
- yfinance

Aliya Sharif (undergraduate mathematics student)
(made to track progress while learning Python and Monte Carlo methods)

