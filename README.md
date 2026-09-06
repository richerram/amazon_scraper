# Amazon Deals Web Scraper

Scraper that emulates human-like behavior to do infinite scrolling and to avoid Amazon's anti-bot rules.

Built using **Playwright** for human-like browser automation and lazy-loading scrolling, and **BeautifulSoup** for rapid HTML DOM extraction.

---

## Features

- **Anti-Bot Evasion**:
  - Masked `navigator.webdriver` and browser automation flags.
  - Desktop Chrome User-Agent and realistic browser context (`sec-ch-ua`, `Accept-Language`, viewport).
  - Humanized interaction pacing: smooth scroll increments, random delays (1.2–2.5s), and occasional jitter/nudge to trigger lazy loaders naturally.
- **Deep Loading (300+ Deals)**:
  - Continuously monitors the DOM item count and scrolls until the target number of deals (default: 300) is loaded.
- **Fast Parsing with BeautifulSoup**:
  - Extracts the full page content once via `page.content()` and parses candidate cards using high-speed BeautifulSoup selectors.
- **Rich Data Fields Extracted**:
  - `asin`: Amazon Standard Identification Number
  - `title`: Product name or deal title
  - `deal_price`: Current discounted price
  - `list_price`: Original strike-through price
  - `discount`: Deal badge / percentage off (e.g. "35% off", "Limited time deal")
  - `rating`: Star rating (e.g. "4.5 out of 5 stars")
  - `reviews_count`: Total customer review count
  - `product_url`: Direct cleaned Amazon product URL
  - `image_url`: Thumbnail image source
- **Google Colab & Local Ready**:
  - Ready-to-import Jupyter Notebook (`amazon_deals_scraper.ipynb`) for Google Colab.
  - Standalone script (`amazon_scraper.py`) with CLI arguments for local or server execution.

---

## Project Structure

```
amazon_scraper/
├── amazon_deals_scraper.ipynb  # Scraper notebook
├── data_normalization.ipynb    # Data Normalization notebook
├── requirements.txt            # Python dependencies
└── README.md                   # Documentation and usage guide
```
