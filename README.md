# Scraping_Grants
A short exercise wherein I am scraping grants from a website as a take home assignment

Tools Used: Python, BeautifulSoup, Pandas, NLTK, Colab

<br>
## Description:
The objective of this project was to extract, clean, and analyze grant-related data from the Rf Grants page. The goal was to gather both structured (amounts, dates, categories) and unstructured (descriptions, themes) data to derive meaningful insights and visualize trends.
<br>

## 📊 Fields:
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

<br>

## 🔍 Data Collection Strategy

Base URL: As given in the assignment details page

Pagination Handling: Followed the See Next 10 button dynamically using the href inside <button class="btn_pagination">.

### Data Extracted From Listing Page:

1. Grant title

2. Awarded date

3. Grant amount

4. Description snippet

5. Link to detailed page

### Data Extracted From Detail Page:

1. Full description

2. Focus Area

3. Term (Start – End)

4. Address

<br>

## 🧼 Data Cleaning
1. Removed duplicate rows

2. Removed redundant prefixes like Awarded, Term, Description:, and Address: from respective columns.

3. Stripped HTML tags and unnecessary line breaks from text.

4. Converted Amount column from $123,456 format to numeric.

5. Extracted duration in months from the term and created a new field: Duration (Months).

<br>

## ⏳ Duration Classification
Each grant was classified as:

1. Short-term if duration < 18 months

2. Long-term if duration ≥ 18 months

👉 This cutoff was updated mid-project from 12 months to 18 months to better reflect funding cycles.

<br>

## 🧠 Unstructured Data Processing
- Used nltk to tokenize the Full Description field.

- Removed stopwords and non-alphabetic noise.

- Stored cleaned tokens in a new column for further analysis.

- Defined theme keyword buckets for Health, Climate, Equity, and Technology.

- Each grant was assigned one or more thematic tags based on keyword presence.

<br>

## 📊 Visualizations & Analysis
### Structured Data:

📌 Count of grants per Focus Area

💰 Average grant amount per Focus Area

⏳ Grant Type distribution (Short vs Long)

💼 Total grant themes across all descriptions

### Unstructured Data:

🔑 Top 20 most frequent keywords in descriptions (bar plot)

🌥 WordCloud of cleaned descriptions

📚 Thematic bar chart showing grants per dominant theme

### All visualizations were styled using Seaborn and Matplotlib, and include:

1. Clean fonts and spacing

2. Count labels on bars

3. Aesthetic palettes

4. No future warnings
