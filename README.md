# Task-2-Moving-object-using-SMA-
A lightweight Flask-based API that calculates the Simple Moving Average (SMA) from a list of closing prices. You send an array of prices and a window size, and the API returns SMA values for each date.

How it Works

User sends a list of closing prices
Pandas creates a date range
Custom simple() function calculates SMA manually
API returns fully structured JSON with dates, prices, and SMA values

Features

Accepts JSON input with close prices and SMA window size
Automatically generates dates starting from a given start date
Calculates SMA manually (no external technical-analysis libraries)
Returns full dataset in JSON format
Built using Flask + Pandas

TEST IN POSTMAN

Step 1 → Open Postman
Step 2 → Select POST method
Step 3 → Enter URL:
http://127.0.0.1:5001/sma

Step 4 → Go to Body tab
Select raw
Select JSON

Step 5 → Paste this JSON:
{
  "close": [100,102,103,105,110,111,107,108,109,110],
  "window": 5,
  "start_date": "2006-01-01"
}

Step 6 → Click Send
