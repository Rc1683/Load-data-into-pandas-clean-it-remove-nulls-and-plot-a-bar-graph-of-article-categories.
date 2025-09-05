# Load-data-into-pandas-clean-it-remove-nulls-and-plot-a-bar-graph-of-article-categories.



Temperature Data Analysis
This project demonstrates how to load, clean, and visualize weather data using Pandas and Matplotlib.
The dataset (archive.csv) contains February and March average temperatures across different regions.

Dataset
The CSV file contains the following columns:
Year → Year of observation
Punxsutawney Phil → Groundhog prediction data
February Average Temperature
February Average Temperature (Northeast)
February Average Temperature (Midwest)
February Average Temperature (Pennsylvania)
March Average Temperature
March Average Temperature (Northeast)
March Average Temperature (Midwest)
March Average Temperature (Pennsylvania)

Code Explanation
import pandas as pd
import matplotlib.pyplot as plt

# 1. Load dataset
df = pd.read_csv("/content/archive.csv")

# 2. Clean dataset (remove null values)
df_clean = df.dropna()

# 3. Compute average of all temperature columns
avg_temps = df_clean.mean(numeric_only=True)

# 4. Plot bar graph
plt.figure(figsize=(12,6))
avg_temps.plot(kind='bar')
plt.title("Average Temperatures by Month and Region")
plt.xlabel("Month / Region")
plt.ylabel("Temperature (°F)")
plt.xticks(rotation=45, ha='right')
plt.show()

Output
A bar chart comparing average February and March temperatures across different regions (Northeast, Midwest, Pennsylvania).
Example:
February Average Temperature vs March Average Temperature
Regional variations (Northeast, Midwest, Pennsylvania)

Requirements
Install dependencies before running:
pip install pandas matplotlib
Usage
Run the script in Jupyter Notebook or as a .py file:
python temperature_analysis.py
Future Improvements
Shorten long column names (e.g., Feb_NE, Mar_MW) for cleaner graphs.
Add line plots to show year-wise temperature trends.
Compare Punxsutawney Phil predictions with actual temperature data.
