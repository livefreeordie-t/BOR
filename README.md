# BOR Method - Session-Based Candlestick Charting

This project implements the BOR (Box of Range) method for analyzing and visualizing futures market sessions using Python, pandas, and Plotly. The notebook processes historical intraday data, identifies key session windows, and generates annotated candlestick charts for each session.

## Features
- Loads and concatenates multiple yearly CSV files of intraday futures data.
- Assigns each data point to a specific trading session (Monday–Friday) based on hard-coded session windows.
- Calculates and visualizes:
  - Premarket high/low and range (08:00–08:59:59, New York time)
  - 08:28 candle range
  - 00:00 open price line
  - Previous day session high (PD BSL) and low (PD SSL)
- Generates interactive Plotly candlestick charts for each session, zoomed to 07:00–12:00, with custom annotations and overlays.
- Saves each chart as an HTML file for easy review.

## How It Works
1. **Data Loading:**
   - Reads all CSV files from the specified yearly data folder.
2. **Session Assignment:**
   - Defines session windows for each weekday (Monday–Friday) using pandas date/time logic.
3. **Session Analysis:**
   - For each session, calculates premarket range, 08:28 candle, 00:00 open, and previous session high/low.
4. **Chart Generation:**
   - Plots each session as a candlestick chart with Plotly.
   - Adds colored rectangles, lines, and text annotations for key levels.
   - Saves each chart as an HTML file in the output directory.

## Requirements
- Python 3.8+
- pandas
- plotly
- IPython (for display)
- Raw 1 minute data

Install requirements with:
```bash
pip install pandas plotly ipython
```

## Usage
1. Place your yearly CSV files in the `yourfile location` directory.
2. Run the notebook `BOR.ipynb`.
3. Output charts will be saved in `yourfile location`.

## Customization
- Adjust session windows or timezones as needed in the code.
- Change the output directory by modifying the `save_dir` variable.

## Output Example
Each session's chart is saved as an HTML file and includes:
- Candlestick bars for the session
- BOR box (red, 08:00–08:59:59)
- 08:28 candle range annotation
- 00:00 open price line (blue)
- Previous day high/low lines (maroon)
- Annotations for all key levels

---

**Author:** livefreeordie_t (https://x.com/livefreeordie_t)
**Last updated:** July 2025
