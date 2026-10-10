# Amazon Product Recommendation System

A content-based recommendation engine built with Natural Language Processing (NLP) to recommend similar women's apparel based on product titles and metadata.

---

## 📌 Project Overview
E-commerce catalogs often contain missing attributes and duplicate listings differing only by size or color. This project processes raw, unstructured Amazon product data, cleans and deduplicates the catalog, and implements vector-based similarity algorithms to retrieve relevant product recommendations.

---

## 📊 Data Pipeline & Funnel (EDA)
- **Raw Data Ingestion:** 183,138 raw products with 19 attributes.
- **Feature Selection:** Filtered down to 7 key features (`asin`, `brand`, `color`, `product_type_name`, `medium_image_url`, `title`, `formatted_price`).
- **Null Value Handling:** Discarded records missing essential values like price and color, bringing data to ~28,000 points.
- **Deduplication:**
  - Stage 1: Removed identical adjacent products differing only by trailing words (e.g., sizes S/M/L) -> ~17,500 products.
  - Stage 2: Applied text distance heuristics to filter non-adjacent near-duplicates -> final clean dataset of ~16,000 products.

---

## ⚙️ NLP & Recommendation Models
1. **Text Preprocessing:**
   - Lowercasing, punctuation removal, tokenization, and stopword removal via NLTK.
2. **Vectorization:**
   - **Bag of Words (CountVectorizer):** Unweighted term frequency representation.
   - **TF-IDF (TfidfVectorizer):** Term frequency weighted by inverse document frequency to highlight unique fashion attributes.
3. **Similarity Engine:**
   - Evaluated cosine and pairwise distance metrics to compute nearest neighbors for any query product title.

---

## 🛠️ Tech Stack
- **Language:** Python
- **Data & Text Analysis:** Pandas, NumPy, Scikit-learn, NLTK
- **Visualization:** Matplotlib, Seaborn, Plotly

---

## 📂 Repository Structure
```text
amazon-recommendation-system/
├── amazon_recommendation.ipynb   # Complete data cleaning, EDA, and model pipeline
├── requirements.txt              # Project dependencies
├── .gitignore                    # Excludes heavy datasets and cache
└── README.md                     # Documentation
```

---

## 🚀 How to Run
1. Clone repository:
   ```bash
   git clone https://github.com/<your-username>/amazon-recommendation-system.git
   cd amazon-recommendation-system
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Open `amazon_recommendation.ipynb` in Jupyter Notebook or VS Code to explore the pipeline.