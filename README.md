# Exploring Airbnb Market Trends

An exploratory analysis of New York City Airbnb listings using Python and pandas. The project cleans three data files in different formats and answers a few basic questions about prices, room types, and review dates.

## Problem

A real estate company wants to enter the short-term rental market and needs a quick overview of the Airbnb market in New York City.

## Data

Three files in different formats:

| File | Format | Contents |
|---|---|---|
| `airbnb_price.csv` | CSV | Nightly price and neighborhood |
| `airbnb_room_type.xlsx` | Excel | Listing description and room type |
| `airbnb_last_review.tsv` | TSV | Host name and date of last review |

Source: DataCamp project "Exploring Airbnb Market Trends". The data files are not included in this repository.

## Questions

1. What are the dates of the earliest and most recent reviews?
2. How many listings are private rooms?
3. What is the average listing price per night?

## Approach

- Loaded the three files using `read_csv`, `read_excel`, and `read_csv` with a tab separator.
- **Price:** removed the word "dollars" and converted the column to a numeric type.
- **Room type:** converted values to lowercase so that variants like "Private room" and "private room" are counted as one category.
- **Description:** filled missing values with "No Description".
- **Last review:** converted the column to datetime.
- Stored the results in a dictionary and converted it to a single DataFrame.

## Results

| Metric | Value |
|---|---|
| First review date | 2019-01-01 |
| Last review date | 2019-07-09 |
| Number of private rooms | 11356 |
| Average price per night | 141.78$ |

## Limitations

- The analysis is descriptive only and does not explain why the values are what they are.
- The average is sensitive to outliers, and I did not check for them. The median would be a useful addition.
- The three tables were not merged, so there is no analysis of price by room type.
- A recent last-review date does not necessarily mean a listing is still active.

## How to Run

```bash
pip install -r requirements.txt
jupyter notebook notebook.ipynb
```

Place the data files in a `data/` folder before running.