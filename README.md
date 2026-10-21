# Airbnb Calendar Data Cleaning with Pandas

A beginner-friendly data cleaning and exploratory analysis project using Python and Pandas on Airbnb calendar data.

## Dataset

The source calendar CSV contains listing IDs, dates, availability, and prices. The original file is not included in this repository because it is a large local dataset. Download your permitted copy and place it at `data/calendar.csv`, or upload it when running the notebook in Google Colab.

Expected columns:
- `listing_id`
- `date`
- `available` (source values such as `t` / `f`)
- `price` (may be blank for unavailable dates)

## Run in Google Colab

1. Open [Google Colab](https://colab.research.google.com/).
2. Choose **File → Upload notebook** and upload `Airbnb_Calendar_Data_Cleaning.ipynb` from this repository.
3. Run the notebook. If prompted, upload `calendar.csv` from your computer (a ZIP containing the CSV is also supported).
4. The notebook creates an `output/` directory containing the cleaned data and quality-analysis CSVs.

## Run locally

```bash
python -m pip install -r requirements.txt
jupyter notebook Airbnb_Calendar_Data_Cleaning.ipynb
```

Place the CSV at `data/calendar.csv` or update the notebook's input path.

## Cleaning and analysis steps

- Inspect shape, columns, types, and missing values.
- Standardize column names and remove exact duplicate rows.
- Parse dates, availability flags, and prices.
- Keep unavailable-date missing prices visible rather than assuming they are errors.
- Validate records and export rows requiring review.
- Add calendar features and summarize monthly availability.
- Flag potential price outliers using the IQR rule without automatically deleting them.
- Export cleaned data, quality summaries, review rows, and outlier candidates.

## Outputs

- `output/cleaned_calendar.csv`
- `output/calendar_rows_for_review.csv`
- `output/data_quality_summary.csv`
- `output/potential_price_outliers.csv`

## Important note

Outlier flags are for investigation, not proof that a price is incorrect. Missing prices on unavailable dates may be expected in this dataset. Always review data-quality findings before using the data for decisions.

## License

Add a license if you want to specify reuse terms for this project.
