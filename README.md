# News Crawler 2.0
News Crawler 2.0 is a Python-based automated information gathering tool. It scrapes search results and news articles based on a comprehensive list of cybersecurity keywords—such as "medical hack," "ransomware," and "vulnerability"—to build a structured database for security research and threat intelligence.
---

## 🚀 Features
* **Automated Keyword Search** : Iterates through a vast list of security terms (e.g., buffer overflow, rootkit, data breach, hospital hack) to find relevant web content.
* **Web Scraping** : Extracts links and full-text content from search engine results and targeted web pages.
* **Data Cleaning** : Processes raw text data to remove duplicates and irrelevant entries.
* **Structured Output**: Generates a labeled dataset in both .csv and .xlsx formats for easy analysis in Excel or Pandas.
* **Keyword Tagging**: Automatically flags articles based on whether they contain specific "comparison" keywords like medical, hospital, or network.

---

## 🛠️ Installation & Dependencies
To run this crawler, you will need Python 3.x and the following libraries:
```bash
pip install pandas google beautifulsoup4 xlsxwriter
```

---

## 📋 How It Works
1. **Search Phase**: The script uses the google search library to find the top results for various combinations of cybersecurity and medical keywords.

2. **Content Extraction**: Utilizing BeautifulSoup or similar request-handling logic, the tool visits the links to extract the article text.

3. **Refinement**:

    * **rty2/rty3 Processing**: The script filters the gathered links to ensure data quality.

    * **Keyword Matching**: It checks every article against a list of comp_keywords to see if they belong to specific categories (e.g., Medical Security vs. General Security).

4. **Export**: The final dataframe is saved to newsdb.csv and output.xlsx.

--- 
## 📂 Data Structure
The output file contains the following columns:

* **Links**: The URL of the scraped article.

* **Text**: The extracted body content of the news story.

* **Keywords (Multiple Columns)**: Boolean/Count flags for specific terms (e.g., 'hospital', 'FireEye', 'devices').

* **Label**: A classification label for the news entry.
---

⚙️ Configuration
You can customize the search by modifying the list_of_keywords variable at the top of the notebook:
```python
list_of_keywords = [
    'medical+vulnerable+hack', 
    'hospital+vulnerable+hack', 
    'nhs+hack', 
    'ransomware', 
    'data breach'
]
```

## ⚖️ Legal Disclaimer
This tool is intended for educational and research purposes only. Users are responsible for ensuring that their scraping activities comply with the Terms of Service of the websites being accessed and the robots.txt files of the target domains.
