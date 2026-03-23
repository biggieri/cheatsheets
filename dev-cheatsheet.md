# Developer Cheat Sheet

## Mac Setup — Done Once
- `xcode-select --install` → Installs Apple's developer tools
- `brew install python` → Installs Python via Homebrew
- `brew install git` → Installs Git
- `git config --global user.name "Name"` → Sets your Git identity
- `git config --global user.email "email"` → Sets your Git email

## Starting a New Project — Every Time
- `mkdir ~/Developer/project-name` → Creates a new project folder
- `cd ~/Developer/project-name` → Navigates into the folder
- `python3 -m venv venv` → Creates a virtual environment
- `source venv/bin/activate` → Activates the virtual environment
- `echo "venv/" > .gitignore` → Creates .gitignore to exclude venv
- `git init` → Starts Git tracking in the folder

## Daily Git Workflow
- `git add .` → Stages all changed files
- `git commit -m "message"` → Saves a snapshot with a description
- `git status` → Shows what files have changed
- `git log` → Shows full commit history
- `deactivate` → Deactivates the virtual environment

## VS Code Shortcuts
- `Command + N` → New file
- `Command + S` → Save file
- `Command + Shift + X` → Open extensions
- `Command + Shift + P` → Open command palette
- `code filename` → Open a file in VS Code from terminal

## GitHub — Connecting & Pushing
- `ssh-keygen -t ed25519 -C "email"` → Creates your SSH key (once)
- `pbcopy < ~/.ssh/id_ed25519.pub` → Copies your SSH key to clipboard (once)
- `git remote add origin git@github.com:username/repo.git` → Links local project to GitHub
- `git push -u origin main` → First push to GitHub
- `git push` → Every push after the first one

## Python Libraries — Data Workflow
- `pip install pandas openpyxl jupyter` → Install core data libraries
- `pandas` → Data manipulation (like Excel but in Python)
- `openpyxl` → Read and write Excel files
- `jupyter` → Interactive notebook for running code block by block

## VS Code Extensions — Installed
- Pylance → Smarter Python suggestions
- Rainbow CSV → Color coded CSV files
- SQLTools → Write and run SQL inside VS Code

## Python Built-ins
- `print(value)` → Prints value to screen
- `len(list)` → Counts items in a list
- `range(n)` → Generates sequence 0 to n-1
- `round(number, 2)` → Rounds to 2 decimal places
- `f"{variable}"` → Inserts variable into a string
- `def name(params):` → Defines a reusable function
- `return value` → Sends value back from a function
- `for x in list:` → Loops through every item in a list
- `if x > y: else:` → Decision maker — like Excel IF()
- `None` → Represents no value — like an empty cell
- `\n` → New line character inside a string

## Loading & Inspecting Data
- `pd.read_csv("file.csv")` → Load a CSV file into a DataFrame
- `pd.DataFrame(data)` → Create a DataFrame from a list of dicts
- `df.head()` → Show first 5 rows
- `df.tail()` → Show last 5 rows
- `df.shape` → Returns (rows, columns) count
- `df.columns` → Lists all column names
- `df.dtypes` → Shows data type of each column

## Cleaning Data
- `df.isnull()` → Shows True/False for missing values
- `df.isnull().sum()` → Counts missing values per column
- `df.dropna()` → Drops all rows with missing values
- `df.dropna(subset=["col"])` → Drops rows missing a specific column
- `df["col"].fillna(0)` → Fills missing values with 0
- `df.copy()` → Makes an independent copy of the DataFrame
- `df.duplicated(subset=["col"])` → Flags duplicate rows
- `df.drop_duplicates()` → Removes duplicate rows
- `df["col"].str.title()` → Title Case — like Excel PROPER()
- `df["col"].str.lower()` → Converts text to lowercase
- `df["col"].str.upper()` → Converts text to UPPERCASE
- `df["col"].str.strip()` → Removes leading/trailing spaces

## Filtering & Sorting
- `df[df["col"] > value]` → Filter rows where condition is true
- `df[df["col"] == "value"]` → Filter rows matching exact value
- `df.sort_values("col")` → Sort ascending by column
- `df.sort_values("col", ascending=False)` → Sort descending

## Summarizing & Grouping
- `df.groupby("col").agg(...)` → Group and summarize — like a pivot table
- `df["col"].sum()` → Sum of a column
- `df["col"].mean()` → Average of a column
- `df["col"].min()` → Minimum value in a column
- `df["col"].max()` → Maximum value in a column
- `df["col"].count()` → Count of non-null values

## Merging DataFrames
- `pd.merge(df1, df2, on="col", how="inner")` → Only matching rows — INNER JOIN
- `pd.merge(..., how="left")` → All left rows — LEFT JOIN
- `pd.merge(..., how="outer")` → All rows from both — FULL OUTER JOIN
- `pd.merge(..., left_on="a", right_on="b")` → Join on differently named columns

## Exporting Data
- `df.to_excel("file.xlsx", index=False)` → Export to Excel
- `df.to_csv("file.csv", index=False)` → Export to CSV

## Advanced Pandas
- `df["col"].diff()` → Difference between each row and previous — like MoM change
- `df["col"].pct_change()` → Percentage change between each row and previous
- `df.drop_duplicates(subset=["col"])` → Remove duplicates based on specific columns
- `pd.ExcelWriter("file.xlsx", engine="openpyxl")` → Write multiple sheets to one Excel file
- `df.to_excel(writer, sheet_name="Sheet Name")` → Export DataFrame to a specific sheet
- `df["col"].nunique()` → Count of unique values in a column
- `df["col"].mean()` → Average of a column

## NumPy
- `import numpy as np` → Import NumPy library
- `np.where(condition, "if true", "if false")` → Like Excel IF() — flag values conditionally
- `np.random.seed(42)` → Set random seed for reproducibility

## Dates
- `pd.to_datetime(df["col"])` → Convert a column to datetime format
- `df["col"].dt.to_period("M")` → Extract year-month from a date column
- `datetime(2025, 1, 1)` → Create a specific date
- `timedelta(days=n)` → Add or subtract days from a date