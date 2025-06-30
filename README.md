# ARIMA-GARCH Implementation for EUR/USD Forecasting

This repository contains an R script that implements an ARIMA-GARCH model to forecast EUR/USD exchange rate returns and compares the strategy's performance against a long-term investment approach.

## Overview

The script performs the following:
1. Implements a rolling window ARIMA-GARCH model for EUR/USD return forecasting
2. Generates trading signals based on model predictions
3. Compares the strategy's cumulative returns against a simple buy-and-hold approach
4. Visualizes the results

## Key Features

- **Data Processing**: Reads EUR/USD historical data and calculates log returns
- **Model Selection**: 
  - Uses AIC to select optimal ARIMA(p,q) order (p,q < 4)
  - Implements GARCH(1,1) with skewed generalized error distribution
- **Forecasting**: Makes one-step-ahead predictions using a rolling window approach
- **Performance Comparison**: Compares strategy returns against long-term investing

## Requirements

The script requires the following R packages:
- `quantmod`
- `timeSeries`
- `rugarch`

Install them using:
```R
install.packages(c("quantmod", "timeSeries", "rugarch"))

Usage

    Ensure you have a CSV file named EURUSD.csv with closing prices in a column named "C"

    Run the script in R/RStudio

    The script will:

        Process the data

        Fit models using a rolling window (default: 100 observations)

        Generate forecasts and trading signals

        Plot cumulative returns comparison

Customization

    Adjust window.length to change the rolling window size

    Modify ARIMA order limits by changing the p and q loop ranges (currently 1-4)

    Change the GARCH specification in ugarchspec() if needed

Output

The script produces a plot showing:

    Green line: Cumulative returns from the ARIMA-GARCH strategy

    Red line: Cumulative returns from long-term investing

Note

The script includes warnings about being a "SLOW PROCEDURE" due to:

    Nested loops for ARIMA order selection

    Rolling window refitting

    GARCH model estimation

Consider running on a subset of data for testing purposes.

The CSV data file is uploaded as well for subsequent usage.
