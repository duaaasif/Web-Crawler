# Web-Crawler
This project is a Python-based web crawler that fetches and extracts data from websites—including headings, paragraphs, images, and links. It supports both static and dynamic web pages using requests and Selenium. The crawler also respects robots.txt rules and stores all extracted content in a structured SQLite database

# Features

1.Page Fetching Uses HTTP GET requests to fetch HTML content from web pages.

2.Data Extraction Extracts headings (h1, h2), paragraphs, image URLs, and hyperlinks from the content.

3.Link Crawling Finds links within pages and crawls them up to the specified depth.

4.Robots.txt Handling Checks if crawling is allowed for a page before processing it.

5.JavaScript Page Rendering Uses Selenium to render and fetch content from JavaScript-heavy websites.

6.SQLite Storage Stores headings, paragraphs, links, and image URLs into structured database tables.

7.Prevents Duplicates Avoids re-crawling and re-storing previously visited links.

8.Works with Static and Dynamic Sites Automatically chooses between requests and Selenium fetching based on your preference.

9.Depth Control You can set depth = 0 for single-page crawling.

**Libraries Used requests:** used to make HTTP GET requests to fetch static web page content.
beautifulsoup4: used to parse and extract information like headings, paragraphs, links, and images from HTML.
selenium: used to render and scrape content from websites that load elements dynamically using JavaScript.
webdriver-manager: automatically downloads and manages the correct version of the Chrome WebDriver for Selenium.
sqlite3: Python's built-in library to create and interact with the SQLite database for structured data storage.

# How It Works

main.py starts the crawler and passes URL and depth
fetcher.py or selenium_fetcher.py retrieves the page based on whether use_selenium is True
extractor.py extracts required data from HTML
db.py saves that extracted data to an SQLite database
crawler.py goes through the links recursively and continues crawling if depth is greater than 0
robots_checker.py checks if the website allows crawling using robots.txt
# How to Run

Clone the repository git clone https://github.com/yourusername/smart-web-crawler.git cd smart-web-crawler
Install required libraries pip install -r requirements.txt
Run the crawler python main.py
Customize Edit url, depth, and use_selenium options in main.py as per your requirement

Sample Websites to Test
# Static websites
https://example.com https://books.toscrape.com https://quotes.toscrape.com

# JavaScript-based (use use_selenium=True)
https://webscraper.io/test-sites/e-commerce/allinone

# Notes

Set depth = 0 for scraping just one page
Set use_selenium = True to render dynamic pages
Do not crawl websites you don’t have permission to scrape
The SQLite database file is automatically created in the same directory
If database is locked, avoid running multiple instances in parallel
# Prerequisites:

Make sure Google Chrome browser is installed on your system.
ChromeDriver is required for Selenium to work. This is handled automatically by webdriver-manager, so no manual setup is needed.
