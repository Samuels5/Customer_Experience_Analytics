# Customer Experience Analytics for Fintech Apps

## Overview

This project analyzes customer satisfaction with mobile banking apps by collecting and processing user reviews from the Google Play Store for three Ethiopian banks:

- Commercial Bank of Ethiopia (CBE)
- Bank of Abyssinia (BOA)
- Dashen Bank

## Task 1: Data Collection and Preprocessing

### Tools & Libraries

- **google-play-scraper**: For scraping Google Play Store reviews
- **pandas**: For data manipulation and cleaning

### Methodology

1. **Scraping**: Reviews were collected for each bank's app using their official package names. The script targets at least 400 reviews per bank.
2. **Preprocessing**:
   - Removed duplicate reviews (by review text and bank)
   - Dropped rows with missing review, rating, date, or bank
   - Normalized date format to YYYY-MM-DD
   - Selected the first 400 reviews per bank for a balanced dataset
3. **Output**: Cleaned data is saved as `reviews_cleaned.csv` with columns: `review`, `rating`, `date`, `bank`, `source`.

### File Outputs

- `scrape_reviews.ipynb`: Jupyter notebook for scraping and preprocessing
- `reviews_cleaned.csv`: Cleaned dataset ready for analysis

### Issues & Notes

- Package names were verified for accuracy.
- If no reviews were returned, different language/country codes were tested.
- All code and data are committed to the `task-1` branch with clear commit messages.

## Task 2: Sentiment and Thematic Analysis

### Tools & Libraries

- **vaderSentiment**: For sentiment analysis
- **scikit-learn**: For TF-IDF keyword extraction
- **matplotlib**, **seaborn**: For visualization

### Methodology

1. **Sentiment Analysis**: Used VADER to compute sentiment scores and labels (positive, negative, neutral) for each review.
2. **Thematic Analysis**:
   - Extracted top keywords per bank using TF-IDF.
   - Grouped keywords into themes using rule-based matching (e.g., 'Account Access Issues', 'Transaction Performance', etc.).
3. **Insights**:
   - Identified top satisfaction drivers and pain points for each bank.
   - Generated visualizations for sentiment and theme distributions.
4. **Output**: Enriched data saved as `reviews_with_sentiment_themes.csv`.

### File Outputs

- `reviews_with_sentiment_themes.csv`: Dataset with sentiment and theme annotations
- Visualizations: Sentiment and theme distribution plots

## Task 3: Store Cleaned Data in Oracle

### Tools & Libraries

- **oracledb**: Python driver for Oracle Database

### Methodology

1. **Schema Design**:
   - Created `Banks` and `Reviews` tables in Oracle XE.
2. **Data Insertion**:
   - Inserted unique banks and all reviews (with sentiment and theme) into the database.
3. **Notes**:
   - Provided fallback instructions for PostgreSQL if Oracle XE is unavailable.
   - Included error handling and credential placeholders in the notebook.

### File Outputs

- Oracle database tables populated with cleaned and enriched review data
- (Optional) SQL dump for backup or migration

## Next Steps

- Task 4: Insights, visualization, and reporting
- Update documentation and finalize the project report

---

For more details, see the notebook and scripts in this repository.
