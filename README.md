# Book Market Analysis: Web Scraping + Cleaning + Analysis + Plotly

Scrapes ~1,000 books from [books.toscrape.com](https://books.toscrape.com) (a practice site that allows scraping) with **Selenium + BeautifulSoup**, cleans the data with **pandas**, answers 4 business questions with `groupby`, and visualises the answers with **Plotly Express**.

## Questions answered
1. Which categories have the most books?
2. Which categories are the most/least expensive?
3. Do higher-rated books cost more? (correlation + optional t-test)
4. How are prices spread across budget / mid / premium bands?

## Run it
```bash
pip install -r requirements.txt      # you also need Google Chrome installed
jupyter notebook Book_Market_Analysis.ipynb
```
Run the cells top to bottom. Scraping takes a few minutes and saves `books_raw.csv`; later runs load that file.

## Cleaning steps
- Removed duplicate rows
- Converted `price` from text (`£51.77`) to a number
- Converted `rating` from words (`Three`) to numbers (3)
- Dropped a column with a single constant value
- Created a `price_band` column
- Validated with `assert` checks, then saved `books_clean.csv`

## Limitations
Practice website: prices and ratings are not real market data, so treat the findings as a demonstration of method.

## Resume bullets (fill the blanks from YOUR results)
- Scraped **[N]** book records across **[N]** categories using Selenium and BeautifulSoup, handling pagination.
- Cleaned the data in pandas (type conversion, duplicate removal, validation checks) and engineered a price-band feature.
- Analysed price, rating and category patterns with groupby and correlation; built 6 interactive Plotly charts. Found **[one finding with a number]**.
