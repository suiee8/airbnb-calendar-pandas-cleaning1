# Project Report: Airbnb Calendar Data Cleaning

## Objective
Clean and validate Airbnb calendar data using Pandas, while documenting data-quality issues and preserving potentially meaningful missing values.

## Source data profile
The inspected source file contained 1,393,570 rows and 4 columns: `listing_id`, `date`, `available`, and `price`. The dates ranged from 2016-01-04 to 2017-01-02, and there were 3,818 unique listing IDs.

## Initial observations
- Availability values: `t` = 934,542 rows and `f` = 459,028 rows.
- Price was missing on 459,028 rows, matching the count of unavailable dates in the source.
- No exact duplicate rows were found in the inspected source.
- The missing prices should not be blindly filled: unavailable dates may legitimately have no price.

## Method
1. Standardize field names and data types.
2. Parse calendar dates and availability into consistent types.
3. Convert price strings to numeric values after removing currency formatting.
4. Profile missing values and invalid records.
5. Derive calendar attributes for grouped analysis.
6. Flag possible price outliers using the interquartile range (IQR), without deleting them automatically.
7. Export cleaned data and diagnostic tables.

## Outputs
The notebook exports the cleaned dataset, rows needing review, a data-quality summary, and candidate price outliers under `output/`.

## Limitations
Outlier detection is heuristic. A high or low price can be legitimate, and unavailable-date missing prices may be expected. Findings should be reviewed in context before downstream use.
