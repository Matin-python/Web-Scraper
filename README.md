# Web Scraper

A configurable web scraping project built with Python, Requests, BeautifulSoup, and Pandas. This tool extracts structured information from websites using custom CSS selectors and supports pagination, data cleaning, logging, and exporting collected data to CSV and Excel files.

## Overview

This project is designed to collect information from websites without requiring changes to the source code for every new website.

Users can provide a website URL and specify CSS selectors for the information they want to extract. The scraper then collects the matching data, processes it using Pandas, and saves the results in convenient file formats.

The project was tested using the [WebScraper.io E-commerce Demo](https://webscraper.io/test-sites/e-commerce/static), which provides sample product listings for practicing web scraping.


## Features

- **Custom Website URL:** Enter the URL of the website you want to scrape.
- **Custom CSS Selectors:** Specify selectors for product cards, titles, prices, descriptions, links, and images.
- **Pagination Support:** Automatically navigate through multiple pages using a next-page link selector.
- **Configurable Page Limit:** Choose the maximum number of pages to scrape.
- **HTTP Request Handling:** Handle request failures, HTTP errors, and connection problems.
- **Duplicate Removal:** Identify and remove duplicate records.
- **Data Cleaning:** Normalize extracted text and remove empty records.
- **Image URL Extraction:** Collect image URLs without downloading the image files.
- **Logging System:** Record scraping activities, errors, and progress in a log file.
- **CSV Export:** Save collected information as a CSV file.
- **Excel Export:** Export collected information to an Excel spreadsheet.
- **Scraping Summary:** Display the total number of pages visited and records collected.


## Technologies Used

- **Python** – Main programming language.
- **Requests** – Sending HTTP requests and retrieving website content.
- **BeautifulSoup** – Parsing HTML and extracting information using CSS selectors.
- **Pandas** – Organizing, cleaning, and processing collected data.
- **OpenPyXL** – Supporting Excel file export.
- **Logging** – Tracking scraping activities and errors.


## How It Works

The scraping process follows these steps:

1. The user enters the target website URL.
2. The user provides CSS selectors for the desired information.
3. The scraper sends an HTTP request using a Requests session.
4. BeautifulSoup parses the returned HTML content.
5. The scraper identifies matching elements using the provided CSS selectors.
6. Extracted information is stored in a list of dictionaries.
7. If pagination is enabled, the scraper follows the next-page link until the page limit is reached or no further page is available.
8. Pandas converts the collected information into a DataFrame.
9. Duplicate and empty records are removed, and text is cleaned.
10. The results are exported to CSV and Excel files.


## Installation

Clone the repository:

```bash
git clone https://github.com/Matin-python/Web-Scraper.git
```

Navigate to the project directory:

```bash
cd Web-Scraper
```

Install the required libraries:

```bash
pip install -r requirements.txt
```


## How to Run

Open the Jupyter Notebook:

```bash
jupyter notebook Web-Scraper.ipynb
```

Run the notebook cells in order.

The program will ask you to enter the following information:

| Input | Description |
|---|---|
| Website URL | The URL of the target webpage |
| Card selector | CSS selector for each item or product |
| Title selector | CSS selector for the item's title |
| Price selector | CSS selector for its price |
| Description selector | CSS selector for its description |
| Link selector | CSS selector for its link |
| Image selector | CSS selector for its image |
| Next-page selector | CSS selector for the next-page link |
| Maximum pages | Maximum number of pages to scrape |

Optional selectors can be left empty when the corresponding information is not needed.


## Example

The project was tested using the following demo website:

[WebScraper.io – E-commerce Laptops](https://webscraper.io/test-sites/e-commerce/static/computers/laptops)

Example configuration:

```python
URL = "https://webscraper.io/test-sites/e-commerce/static/computers/laptops"

card_selector = "div.thumbnail"
title_selector = "a.title"
price_selector = "h4.price"
description_selector = "p.description"
link_selector = "a.title"
image_selector = "img"
next_page_selector = "a[rel='next']"

max_pages = 3
```

The scraper extracts product titles, prices, descriptions, product links, and image URLs.


## Output Files

After a successful scraping process, the following files are generated:

| File | Description |
|---|---|
| `scraped_data.csv` | Collected data in CSV format |
| `scraped_data.xlsx` | Collected data in Excel format |
| `scraper.log` | Log file containing scraping activities and errors |

The extracted information is also displayed as a Pandas DataFrame inside the notebook.




## Limitations

- Extracted information depends on the HTML structure of the target website.
- Some websites load content dynamically using JavaScript.
- Website structures and CSS classes may change over time.
- Some websites restrict automated requests or require additional authentication.

## Project Structure

```text
Web-Scraper/
│
├── Web-Scraper.ipynb
├── README.md
├── LICENSE.md
└── requirements.txt
```

## Future Improvements

- Extract structured information such as titles, prices, and descriptions.
- Store extracted data in Pandas DataFrames.
- Export collected information to CSV or Excel files.
- Implement error handling for failed HTTP requests.
- Support more flexible data extraction and filtering.


## Contributing

Contributions are welcome.

You can improve the feature engineering, add new classification algorithms, improve the evaluation process, or add additional visualizations to the project.


## License

This project is licensed under the **MIT License**.

See the `LICENSE` file for more information.


## Author

**Mohammad Reza Bakhshandeh**

Electrical Engineering (Electronics) Graduate

Interested in Python Development, Machine Learning, Computer Vision, Artificial Intelligence, and Data Science.
