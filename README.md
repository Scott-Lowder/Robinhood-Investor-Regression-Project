# Robinhood Investor Regression Project

## Hypothesis:
Research Question:
Is influence of individual Robinhood investors on a stock's risk level different for small companies versus large companies?

Hypothesis and Regression Specification:
Yes, a positive change in Robinhood holdings will have a more pronounced positive effect on volatility for smaller firms.

Null Hypothesis ($H_0$): The influence of Robinhood accounts changes on volatility is the same for all firms, regardless of their market size. (Key coefficient is zero.)

Main Regression Specification: Pooled OLS Regression model. Main objective is to estimate the coefficient $\beta_4$, which captures the interaction effect between Robinhood attention and firm size. Use squared returns ($R_{i,t}^2$) as the measure for next-day volatility. $$R_{i,t}^2 = \alpha + \beta_1 R_{i,t-1}^2 + \beta_2 \Delta \text{RH}_{i,t-1} + \beta_3 \text{SIZE}_i + \beta_4 (\Delta \text{RH}_{i,t-1} \times \text{SIZE}_i) + \eta_{i,t}$$
- $\mathbf{R_{i,t}^2}$: Next-Day Volatility. The squared daily return, which is our proxy for how risky or volatile the stock was.
- $\mathbf{R_{i,t-1}^2}$: Lagged Volatility. Yesterday's volatility. This controls for the tendency of high-volatility days to follow each other.
- $\mathbf{\Delta \text{RH}_{i,t-1}}$: Robinhood Attention. The percentage change in Robinhood account holders, measured on the previous day.
- $\mathbf{\text{SIZE}_i}$: Firm Size. A rank based on market capitalization, where a higher value means a relatively smaller company.
- $\mathbf{\beta_4 (\Delta \text{RH}_{i,t-1} \times \text{SIZE}_i)}$: Key Test. This is the combined effect of Robinhood attention and small size. If $\beta_4$ is positive and significant, hypothesis is supported.
- $\eta_{i,t}$: Error Term.
