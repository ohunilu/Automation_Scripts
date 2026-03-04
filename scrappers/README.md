# BrochureBot 1.2 - The Web-to-PDF Archivist

[![Python](https://img.shields.io/badge/Made%20with-Python%203-1f425f.svg)](https://www.python.org/)
[![Scrapy](https://img.shields.io/badge/Built%20with-Scrapy%20Framework-639b0c.svg)](https://scrapy.org/)

## The Genesis of the Idea!

**DataExtractBot** was built to automate the extraction of data from websites. More specifically, this project serves as an example of leveraging powerful open-source libraries to crawl e-commerce platforms and securely extract, process, and save product data. 

Right now, it's configured to scrape the dummy site `books.toscrape.com`, extracting book titles, prices, and ratings.

## How DataExtractBot Works Its Magic

### Intelligent Website Detection
DataExtractBot leverages **Scrapy**, a fast, high-level web crawling framework, to navigate through paginated listings. It intelligently identifies book items and their attributes directly from the HTML using CSS selectors.

### Data Processing and Export
The extracted data is passed through a Scrapy Item Pipeline (`ExportPipe`). This pipeline accumulates the scraped items and, upon completion, converts them into a powerful **Pandas** DataFrame. The DataFrame is then exported to a highly efficient Parquet file format using `pyarrow` and `fastavro`, ensuring the data is compactly stored and ready for analytics.

### The Complete Workflow
1. The user executes the `runner.py` script.
2. The script configures and launches a Scrapy `CrawlerProcess`.
3. The `CrawlSpider` navigates the target URL, yielding book data and following pagination links.
4. The yielded items are collected by the `ExportPipe` pipeline.
5. Once scraping is complete, the collected data is exported to `extract_data.parquet`.

## Unleashing the Bot: Your Quick Start Guide

### Prerequisites
Make sure you have Python 3 installed. Crate a python environment venv and activate it

```bash
python3 -m venv venv
source venv/bin/activate
```

You will also need to install the project dependencies.

```bash
pip install -r requirements.txt
```

## Running the Script

Kick off the scraping process by navigating to the main project folder and executing the runner script:

```bash
python3 -m scrappers.runner
```

You'll see a terminal spinner showing the progress, and a `scraper.log` file will be generated with detailed execution logs.


## Packages Documentation

The following packages are used in this project:
- [Scrapy](https://docs.scrapy.org/en/latest/) - A fast high-level web crawling and web scraping framework.
- [Pandas](https://pandas.pydata.org/docs/) - Data manipulation and analysis library.
- [Fastavro](https://fastavro.readthedocs.io/en/latest/) - Fast Avro for Python.
- [PyArrow](https://arrow.apache.org/docs/python/) - Python library for Apache Arrow.
- [Halo](https://github.com/ManrajGrover/halo) - Beautiful terminal spinners in Python.

## ⚠️ Important Disclaimer & Ethical Use ⚠️

**Please use it responsibly.** The goal is to demonstrate how automation can save hours of manual browsing for **personal, educational review**, not to infringe on the rights of content creators. Always respect website terms of service.

---
