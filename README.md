**Project Overview**
<br/>
Carry trade strategies traditionally exploit interest rate differentials and currency movements. However, accurately forecasting exchange rates—particularly under the influence of the forward premium—remains a major challenge. This often makes carry trades difficult to model and exposes them to significant downside risk.
This project begins by validating the continued profitability of carry trades across G10 currencies using recent historical data. It then investigates the impact of negative interest rates on carry trade returns through linear regression analysis. Subsequently, it compares traditional interest-rate-based carry portfolios with machine learning–based alternatives, using quarterly data from 1997 to 2022 for six currencies: CHF, EUR, JPY, GBP, NOK, and SEK. The benchmark strategy goes long on the top three high-yielding currencies and short on the bottom three each quarter.<br/>
<br/>

**Implementation**
<br/>
To construct and evaluate machine learning–driven portfolios, ARIMA, CNN, and LSTM models were used to forecast currency-based returns and build equal-weighted carry portfolios. These models were benchmarked against the traditional rule-based strategy.
A modular framework was developed to enable rapid experimentation with additional ML architectures. Unlike conventional approaches that optimize for prediction accuracy (e.g., RMSE), this framework evaluates models based on portfolio performance metrics—specifically mean return, Sharpe ratio, and negative skewness—each normalized between 0 and 1. A Euclidean distance metric from the ideal point (1, 1, 1) is used as the overall model objective to balance return, risk, and skew.
The codebase is fully modular:<br/>
abstract_ml_model.py defines a base class with train and predict methods for all ML models.<br/>
model_engine.py handles training, prediction, and portfolio construction.<br/>
model_executor.py runs the full pipeline.<br/>
portfolio_builder.py compares and logs portfolio performance.<br/>
This design allows seamless integration of new models and extensions for future research.
<br/><br/>
**Key Findings**
<br />
The analysis confirms that carry trades remain profitable in the modern era, with the violation of uncovered interest rate parity (UIP) persisting across recent data. The traditional carry portfolio continued to exhibit negative skewness, as seen in historical literature.
In contrast, ML-driven portfolios—especially those using CNN and LSTM models—were not only able to generate positive average returns but also reduce downside skew.
Optimizing directly for portfolio-level outcomes, rather than prediction accuracy, proved effective in developing more risk-conscious strategies. This approach holds promise for broader application to other asset classes or systematic strategies in future financial modeling.
