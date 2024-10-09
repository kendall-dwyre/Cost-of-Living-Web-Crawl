# Cost of Living Index Scraper and Calculator

This Python script scrapes the latest cost of living rankings by country from [Numbeo](https://www.numbeo.com/cost-of-living/rankings_by_country.jsp), processes the data, and computes a weighted cost of living index relative to the United States.

## Objective

The objective of this script is to:
1. Extract cost of living data from a live webpage.
2. Process the data to make it usable in a DataFrame.
3. Calculate a weighted cost of living index relative to the United States, allowing users to easily compare the cost of living between countries.

## Process Overview

### Step 1: Fetch the Webpage Content
We use the `requests` library to access the cost of living rankings page. If the webpage is successfully loaded (HTTP status 200), we proceed; otherwise, an error is raised.

### Step 2: Parse the HTML Content
We use `BeautifulSoup` to parse the HTML content. The relevant data is contained within a table on the page, which we locate using its HTML `id`.

### Step 3: Extract Table Data
The script extracts the table headers (e.g., country names, cost of living indices) and rows of data. Each row represents a country with its associated cost of living index and other information.

### Step 4: Store Data in a DataFrame
We store the extracted data in a pandas `DataFrame` for further processing and analysis.

### Step 5: Data Processing
Relevant columns are converted to the correct data types (such as converting the 'Cost of Living Index' column to `float`), which enables accurate calculations.

### Step 6: Calculate the Weighted Cost of Living Index
The script retrieves the cost of living index for the United States and uses this as a baseline to calculate a weighted cost of living index for each country. This index expresses the cost of living in each country as a percentage relative to the U.S.

### Step 7: Output and Save the Results
The final DataFrame, which includes the country name, original cost of living index, and the newly computed weighted index, is displayed and saved as a CSV file (`weighted_cost_of_living_rankings.csv`).

## Insights

- The `Weighted Cost of Living Index` allows for easier comparison between countries. For example, if a country has a weighted index of 80, this indicates that the cost of living in that country is 80% of the cost of living in the U.S.
- This script provides a simple way to fetch and process live data from the web and calculate meaningful insights relative to a chosen baseline (in this case, the United States).

## How to Run

1. **Install Dependencies**:
   Make sure you have the necessary Python libraries installed:

   ```bash
   pip install requests beautifulsoup4 pandas
