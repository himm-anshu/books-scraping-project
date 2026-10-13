# 📚 Book Market Analysis: Web Scraping, Data Cleaning & Visualization

## 📌 Project Overview

This project uses web scraping and data analysis to explore book listings from [Books to Scrape](https://books.toscrape.com/), a website designed for practicing web scraping.

Using Python, Selenium, BeautifulSoup, Pandas, and Plotly Express, I collected book information, cleaned the dataset, answered business questions, and created interactive visualizations to explore book prices, ratings, and category distributions.

**Project workflow:** Web Scraping → Data Cleaning → Exploratory Data Analysis (EDA) → Data Visualization → Insights

## 🎯 Business Questions

This project aims to answer the following questions:

1. Which categories contain the most books?
2. Which categories have the highest and lowest average book prices?
3. Is there a relationship between book prices and star ratings?
4. How are books distributed across budget, mid-range, and premium price bands?

## 🛠️ Tools & Technologies

- **Python** — Core programming language
- **Selenium** — Browser automation and webpage navigation
- **BeautifulSoup** — HTML parsing and data extraction
- **Pandas** — Data cleaning, transformation, aggregation, and analysis
- **Plotly Express** — Interactive charts and visualizations
- **SciPy** — Optional statistical hypothesis testing
- **Jupyter Notebook** — Development and documentation

## 📊 Dataset Overview

The data was scraped from Books to Scrape, a practice website intended for learning web scraping.

The original dataset contains **1,000 book records and 5 columns**:

| Column | Description |
|---|---|
| `title` | Title of the book |
| `category` | Book category |
| `price` | Listed price in pounds sterling (£) |
| `rating` | Book rating, initially represented as words |
| `availability` | Availability status of the book |

The cleaned dataset includes a derived `price_band` column for classifying books into price ranges.

**Important:** The website's prices and ratings are practice data, not real-world market information. The project demonstrates an analytical workflow rather than actual market research.

## 🔎 Project Workflow

### 1. Web Scraping

Used Selenium to open the website in a headless Chrome browser and BeautifulSoup to parse the HTML.

The scraping process:

- Extracted book category names and their links.
- Navigated through category pages and pagination.
- Collected book titles, categories, prices, ratings, and availability.
- Saved the scraped dataset as `books_raw.csv` to avoid unnecessary repeated scraping.

### 2. Data Cleaning & Preparation

Used Pandas to prepare the data for analysis.

- Inspected dataset dimensions, column data types, and missing values.
- Checked for duplicate records.
- Removed currency symbols and converted prices into numeric values.
- Converted text-based ratings (`One` to `Five`) into numeric ratings from 1 to 5.
- Removed leading and trailing whitespace from text columns.
- Checked availability values and removed the column because all 1,000 records had the same status.
- Created a `price_band` column to group books into budget, mid-range, and premium categories.
- Applied validation checks to confirm that prices were positive, ratings were within the expected range, and duplicate records were absent.

The cleaned dataset was saved as `books_clean.csv`.

### 3. Exploratory Data Analysis (EDA)

Used Pandas `groupby()`, `agg()`, `value_counts()`, and descriptive statistics to investigate:

- Book counts by category.
- Average book prices by category.
- Average and median prices by rating.
- Price distribution across the dataset.
- Proportions of books in different price bands.
- Correlation between price and rating.

Categories with at least 10 books were used for category-level price comparisons to reduce the influence of very small groups.

### 4. Statistical Testing

An optional Welch's independent two-sample t-test was performed to compare the average prices of five-star books against books rated one or two stars.

The test used a significance threshold of 0.05.

### 5. Interactive Data Visualization

Created six interactive charts using Plotly Express:

1. **Top 10 Categories by Book Count** — compares the number of books across categories.
2. **Average Book Price by Category** — compares average prices for categories containing at least 10 books.
3. **Distribution of Book Prices** — displays the overall price distribution.
4. **Book Price by Star Rating** — uses a box plot to compare price distributions across ratings.
5. **Category Price vs. Rating** — uses a bubble chart to compare average price and rating, with bubble size representing the number of books.
6. **Share of Books by Price Band** — displays the proportion of books in each price range.

## 📈 Key Findings

Based on the current analysis output:

- **Overall average price:** £35.07 across 1,000 books.
- **Price and rating relationship:** The Pearson correlation coefficient is 0.028, indicating virtually no linear relationship between price and rating in this dataset.
- **Price distribution:** 19.6% of books fall into the budget band, 40.1% into the mid-range band, and 40.3% into the premium band.
- **Statistical test:** The average price of five-star books is £35.37, compared with £34.68 for books rated one or two stars. The Welch's t-test returned a p-value of 0.582, so the difference was not statistically significant at the 0.05 level.

These findings describe the current scraped dataset only. Category-level findings should be interpreted after validating the category extraction.

## 📁 Project Structure

```text
book-market-analysis/
│
├── book_market_analysis.ipynb   # Scraping, cleaning, analysis and charts
├── books_raw.csv                # Raw scraped dataset (generated)
├── books_clean.csv              # Cleaned dataset (generated)
├── requirements.txt             # Python dependencies
└── README.md                    # Project documentation
```

The CSV files are generated by the notebook and may be excluded from version control if you prefer to keep the repository lightweight.

## ⚙️ Installation & Setup

### Prerequisites

- Python installed
- Google Chrome installed
- Jupyter Notebook or JupyterLab
- An internet connection for the initial scrape

### Step 1: Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
cd YOUR-REPOSITORY
```

Replace the example GitHub URL with your actual repository URL.

### Step 2: Install dependencies

```bash
pip install -r requirements.txt
```

### Step 3: Launch Jupyter Notebook

```bash
jupyter notebook
```

Open `book_market_analysis.ipynb` and run the cells from top to bottom.

**Note:** Selenium uses Chrome in headless mode by default. The initial scraping process may take a few minutes. If `books_raw.csv` already exists, the notebook loads that file instead of scraping the website again. Delete the file if you want to collect fresh data.

## 🚀 Future Improvements

- Validate category extraction and improve scraping reliability.
- Add automated error handling and retry logic.
- Collect additional attributes such as product URLs and book descriptions.
- Build a dashboard in Power BI or Tableau using the cleaned dataset.
- Apply the same workflow to real-world websites that permit automated data collection.
- Add more statistical analysis and comparisons where appropriate.

## ⚠️ Limitations

- Books to Scrape is a practice website; its prices and ratings should not be interpreted as real market data.
- The dataset contains only five original fields.
- Category-level comparisons may be affected by scraping or categorization errors.
- The analysis is descriptive and does not establish causation.

## 👨‍💻 Author

**Himanshu**

Aspiring Data Analyst | Python | SQL | Power BI | Tableau | Data Cleaning | Exploratory Data Analysis

