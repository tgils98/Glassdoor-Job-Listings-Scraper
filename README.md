# GlassDoor-Job-Listings-Scraper
Scrapes job listings from GlassDoor using Selenium and ChromeDriver:

### 📦 Setup and Imports

* Imports libraries like Selenium, BeautifulSoup, Pandas, and CSV for web scraping, browser automation, and data handling.


### 🔍 Function: fetch_jobs(keyword, num_pages, location)

* Automates job scraping from Glassdoor UK, using Chrome browser:
  

### 🚀 Browser Setup

* Initializes Chrome with custom window size using webdriver.Chrome().
* Opens the Glassdoor job search page

### 🔎 Performs Job Search

* Enters the job keyword and location into search fields.
* Submits the search form to load job listings.

### 📋 Inner Helper Functions

* random_sleep(): Pauses randomly to mimic human browsing.
* click_load_more(): Clicks "Load More" to reveal more jobs on the current page.
* close_popups(): Closes login or alert pop-ups if they appear.
* scrape_page(): The main scraping logic.


### 🧹 Scraping Logic

For each job listing:
* Follows the job link.
* Closes any pop-ups.
* Clicks "Show more" to reveal full job description.
  
    Extracts:
    * Job title
    * Company name
    * Location
    * Salary
    * Up to 3 bullet-point lists from the job description
    * Additional company info (e.g. size, industry, type)


### 🔁 Pagination

* Repeats scraping across the specified number of pages.
* Tries clicking the next page button if available.
* Continues scraping new jobs until num_pages is reached or no more pages are available.

### 💾 Data Storage

* Stores all job data in a list called all_data. (❗Note: The CSV saving part is placed after the return all_data, so it never executes — needs to be moved before return to work.)
