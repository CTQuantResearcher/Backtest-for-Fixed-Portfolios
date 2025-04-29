Multi-Portfolio Backtest Framework
A comprehensive backtesting system that allows comparison of multiple stock portfolios against a benchmark. This framework calculates extensive performance metrics, conducts sector analysis, visualizes results, and analyzes portfolio overlaps.
<img width="713" alt="image" src="https://github.com/user-attachments/assets/479cbc0b-41fb-432c-bca2-9c03439e5192" />

Show Image
Features

Multi-Portfolio Analysis: Compare up to three different portfolios against a benchmark
Comprehensive Metrics: Calculate 25+ risk and performance metrics including Sharpe, Sortino, Alpha, Beta, etc.
Sector Analysis: Analyze sector weightings and compare across portfolios
Advanced Visualization: Generate performance charts, drawdown analysis, and monthly return heatmaps
Portfolio Overlap: Quantify the overlap between different portfolios

Installation
bashCopypip install pandas numpy matplotlib seaborn requests plotly yfinance scipy tabulate statsmodels IPython
API Requirements
The code uses the following APIs (API keys needed):

Financial Modeling Prep (FMP)
Alpha Vantage
Anthropic (optional - not used in core functionality)

Usage
Basic Usage
pythonCopyfrom portfolio_backtest import run_backtest

# Default: Run a 15-year backtest
results = run_backtest()

# Specify custom date range
from datetime import datetime, timedelta
start_date = (datetime.now() - timedelta(days=5*365)).strftime('%Y-%m-%d')
end_date = datetime.now().strftime('%Y-%m-%d')
results = run_backtest(start_date=start_date, end_date=end_date)
Configuring Portfolios
The code comes with three pre-configured portfolios:

Portfolio 1: 140 equally-weighted stocks
Portfolio 2: 81 equally-weighted stocks
Portfolio 3: 29 stocks with custom weights

You can modify these portfolios by editing the portfolio1_tickers, portfolio2_tickers, and portfolio3_tickers variables along with the portfolio3_weights.
Core Components
Data Acquisition Functions

download_price_data(): Downloads historical price data for all tickers
get_sector_data(): Retrieves sector information for tickers using multiple data sources

Performance Calculation Functions

calculate_returns(): Computes daily returns from price data
calculate_portfolio_returns(): Calculates weighted portfolio returns
calculate_cumulative_returns(): Computes cumulative returns
calculate_drawdowns(): Measures portfolio drawdowns
calculate_risk_metrics(): Generates comprehensive performance metrics

Analysis Functions

calculate_sector_weights(): Analyzes sector weightings
create_sector_weights_table(): Creates a comparison table of sector weights

Visualization Functions

create_combined_metrics_table(): Generates performance comparison tables
create_performance_charts(): Creates visualizations including:

Cumulative returns chart
Drawdown analysis
Monthly return heatmaps
Risk-return scatter plot



Sample Output
The framework generates extensive output including:

Detailed performance metrics tables
Sector weight analysis
Performance visualizations
Portfolio overlap statistics

Metrics Calculated
Return Metrics

Total Return
Annualized Return
Win Rate

Risk Metrics

Annualized Volatility
Maximum Drawdown
Average Drawdown
Average Recovery Time
Value at Risk (VaR)
Conditional VaR (CVaR)
Skewness
Kurtosis

Risk-Adjusted Metrics

Sharpe Ratio
Sortino Ratio
Calmar Ratio
Treynor Ratio
Omega Ratio

Relative Performance Metrics

Alpha
Beta
Information Ratio
Tracking Error
Upside/Downside Capture Ratios

Limitations

API rate limits may restrict sector data retrieval for large portfolios
Historical data availability may vary by ticker
Survivorship bias is not addressed (only analyzes stocks that exist today)
No transaction costs or slippage modeling

Dependencies

pandas: Data manipulation and analysis
numpy: Numerical computations
matplotlib/seaborn: Basic data visualization
plotly: Interactive charts
yfinance: Market data retrieval
requests: API communication
scipy.stats: Statistical calculations
statsmodels: Time series analysis
tabulate: Formatted table output
IPython: Enhanced display capabilities
