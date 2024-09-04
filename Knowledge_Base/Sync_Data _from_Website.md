# Sync Data from Website

This document primarily introduces how to scrape data from a web page, parse it into Markdown, and import it into the Dify knowledge base.

Dify's knowledge base supports web scraping and parsing into Markdown for import through integration with Firecrawl.

[Firecrawl](https://www.firecrawl.dev/) is an open-source web parsing tool that converts web pages into clean Markdown format text that LLMs easily recognize. It also provides an easy-to-use API service.

## How to Configure

### 1. Configure Firecrawl API credentials

First, you need to configure Firecrawl credentials in the **Data Source** section of the **Settings** page.

![configure_firecrawl_1](/Knowledge_Base/images/configure_firecrawl_1.png) 

Log in to the [Firecrawl website](https://www.firecrawl.dev/) to complete registration, get your API Key, and then enter and save it in Dify.

![configure_firecrawl_2](/Knowledge_Base/images/configure_firecrawl_2.png) 

### 2. Scrape target webpage 

On the knowledge base creation page, select **Sync from website** and enter the URL to be scraped.

![web_scrape_config](/Knowledge_Base/images/web_scrape_config.png) 

The configuration options include: Whether to crawl sub-pages, Page crawling limit, Page scraping max depth, Excluded paths, Include only paths, and Content extraction scope. After completing the configuration, click **Run** to preview the parsed pages. 


![web_scrape](/Knowledge_Base/images/web_scrape.png) 

### 3. Review import results

After importing the parsed text from the webpage, it is stored in the knowledge base documents. View the import results and click **Add URL** to continue importing new web pages.

![web_scrape_result](/Knowledge_Base/images/web_scrape_result.png)