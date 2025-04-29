# Multi-Portfolio Backtest Framework
A comprehensive backtesting system that allows comparison of multiple stock portfolios against a benchmark. This framework calculates extensive performance metrics, conducts sector analysis, visualizes results, and analyzes portfolio overlaps.

<img width="713" alt="image" src="https://github.com/user-attachments/assets/479cbc0b-41fb-432c-bca2-9c03439e5192" />

# Features

Multi-Portfolio Analysis: Compare up to three different portfolios against a benchmark

<img width="371" alt="image" src="https://github.com/user-attachments/assets/050a6ce5-f7fb-43db-8dc7-633e2a77765c" />

Comprehensive Metrics: Calculate 25+ risk and performance metrics including Sharpe, Sortino, Alpha, Beta, etc.

<img width="398" alt="image" src="https://github.com/user-attachments/assets/9f6d1731-6507-4010-9957-eb7644610dac" />

Sector Analysis: Analyze sector weightings and compare across portfolios

<img width="354" alt="image" src="https://github.com/user-attachments/assets/ef63245b-d21e-4573-89ec-01a321a27ed4" />

Advanced Visualization: Generate performance charts, drawdown analysis, and monthly return heatmaps

<img width="638" alt="image" src="https://github.com/user-attachments/assets/a964dbab-90f5-4d84-a165-3ddc455ede3a" />

<img width="721" alt="image" src="https://github.com/user-attachments/assets/b72d9f31-11e2-4126-a43d-9548bc4aefc0" />

<img width="546" alt="image" src="https://github.com/user-attachments/assets/ea7f8894-b3a6-4384-b78d-4e83394bd2ad" />

Portfolio Overlap: Quantify the overlap between different portfolios

<img width="358" alt="image" src="https://github.com/user-attachments/assets/b9cf69c7-c59e-409f-be34-96ce1ffec3e6" />


# Installation
bashCopypip install pandas numpy matplotlib seaborn requests plotly yfinance scipy tabulate statsmodels IPython

# API Requirements
The code uses the following APIs (API keys needed):
Financial Modeling Prep (FMP)
Alpha Vantage

# Default: Run a 15-year backtest
You can change the timedelta to run any year at a time, currently it is set to "15", it could be 5 or 1 or 30, it will only run stocks for data it has for

Main execution
if __name__ == "__main__":
    print("Starting comprehensive portfolio backtest...")
    
    # Run the backtest with a 3-year lookback (explicitly set)
    result = run_backtest(start_date=(datetime.now() - timedelta(days=15*365)).strftime('%Y-%m-%d'))
    
    print("Backtest completed successfully!")


# Specify custom portfolios
The code comes with three pre-configured portfolios:

Portfolio 1: 140 equally-weighted stocks
Portfolio 2: 81 equally-weighted stocks
Portfolio 3: 29 stocks with custom weights

You can modify these portfolios by editing the portfolio1_tickers, portfolio2_tickers, and portfolio3_tickers variables along with the portfolio3_weights.

# Explanations

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

# Limitations

API rate limits may restrict sector data retrieval for large portfolios
Historical data availability may vary by ticker
Survivorship bias is not addressed (only analyzes stocks that exist today)
No transaction costs or slippage modeling

# Dependencies

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
