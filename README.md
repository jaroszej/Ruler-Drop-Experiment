# Ruler Drop Reaction Time Experiment

This experiment aims to measure reaction times for catching a falling ruler. Follow these steps to perform the experiment with a friend.

---

## Drop Instructions

1. **Positioning**:
   - Have your friend hold a ruler vertically above your open hand, with the zero mark (or starting point) aligned just above your thumb and index finger.
   - Keep your hand open but positioned so that the ruler is directly above it without any space between your hand and the ruler. Avoid touching the ruler to ensure the reaction is unprompted.

2. **Prepare to Catch**:
   - Relax your hand but be ready to close it to catch the ruler as soon as it starts falling.

3. **The Drop**:
   - Without warning, your friend should release the ruler, letting it drop straight down at the speed of gravity. They should not push or throw the ruler.
   - As quickly as possible, close your hand to catch the ruler. Once closed, do not move your hand!

4. **Measure the Drop**:
   - After catching the ruler, look at the measurement on the ruler where you caught it. This distance represents the drop length in inches.

5. **Record the Distance**:
   - Write down the distance in inches from the starting point to where you caught the ruler. This mark will be at the top of your closed hand on the ruler. Repeat this process for several trials to gather multiple measurements. The recommended amount is 30 trials.

6. **Jupyter Notebook**:
   - Continue on to the Python section, [Gathering Insights](#gathering-insights), where you will use programming to gather insights on the data you have collected.
---

# Python Function Documentation

These scripts allow users to record and analyze their reaction times for catching a falling ruler, as measured by distance (inches). The main functionalities include recording reaction times, importing and exporting data, viewing and filtering records, calculating comprehensive statistics, and plug-and-play results plotting.

Take some time to review these functions to understand how this analysis is done.

---
# Functions

- [`plot(subject_name=None, subject_list=None, index_range=None, date=None, date_range=None, title="Reaction Times", xlabel="Index", ylabel="Reaction Time (ms)", show_mean=False, show_median=False, show_std_band=False, show_best_fit=True)`](#plot)
- [`record_reaction_time(distance_in_inches)`](#record_reaction_time)
- [`import_from_csv(filename="reaction_times.csv")`](#import_from_csv)
- [`export_to_csv(filename="reaction_times.csv")`](#export_to_csv)
- [`view_record(index=None, end_index=None)`](#view_record)
- [`search_records(subject_name=None, date=None)`](#search_records)
- [`clear_records(index=None)`](#clear_records)
- [`stats(subject_name=None, subject_list=None, date=None, date_range=None, index_range=None)`](#stats)
- [`pretty_stats(subject_name=None, subject_list=None, date=None, date_range=None, index_range=None)`](#pretty_stats)
- [`record_ruler_drop(subject_name, distance_in_inches)`](#record_ruler_drop)

---

### Special Notes
- **Data File**: The primary data file is `reaction_times.json`, which stores records of reaction times.
- **File Backups**: Each export action creates a timestamped JSON backup (e.g., `reaction_times_<timestamp>.json`) to prevent data loss.
- **Date Format**: Use the "day-month-year" format for dates to ensure consistency.
---
### plot
---
## `plot(subject_name=None, subject_list=None, index_range=None, date=None, date_range=None, title="Reaction Times", xlabel="Index", ylabel="Reaction Time (ms)", show_mean=False, show_median=False, show_std_band=False, show_best_fit=True)`
   - **Description**: Plots reaction times with various filtering options using matplotlib, allowing control over displaying statistical lines such as mean, median, standard deviation band, and best-fit line.
   - **Parameters**:
     - `subject_name` (str, optional): Filter by a single subject's name.
     - `subject_list` (list, optional): Filter by a list of subject names.
     - `index_range` (tuple, optional): Tuple containing start and end indices to filter by.
     - `date` (str, optional): Specific date (format: "day-month-year") to filter by.
     - `date_range` (tuple, optional): Tuple with start and end dates (format: "day-month-year") to filter by.
     - `title` (str, optional): Custom title for the plot.
     - `xlabel` (str, optional): Label for the x-axis.
     - `ylabel` (str, optional): Label for the y-axis.
     - `show_mean` (bool, optional): If `True`, displays a horizontal line at the mean reaction time for each subject. Default is `False`.
     - `show_median` (bool, optional): If `True`, displays a horizontal line at the median reaction time for each subject. Default is `False`.
     - `show_std_band` (bool, optional): If `True`, displays a shaded area representing one standard deviation above and below the mean. Default is `False`.
     - `show_best_fit` (bool, optional): If `True`, displays a line of best fit for each subject's data. Default is `True`.
   - **Example**: 
     ```python
     plot(subject_name="Alice", title="Alice's Reaction Times", show_mean=True, show_best_fit=False)
     ```
--- 
## record_reaction_time
---
### `record_reaction_time(distance_in_inches)`
   - **Description**: Calculates the reaction time in milliseconds for a given ruler fall distance (in inches).
   - **Parameters**:
     - `distance_in_inches` (float): Distance the ruler fell in inches.
   - **Returns**: The reaction time in milliseconds (rounded to 4 decimal places).
   - **Example**: `record_reaction_time(7)`

---

## import_from_csv
---
### `import_from_csv(filename="reaction_times.csv")`
   - **Description**: Imports reaction time records from a CSV file and creates/overwrites a JSON file.
   - **Parameters**:
     - `filename` (str, optional): The name of the CSV file to import from (default is `"reaction_times.csv"`).
   - **Example**: `import_from_csv("reaction_times.csv")`
---
## export_to_csv
---
### `export_to_csv(filename="reaction_times.csv")`
   - **Description**: Exports all reaction time records from the JSON file to a CSV file and creates a timestamped JSON backup.
   - **Parameters**:
     - `filename` (str, optional): The name of the CSV file to export to (default is `"reaction_times.csv"`).
   - **Example**: `export_to_csv("reaction_times.csv")`

---
## view_record
---
### `view_record(index=None, end_index=None)`
   - **Description**: Displays records from the JSON file. If an index or range is provided, only those records are shown.
   - **Parameters**:
     - `index` (int, optional): Specific index of a record to view.
     - `end_index` (int, optional): End index for viewing multiple records in a range.
   - **Example**: `view_record(index=1)` or `view_record(index=1, end_index=5)`
---
## search_records
---
### `search_records(subject_name=None, date=None)`
   - **Description**: Searches for records by subject name or date.
   - **Parameters**:
     - `subject_name` (str, optional): The name of the subject to search for.
     - `date` (str, optional): The date to search for in "day-month-year" format.
   - **Example**: `search_records(subject_name="Alice")`
---
## clear_records
---
### `clear_records(index=None)`
   - **Description**: Clears records in the JSON file. If an index is provided, only that record is removed. If no index is provided, all records are cleared.
   - **Parameters**:
     - `index` (int, optional): The index of the record to delete. If `None`, all records are cleared.
   - **Example**: `clear_records(index=1)`

---
## stats
---
### `stats(subject_name=None, subject_list=None, date=None, date_range=None, index_range=None)`
   - **Description**: Calculates and returns comprehensive statistics for reaction times. Allows filtering by subject, list of subjects, a specific date, a range of dates, or a range of indices. Statistics include:
     - **Count**: Total number of reaction times.
     - **Average Reaction Time**: The mean reaction time.
     - **Minimum Reaction Time**: The shortest recorded time.
     - **Maximum Reaction Time**: The longest recorded time.
     - **Median Reaction Time**: The middle value in the dataset.
     - **Standard Deviation**: A measure of the spread of reaction times.
     - **Range**: The difference between the maximum and minimum times.
     - **Interquartile Range (IQR)**: Spread of the middle 50% of reaction times.
     - **25th Percentile (Q1)**: The point below which 25% of reaction times fall.
     - **75th Percentile (Q3)**: The point below which 75% of reaction times fall.
     - **Mode**: The most frequently occurring reaction time, if any.
     - **Variance**: The square of the standard deviation, indicating variability.
   - **Parameters**:
     - `subject_name` (str, optional): Filter by a single subject's name.
     - `subject_list` (list, optional): Filter by a list of subject names.
     - `date` (str, optional): Specific date (format: "day-month-year") to filter by.
     - `date_range` (tuple, optional): Tuple with start and end dates (format: "day-month-year") to filter by.
     - `index_range` (tuple, optional): Tuple containing start and end indices to filter by.
   - **Examples**:
     - Overall statistics: `stats()`
     - For a single subject: `stats(subject_name="Alice")`
     - For multiple subjects: `stats(subject_list=["Alice", "Bob"])`
     - For a specific date: `stats(date="08-11-2024")`
     - For a range of dates: `stats(date_range=("08-11-2024", "10-11-2024"))`
     - For a range of indices: `stats(index_range=(1, 5))`
---
## pretty_stats
---
### `pretty_stats(subject_name=None, subject_list=None, date=None, date_range=None, index_range=None)`
   - **Description**: Calls `stats()` and formats the results in a readable output, displaying all computed statistics.
   - **Parameters**:
     - `subject_name` (str, optional): Filter by a single subject's name.
     - `subject_list` (list, optional): Filter by a list of subject names.
     - `date` (str, optional): Specific date (format: "day-month-year") to filter by.
     - `date_range` (tuple, optional): Tuple with start and end dates (format: "day-month-year") to filter by.
     - `index_range` (tuple, optional): Tuple containing start and end indices to filter by.
   - **Example**: `pretty_stats(subject_name="Alice")`
---
## record_ruler_drop
---
### `record_ruler_drop(subject_name, distance_in_inches)`
   - **Description**: Records the reaction time for a subject, including their name, date, distance, and reaction time, in a JSON file.
   - **Parameters**:
     - `subject_name` (str): Name of the subject.
     - `distance_in_inches` (float): Distance the ruler fell in inches.
   - **Example**: `record_ruler_drop("Alice", 7)`
---


