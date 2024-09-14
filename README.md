# cs50 Final
#### Video Demo: https://youtu.be/fD3lMN7AS5A?si=s-Nn6DYDw3UKCSmf

## Description
# Stock Price Analysis and Prediction Tool
This is my final project for "Harvard CS50 Introduction to programming with Python".

The Stock Price Analysis and Prediction Tool is a comprehensive Python-based application designed to analyze and forecast stock prices using various technical indicators, portfolio metrics, sentiment analysis, and basic machine learning techniques. This tool is ideal for investors, analysts, and students who want to explore the dynamics of stock market data and make data-driven investment decisions.


## Table of Contents

1. [Overview](#overview)
2. [Features](#features)
   - [Stock Data Retrieval](#stock-data-retrieval)
   - [Technical Analysis](#technical-analysis)
   - [Portfolio Analysis](#portfolio-analysis)
   - [Sentiment Analysis](#sentiment-analysis)
   - [Stock Price Prediction](#stock-price-prediction)
   - [Interactive Visualizations](#interactive-visualizations)
   - [Testing](#testing)
3. [Installation](#installation)
   - [Cloning the Repository](#cloning-the-repository)
   - [Setting Up a Virtual Environment](#setting-up-a-virtual-environment)
   - [Installing Dependencies](#installing-dependencies)
4. [Usage](#usage)
   - [Running the Main Program](#running-the-main-program)
   - [Understanding the Output](#understanding-the-output)
   - [Running Tests](#running-tests)
5. [Project Structure](#project-structure)
6. [Detailed Function Descriptions](#detailed-function-descriptions)
   - [Main Function](#main-function)
   - [Stock Data Retrieval Function](#stock-data-retrieval-function)
   - [Mean and Median Calculation Functions](#mean-and-median-calculation-functions)
   - [Technical Indicators Calculation Function](#technical-indicators-calculation-function)
   - [Plotting Function](#plotting-function)
   - [Stock Comparison Function](#stock-comparison-function)
   - [Trend Prediction Function](#trend-prediction-function)
   - [Portfolio Analysis Function](#portfolio-analysis-function)
   - [Sentiment Analysis Function](#sentiment-analysis-function)
7. [Dependencies](#dependencies)
8. [Advanced Features](#advanced-features)
9. [Future Enhancements](#future-enhancements)
10. [Contributing](#contributing)
11. [License](#license)

1. ## Overview

The Stock Price Analysis and Prediction Tool is an advanced Python application designed for analyzing historical stock price data and predicting future trends. It leverages various financial and machine learning libraries to provide comprehensive insights into stock performance. The tool is suitable for both novice investors and experienced analysts who want to explore the intricacies of stock market dynamics.

2. ## Features

### Stock Data Retrieval

This tool uses the `yfinance` library to fetch historical stock data directly from Yahoo Finance. Users can specify one or more stock symbols as command-line arguments, and the tool will retrieve up to one year of daily data for each symbol. The data includes important financial metrics such as Open, High, Low, Close, Volume, and Adjusted Close prices.

- **Customization**:
Users can modify the time period and intervals (daily, weekly, monthly) by tweaking the parameters in the `fetch_stock_data` function.

- **Data Accuracy**:
Yahoo Finance is a widely trusted source, ensuring that the data fetched is reliable and up-to-date.

### Technical Analysis

The tool calculates and plots several key technical indicators, which are crucial for making informed trading decisions:

- **Simple Moving Averages (SMA)**:
The SMA is a fundamental indicator that smooths out price data to help identify trends over a specified period. The tool computes both the 50-day and 200-day SMAs.
  - The 50-day SMA is typically used to identify short-term trends, while the 200-day SMA is used for long-term trends.
  - The tool visualizes these averages alongside the actual stock prices, providing a clear picture of the market trends.

- **Bollinger Bands**:
 Bollinger Bands consist of a middle band (typically a 20-day SMA) and two outer bands representing two standard deviations above and below the middle band.
  - Bollinger Bands are used to gauge the volatility of a stock. When the bands widen, it indicates higher volatility, and when they contract, it suggests lower volatility.
  - The tool plots the upper and lower Bollinger Bands on the price chart, allowing users to see potential breakouts or reversals.

- **MACD (Moving Average Convergence Divergence)**:
 The MACD is a trend-following momentum indicator that shows the relationship between two moving averages of a stock's price.
  - The MACD line is calculated by subtracting the 26-day EMA from the 12-day EMA, and the signal line is a 9-day EMA of the MACD line.
  - The tool plots both the MACD line and the signal line, along with a histogram that shows the difference between the two, helping users spot potential buy and sell signals.

- **RSI (Relative Strength Index)**:
The RSI is a momentum oscillator that measures the speed and change of price movements.
  - RSI values range from 0 to 100, with readings above 70 indicating that a stock is overbought and readings below 30 indicating that it is oversold.
  - The tool calculates the RSI and plots it on a separate chart below the price data, providing insights into potential reversals.

### Portfolio Analysis

The portfolio analysis feature allows users to analyze the performance of multiple stocks as a portfolio. This is particularly useful for investors who hold a diversified set of assets.

- **Cumulative Returns**: T
his metric shows the total return of each stock over the specified period. It helps in comparing the overall performance of different stocks in the portfolio.

- **Volatility**:
Volatility is a measure of the risk associated with a stock's returns. The tool calculates the standard deviation of daily returns to quantify volatility.

- **Sharpe Ratio**:
 The Sharpe Ratio is a risk-adjusted measure of return. It compares the excess return of the stock (return above the risk-free rate) to its volatility. A higher Sharpe Ratio indicates better risk-adjusted performance.

### Sentiment Analysis

Sentiment analysis provides an additional layer of insight by analyzing the sentiment of news articles, tweets, or other text content related to the stocks.

- **VADER Sentiment Analysis**:
 The tool uses the `vaderSentiment` library, which is specifically attuned to sentiments expressed in social media. It scores text on a scale from -1 (negative sentiment) to +1 (positive sentiment).

- **Customizable Input**:
Users can input custom text or integrate the tool with a data source (e.g., Twitter API) to analyze live sentiment data.

- **Visualization**:
The sentiment scores are presented in an easy-to-understand format, with a summary of the overall sentiment (positive, negative, or neutral).

### Stock Price Prediction

The tool includes a simple linear regression model to predict future trends in stock prices based on historical data. This feature provides a basic forecasting tool that can be used as a starting point for more sophisticated models.

- **Linear Regression**:
The tool applies linear regression to model the relationship between the time (independent variable) and the stock price (dependent variable).

- **Trend Visualization**:
The predicted trend is plotted alongside the actual stock prices, allowing users to compare the forecasted values with the observed data.

- **Customization**:
Advanced users can modify the model to include more complex features or switch to other machine learning algorithms like Decision Trees, Random Forest, or LSTM networks.

### Interactive Visualizations

One of the standout features of this tool is its use of `plotly` for creating interactive charts and plots. These visualizations provide a more engaging way to explore stock data and technical indicators.

- **Interactive Elements**:
 Users can zoom in and out, hover over data points for more details, and toggle different data series on and off.

- **Multiple Charts**:
The tool generates separate charts for each technical indicator, allowing users to focus on specific aspects of the stock's performance.

- **Exporting**:
 Users can export the interactive charts as static images or HTML files for inclusion in reports or presentations.

### Testing

To ensure the reliability and accuracy of the tool, test cases are provided using the `pytest` framework. These tests cover key functions and ensure that the calculations and data retrieval processes are working as expected.

- **Test Coverage**:
The tests cover data fetching, mean and median calculations, and the correctness of technical indicator computations.

- **Ease of Use**:
 Running the tests is straightforward and provides immediate feedback on the integrity of the codebase.

3. ## Installation

To use the Stock Price Analysis and Prediction Tool, you need to set up your Python environment and install the necessary libraries.

### Cloning the Repository

Start by cloning the repository to your local machine:

`bash
git clone https://github.com/code50/114553345
cd stock-analysis-tool


 Create and activate a virtual environment (optional but recommended):
      python -m venv venv
      source venv/bin/activate  # On Windows: venv\Scripts\activate

 **Install the required libraries**:
     pip install -r requirements.txt

4. ## Usage
### Running the Main Program

- You can analyze one or more stocks by providing their symbols as command-line arguments. For example:
    python project.py AAPL,GOOGL,MSFT

This will:

 1. Fetch historical stock data for Apple, Google, and Microsoft.
 2. Calculate and display technical indicators like SMA, Bollinger Bands, MACD, and RSI.
 3. Plot the stock data with these indicators.
 4. Perform a portfolio analysis if multiple stocks are provided.
 5. Run a basic sentiment analysis on each stock.
 6. Predict future trends using linear regression.

### Understanding the Output

Stock Data and Indicators:
 The tool outputs a series of plots showing the stock's closing prices along with the calculated technical indicators (SMA, Bollinger Bands, MACD, RSI).

Portfolio Analysis:
 If multiple stocks are provided, additional plots showing cumulative returns, volatility, and Sharpe Ratios will be displayed.

Sentiment Analysis:
 The sentiment score for each stock will be displayed, giving a quick overview of the market sentiment.

Prediction:
 The linear regression model's predictions will be plotted alongside the actual prices, helping you visualize potential future trends.


 ### Running Tests

To ensure that the functions are working as expected, you can run the tests provided in test_project.py:
    pytest test_project.py

5. ## Project Structure
   .
├── project.py             # Main script containing the primary functions
├── test_project.py        # Test cases for the functions
├── requirements.txt       # List of required Python libraries
└── README.md              # Project documentation


6. ## Detailed Function Descriptions

### Main Function
main()
The main function is the entry point of the application.
it handles command-line arguments, fetches stock data, performs analysis, and triggers the plotting of results. It ensures a seamless flow from data retrieval to analysis and visualization.

### Stock Data Retrieval Function
fetch_stock_data(stock_symbol: str) -> pd.DataFrame
This function retrieves historical stock data for a given stock symbol using the yfinance library. The data includes daily Open, High, Low, Close, Volume, and Adjusted Close prices. The function returns this data as a pandas DataFrame.

### Mean and Median Calculation Functions
calculate_mean(data: pd.DataFrame) -> float
Calculates the mean (average) of the closing prices in the provided DataFrame. This function is useful for getting a sense of the average price level over a period.


### Technical Indicators Calculation Function
calculate_technical_indicators(data: pd.DataFrame) -> pd.DataFrame
This function calculates various technical indicators, including SMA, Bollinger Bands, MACD, and RSI. These indicators are added as new columns to the DataFrame, allowing for detailed technical analysis.

### Plotting Function
plot_stock_data(data: pd.DataFrame, symbol: str)
This function generates interactive plots using plotly. It plots the stock’s closing prices along with the calculated technical indicators. The plots are interactive, allowing users to zoom in, hover over data points, and explore the data in detail.

### Stock Comparison Function
compare_stocks(data: dict)
Compares the performance of multiple stocks by plotting their closing prices on the same graph. This function is useful for visually comparing the price trends of different stocks over the same period.

### Trend Prediction Function
trend_prediction(data: pd.DataFrame)
Applies linear regression to predict future stock price trends. The predicted prices are plotted alongside the actual closing prices, allowing users to visualize how well the model fits the historical data.

### Portfolio Analysis Function
portfolio_analysis(data: dict)
Analyzes the performance of a portfolio of stocks by calculating cumulative returns, volatility, and Sharpe Ratios. The function provides visualizations that help users assess the risk and return characteristics of their portfolio.

### Sentiment Analysis Function
sentiment_analysis(symbol: str)
Performs sentiment analysis using the vaderSentiment library. It analyzes the sentiment of news articles or social media content related to the stock, providing a sentiment score that indicates whether the sentiment is positive, negative, or neutral.

7. ## Dependencies

The following Python libraries are required for this project:
pandas: For data manipulation and analysis.
numpy: For numerical computations.
matplotlib: For basic plotting and visualization.
plotly: For creating interactive visualizations.
yfinance: For fetching historical stock data from Yahoo Finance.
scikit-learn: For implementing machine learning models like linear regression.
vaderSentiment: For performing sentiment analysis.
tweepy: (Optional) For accessing Twitter’s API to fetch tweets for sentiment analysis.
pytest: For running test cases and ensuring code reliability.
dash or streamlit: (Optional) For creating a web-based dashboard for real-time data visualization.


8. ## Advanced Features

The tool can be extended with the following advanced features:

Advanced Machine Learning Models: Implement more sophisticated models like LSTM or ARIMA for better time series forecasting.
Real-Time Data Streaming: Integrate real-time data streams using WebSockets or APIs for continuous updates and live analysis.
Enhanced Sentiment Analysis: Use more advanced natural language processing techniques or integrate with live news feeds for dynamic sentiment analysis.
Custom Dashboards: Use dash or streamlit to create a user-friendly web interface that allows for interactive exploration of the data and indicators.


9. ## Future Enhancements


The following enhancements are planned for future versions:

Integration with More Data Sources: Expand the data retrieval capabilities to include other financial data sources like Alpha Vantage or Quandl.
Portfolio Optimization: Implement algorithms for optimizing the portfolio based on risk, return, and other criteria.
Backtesting: Add a backtesting feature that allows users to test different trading strategies on historical data.
User Authentication: Implement user authentication for personalized experiences and data security.
Cloud Deployment: Deploy the tool on a cloud platform like AWS or Heroku for accessibility from anywhere.

10. ## Contributing

Contributions are welcome! Here’s how you can contribute:

Fork the repository: Create a new branch for your feature or bug fix.
Make your changes: Ensure that your code follows the project’s style guidelines and passes all tests.
Submit a pull request: Describe the changes you’ve made and why they should be merged.


Reporting Issues
If you encounter any issues or have suggestions for improvements, please open an issue on the GitHub repository. Be sure to include as much detail as possible to help us understand the problem or suggestion.


11. ## License

This project is licensed under the MIT License. You are free to use, modify, and distribute this software, provided that you include the original license and copyright notice in any copies or substantial portions of the software.


Contact Information
For any inquiries or further information, please contact:

Project Maintainer: varun kumar
GitHub Repository: Stock Price Analysis and Prediction Tool

Thank you for using the Stock Price Analysis and Prediction Tool! We hope it helps you make informed investment decisions and enhances your understanding of stock market dynamics.
