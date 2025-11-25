# Task-2-Moving-object-using-SMA-
This Python program calculates the Simple Moving Average (SMA) for a list of closing prices. It uses Pandas DataFrame to store the dates and close prices, and a custom function simple() to manually compute SMA using loops.

Step-by-Step Explanation 

Step 1: Import pandas
import pandas as pd
We import pandas because we need DataFrame for storing tabular data.

Step 2: Create sample data
data = {
    "Date": pd.date_range(start="2006-01-01", periods=10),
    "close": [100,102,103,105,110,111,107,108,109,110]
}
Date → 10 continuous dates starting from 1 Jan 2006
close → 10 stock prices

Step 3: Convert to DataFrame
df = pd.DataFrame(data)
df.set_index("Date", inplace=False)
This creates a table like:
Date	close
2006-01-01	100
2006-01-02	102
...	...

🧮 Step 4: Create SMA Function
def simple(df, window):
This function calculates SMA for the given period (window).

Working Inside Function

A. Create empty list to store SMA values
sma_list = []

B. Loop through each row
for i in range(len(df)):

C. For first few rows where SMA cannot be calculated
if i < window - 1:
    sma_list.append(None)
Example: For window = 5
First 4 rows will get None because you need 5 values to calculate average.

D. Calculate SMA manually
total = 0
for j in range(i - window + 1, i + 1):
    total += df['close'].iloc[j]
sma_list.append(total / window)

This loop adds last 'window' number of close prices.
E. Add new column in DataFrame
df[f"sma_{window}"] = sma_list

F. Return the updated DataFrame
return df

🧾 Step 5: Call Function
result = simple(df, 5)
print(result)

Features

✔ Manual SMA Calculation (No built-in rolling functions)
✔ Beginner-friendly code with clear logic
✔ Uses Pandas DataFrame to store price & SMA
✔ Flexible window size (5-day, 10-day, etc.)
✔ Auto-generated date range
✔ Handles unavailable SMA values
✔ Easily extendable for API or trading bot use
✔ Fully offline — no API required

How It Works (Step-by-Step)

1️⃣ Create a sample dataset
A date range is generated using pd.date_range()
Closing prices are stored in a list
Both are combined into a DataFrame

2️⃣ SMA function receives:
DataFrame
Window size (example: 5)

3️⃣ Loop Runs Through Each Row
For each row:
If there are not enough previous values → append None
Else → calculate average of last window closing prices

4️⃣ Add SMA Column
The calculated SMA list is added as a new column in DataFrame.

5️⃣ Print Final Data
It shows:
Date
Close pric
SMA value
