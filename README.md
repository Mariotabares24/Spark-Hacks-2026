# GraingeSeek Industrial Product Catalog

A simplified, Grainger-like industrial product catalog built for **SparkHacks 2026**. Users can search, compare, and build quote lists from 100+ industrial products, all in the browser using vanilla HTML, CSS, and JavaScript.

---

## My Contributions

**Mario Tabares** Frontend Development

I was responsible for building out a large portion of the frontend for this project. Here is a breakdown of what I worked on:

- **Site Structure & UI Shell:** Set up the base HTML pages, shared navigation bar, and the overall layout/structure that the rest of the app is built on top of.
- **Product Catalog & Browsing Page:** Built the product listing page including rendering products dynamically from the JSON dataset, and implemented the search bar, category/brand filters, price range slider, and sorting options (by price and name).
- **Product Comparison Feature:** Developed the comparison tool that lets users select 2 to 4 products and view them side by side in a comparison table, with key differences highlighted.
- **Landing Page:** Designed and built the home/landing page with the search entry flow so users can jump straight into finding products.
- **Data Loading Utilities:** Wrote the shared JavaScript module (`app.js`) that handles fetching the product JSON, managing cart and compare state through localStorage, and providing helper functions used across all pages.
- **Styling & Responsiveness:** Worked on the global stylesheet (`styles.css`) to make sure the site looks clean and works well on both desktop and mobile screen sizes.

---

## Features

- **Product Catalog:** Browse 169 products across 24 categories
- **Keyword Search:** Search across titles, brands, descriptions, and categories
- **Filters & Sorting:** Filter by category, brand, and price range; sort by price or name
- **Product Details:** Full specification tables with organized key-value data
- **Compare (2 to 4 products):** Side-by-side comparison table with highlighted differences
- **Quote Builder:** Add items, adjust quantities, see totals, and export as CSV
- **AI Chatbot:** Gemini-powered customer service chatbot that can answer questions about products using the dataset
- **Responsive Design:** Works on desktop and mobile
- **Accessibility:** Keyboard navigation, ARIA labels, focus states, skip navigation

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | Vanilla HTML / CSS / JavaScript |
| Backend | Node.js / Express |
| AI Chatbot | Google Gemini API |
| Data | Static JSON (preprocessed from Kaggle CSV) |
| Search & Filters | Client-side JavaScript |
| State | localStorage (cart & compare) |

## Getting Started

### 1. Clone the repo

```bash
git clone https://github.com/Himanshu-1804/Spark-Hacks-2026.git
cd Spark-Hacks-2026
```

### 2. Install dependencies

```bash
npm install
```

### 3. Set up environment variables

Create a `.env` file in the root directory and add your Gemini API key:

```
GEMINI_API_KEY=your_api_key_here
```

### 4. Run the server

```bash
npm start
```

Then open [http://localhost:3000](http://localhost:3000).

### 5. (Optional) Regenerate product data

If you update the CSV dataset, re-run the conversion script:

```bash
python3 public/scripts/convert_csv.py
```

This reads `public/grainger_data_2022_01.csv` and writes `public/data/products.json`.

## Project Structure

```
├── app.js                  # Express server + Gemini API chat endpoint
├── package.json
├── .gitignore
├── datasets/
│   └── grainger_dataset.csv   # CSV for Gemini chatbot context
├── public/
│   ├── index.html          # Home / landing page
│   ├── products.html       # Product listing (search, filter, sort)
│   ├── product.html        # Product detail page
│   ├── compare.html        # Compare products side-by-side
│   ├── cart.html           # Quote list / cart
│   ├── about.html          # About & help
│   ├── grainger_data_2022_01.csv   # Raw Kaggle CSV
│   ├── css/
│   │   └── styles.css      # Global stylesheet
│   ├── js/
│   │   ├── app.js          # Shared: data loading, cart, compare, search, UI helpers
│   │   ├── home.js         # Home page logic
│   │   ├── products.js     # Product listing logic
│   │   ├── product-detail.js   # Product detail logic
│   │   ├── compare.js      # Compare page logic
│   │   └── cart.js         # Cart / quote builder logic
│   ├── data/
│   │   └── products.json   # Preprocessed product dataset
│   └── scripts/
│       └── convert_csv.py  # CSV → JSON conversion script
└── README.md
```

## Data Source

Product data sourced from the [Kaggle Grainger Products Database (140k records)](https://www.kaggle.com/datasets/thedevastator/grainger-products-database-140k-records/data). This is a static snapshot and does not reflect real-time inventory.

> **Disclaimer:** Always verify specs and pricing before purchasing. This is a demo application.

## Team

| Member | Role |
|--------|------|
| **Mario Tabares** | Frontend (catalog UI, search/filters, comparison, landing page, styling) |
| **Himanshu Panchal** | Frontend (product details, quote builder, about page, accessibility) |
| **Anthony Valenzo** | Backend & AI Chatbot (Express server, Gemini API integration, dataset prep) |

## License

This project was built as part of SparkHacks 2026 at UIC.
