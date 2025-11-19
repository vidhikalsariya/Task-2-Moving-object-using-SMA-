# Task-2-Moving-object-using-SMA-
A lightweight Flask-based API that calculates the Simple Moving Average (SMA) from a list of closing prices. You send an array of prices and a window size, and the API returns SMA values for each date.

How it Works

User sends a list of closing prices
Pandas creates a date range
Custom simple() function calculates SMA manually
API returns fully structured JSON with dates, prices, and SMA values
