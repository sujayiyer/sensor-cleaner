# Sensor Data Cleaner & Visualizer

A beginner Python project for loading messy sensor logs, cleaning them with
pandas, and plotting the trends with matplotlib. No machine learning - just the
data-handling fundamentals that everything else builds on.

## What it does

- Loads a CSV of sensor readings (built around the UCI Air Quality dataset)
- Handles real-world data quirks: semicolon separators, comma decimals, and
  missing values stored as the sentinel value -200
- Combines split Date and Time columns into a single timestamp
- Removes duplicate rows and trailing empty rows/columns
- Fills missing values (interpolation and forward-fill)
- Flags and handles outlier spikes
- Plots each sensor over time, plus a before-and-after view of the cleaning
- Saves the cleaned data to a new CSV and the plots as PNG files

All of this runs in a single Jupyter notebook.

## Requirements

- Python 3.9 or newer
- pandas
- numpy
- matplotlib
- jupyter

Install everything with:

    pip install pandas numpy matplotlib jupyter

## Getting the data

Download the UCI Air Quality dataset from:

    https://archive.ics.uci.edu/dataset/387/air+quality

Place the CSV in the `data/raw/` folder. The notebook also includes a cell that
generates fake practice data, so you can run it end to end before you download
anything.

## How to run

1. Open the notebook:

       jupyter notebook sensor_data_cleaner.ipynb

2. Run the cells from top to bottom, in order. Notebooks share state between
   cells, so skipping around can cause confusing errors.

3. Start with the practice-data section to confirm the cleaning steps work,
   then point the loader at the real UCI file.


## A note on secrets

This project is local-only and does not use any API keys. If you later extend
it to pull live data from an online source, keep any keys in a git-ignored
`.env` file and load them with python-dotenv. Never hardcode a key in the
notebook or print it to the output.

## License

Use it freely for learning. The UCI Air Quality dataset is licensed under
CC BY 4.0, so credit the source if you publish anything based on it.
