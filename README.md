# Piotroski Score Calculator for S&P 500 Companies

A Python tool that automatically calculates Piotroski F-Scores for S&P 500 companies using financial data from Yahoo Finance. The Piotroski F-Score is a comprehensive metric used to evaluate a company's financial strength based on nine different aspects of financial performance and position.

## Features

- Automatic retrieval of financial data using the `yfinance` library
- Calculation of three main components of the Piotroski F-Score:
  - Profitability (0-5 points)
  - Leverage/Liquidity (0-2 points)
  - Operating Efficiency (0-2 points)
- Web scraping of current S&P 500 companies list from Wikipedia
- Ranking of companies based on their Piotroski scores

## Dependencies

- yfinance
- pandas
- requests
- beautifulsoup4

## Installation

```bash
pip install yfinance pandas requests beautifulsoup4
```

## Usage

1. Import the required libraries and functions:
```python
from potroski_score import get_financial_statements, profitability_statement
from potroski_score import leverage, efficiency_statement
```

2. To analyze a single company:
```python
ticker = "AAPL"
financial_statements = get_financial_statements(ticker)
profitability = profitability_statement(financial_statements)
leverage_score = leverage(financial_statements)
efficiency = efficiency_statement(financial_statements)
total_score = profitability + leverage_score + efficiency
```

## How the Score is Calculated

### Profitability (5 points)
- Positive net income (1 point)
- Net income improvement year over year (1 point)
- Positive return on assets (1 point)
- Positive operating cash flow (1 point)
- Operating cash flow exceeding net income (1 point)

### Leverage/Liquidity (2 points)
- Decreasing debt-to-equity ratio (1 point)
- Improving current ratio (1 point)

### Operating Efficiency (2 points)
- Improving gross profit margin (1 point)
- Improving asset turnover ratio (1 point)

## Interpretation

The total Piotroski Score ranges from 0 to 9:
- Scores 7-9: Strong financial position
- Scores 4-6: Moderate financial position
- Scores 0-3: Weak financial position

## Limitations

- Relies on the accuracy of Yahoo Finance data
- May not work for companies with incomplete financial data
- Limited to S&P 500 companies in the current implementation

## Contributing

Feel free to fork this repository and submit pull requests. You can also open issues for any bugs or feature requests.

## License

[MIT License](LICENSE)
