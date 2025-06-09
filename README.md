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

## Next Steps

- Sentiment and thematic analysis (Task 2)
- Database storage (Task 3)
- Insights, visualization, and reporting (Task 4)

---

For more details, see the notebook and scripts in this repository.
