# Scraping_Grants
A short exercise wherein I am scraping grants from a website as a take home assignment

Tools Used: Python, BeautifulSoup, Pandas, NLTK, Colab

📌 Description:
This dataset contains structured and cleaned information about grants awarded by RF, scraped across multiple pages and enriched with metadata from individual grant detail pages. The dataset includes funding amounts, durations, focus areas, and descriptive texts for each grant, as well as automated classification based on grant length.

📊 Fields:
| Column Name           | Description |
|------------------------|-------------|
| `Title`                | Name of the grant |
| `Awarded On`           | Date the grant was awarded (prefix cleaned) |
| `Amount`               | Funding amount in USD (numeric, `$` removed) |
| `Term`                 | Start and end date of the grant period |
| `Duration (Months)`    | Calculated duration of the grant in months |
| `Grant Type`           | `"Short-term"` or `"Long-term"` based on duration (cutoff: 12 months) |
| `Focus Area`           | Grant's thematic focus (e.g., Health, Opportunity) |
| `Full Description`     | Cleaned narrative about the purpose and goals of the grant |
| `Address`              | Location of the grantee organization |


🛠 Methodology:

1. Scraping Strategy:

Used BeautifulSoup to parse both the main grants listing pages and individual grant detail pages.

Pagination was handled dynamically using the “See Next 10” button and its href.

2. Structured Data Extracted:

Grant Title, Link, Amount, Award Date, Term, Focus Area, Address

3. Unstructured Data Extracted:

Full Description (cleaned of prefixes and punctuation)


🧼 Preprocessing & Cleaning:

1. Removed HTML tags and non-textual noise

2. Removed redundant prefixes (Awarded, Term, Description: etc.)

3. Cleaned amount field (removed $ and commas)

4. Extracted Duration (Months) from Term column

5. Classified grants as Short-term (< 12 months) or Long-term (>= 12 months)

