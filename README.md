# Robinhood Investor Regression Project

## View Jupyter Notebook Here:
[View Jupyter Notebook](https://github.com/Scott-Lowder/Play-Web-Games/blob/main/Project_submission_2025%20(2).ipynb)

## Research Question
Is the influence of individual Robinhood investors on a stock's risk level different for small companies versus large companies?

## Hypothesis and Regression Specification
**Hypothesis:** Yes, a positive change in Robinhood holdings will have a more pronounced positive effect on volatility for smaller firms.

**Null Hypothesis ($H_0$):** The influence of Robinhood account changes on volatility is the same for all firms, regardless of their market size (i.e., the interaction coefficient $\beta_4$ is zero).

---

## Main Regression Specification
We utilize a **Pooled OLS Regression** model. The main objective is to estimate the coefficient $\beta_4$, which captures the interaction effect between Robinhood attention and firm size. We use squared returns ($R_{i,t}^2$) as the measure for next-day volatility.

$$R_{i,t}^2 = \alpha + \beta_1 R_{i,t-1}^2 + \beta_2 \Delta \text{RH}_{i,t-1} + \beta_3 \text{SIZE}_i + \beta_4 (\Delta \text{RH}_{i,t-1} \times \text{SIZE}_i) + \eta_{i,t}$$



## Variable Definitions:
* **$R_{i,t}^2$ (Next-Day Volatility):** The squared daily return, which is our proxy for how risky or volatile the stock was.
* **$R_{i,t-1}^2$ (Lagged Volatility):** Yesterday's volatility. This controls for the tendency of high-volatility days to follow each other (volatility clustering).
* **$\Delta \text{RH}_{i,t-1}$ (Robinhood Attention):** The percentage change in Robinhood account holders, measured on the previous day.
* **$\text{SIZE}_i$ (Firm Size):** A rank based on market capitalization, where a higher value represents a relatively **smaller** company.
* **$\beta_4 (\Delta \text{RH}_{i,t-1} \times \text{SIZE}_i)$ (Key Test):** This is the combined effect of Robinhood attention and small size. If $\beta_4$ is positive and statistically significant, the hypothesis is supported.
* **$\eta_{i,t}$ (Error Term):** The residual variance not captured by the independent variables.

## Interpretation and Conclusion
Based on the results from the regression, reject the null hypothesis that the coefficient on the interaction term ($\Delta \text{RH}_{i,t-1} \times \text{SIZE}_i$) is zero, using the standard 99% confidence level (since the P-value was $0.000$). The positive and highly significant coefficient on the interaction term ($\beta_4=0.0004$) says that the predictive power of increased Robinhood attention on next-day stock volatility is significantly greater for smaller firms (those with a higher $\text{SIZE}$ proxy value) than for larger firms, validating the research hypothesis that retail trading disproportionately impacts the market behavior of smaller stocks. Moving forward, to further explore this phenomenon, future research should incorporate firm fixed effects to control for unobserved, time-invariant differences between companies (like brand value or risk tolerance) and could also be expanded to include data on short interest as a control variable, testing whether the "Robinhood effect" is distinct from general speculative short squeezes.
