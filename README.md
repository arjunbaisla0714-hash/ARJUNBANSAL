# OTT Review Analysis

A beginner-friendly Python command-line project for exploring OTT (streaming platform) reviews. It reads review records from a CSV file and provides summary statistics, identifies the highest-rated review, performs a simple keyword-based sentiment check, and lets you search reviews by OTT platform.

## Features

- **Overall analysis:** Displays the total number of reviews, average rating, and review counts by OTT platform and genre.
- **Highest-rated review:** Shows the review with the highest individual rating, including the show, platform, rating, and review text.
- **Sentiment analysis:** Classifies reviews as positive, negative, or neutral/mixed using a small set of keywords.
- **Platform search:** Finds and displays reviews matching a platform name entered by the user.
- **Interactive menu:** Lets you choose an analysis option or exit the program.

## Project files

The program expects the dataset CSV file to be in the same folder as the Python script.

```text
ott-review-analysis/
├── ott_review_analysis.py
└── ott_reviews_dataset.csv
```

`ott_review_analysis.py` contains the application. `ott_reviews_dataset.csv` is the input dataset and must be supplied separately.

## Requirements

- Python 3
- A CSV dataset named `ott_reviews_dataset.csv`

The project uses Python's built-in `csv` module, so no third-party Python packages are required.

## Dataset format

The program reads these column names from the CSV file:

| Column | Purpose |
|---|---|
| `Show_Name` | Name of the show or title being reviewed |
| `OTT_Platform` | Streaming platform name |
| `Rating` | Numeric review rating; the program converts this value to an integer |
| `Genre` | Genre of the show |
| `Review` | Written review text used for display and keyword sentiment checking |

Make sure the CSV header uses these exact column names. Ratings should contain valid whole-number values.

## Setup and run

1. Install Python 3 if it is not already installed.
2. Place `ott_review_analysis.py` and `ott_reviews_dataset.csv` in the same directory.
3. Open a terminal or command prompt in that directory.
4. Run:

   ```bash
   python ott_review_analysis.py
   ```

   On some systems, use:

   ```bash
   python3 ott_review_analysis.py
   ```

5. Select an option from the menu by entering a number from `1` to `5`.

## Menu options

| Option | Action |
|---|---|
| `1` | Show overall analysis |
| `2` | Show the highest-rated review |
| `3` | Analyze review sentiment |
| `4` | Search reviews by OTT platform |
| `5` | Exit the program |

For the platform search, enter all or part of a platform name. The search is case-insensitive.

## How sentiment analysis works

The sentiment feature checks whether each review contains any words from two predefined lists:

- **Positive keywords:** `amazing`, `brilliant`, `great`, `good`, `excellent`, `funny`, `enjoyable`, `beautiful`, `entertaining`, `interesting`
- **Negative keywords:** `boring`, `slow`, `weak`, `disappointing`, `confusing`, `stressful`, `average`, `difficult`

A review is counted as positive if it contains a positive keyword but no negative keyword, and negative if it contains a negative keyword but no positive keyword. Reviews containing both types—or neither—are counted as neutral/mixed.

**Note:** This is a basic keyword-matching approach, not advanced AI or natural-language sentiment analysis. It may miss context, sarcasm, negation, and words that are not in the lists.

## Error handling and limitations

- If `ott_reviews_dataset.csv` is missing, the program prints a message asking you to keep the CSV in the same folder.
- If the dataset contains no review records, the program reports that no review data is available and stops.
- The program expects the required columns to exist and `Rating` values to be valid integers. It does not currently validate malformed rows or unexpected rating values.

## Built with

- Python 3
- Built-in `csv` module
- Dictionaries, lists, functions, loops, and conditional statements

## Future improvements

Possible extensions include:

- Validate CSV columns and rating values before analysis.
- Add average ratings for each platform and genre.
- Allow filtering by genre or rating.
- Improve sentiment analysis with a more sophisticated natural-language method.
- Add charts and exportable analysis reports.

## License

No license is specified for this project. Add a license file if you plan to publish or distribute it and want to define reuse permissions.
