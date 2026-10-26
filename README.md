# LLM Document Analysis — SEC 8-K New Product Extraction

CAP 5619 (AI in Fintech), Assignment 2. Extracts new product announcements from SEC Form 8-K filings using an LLM (Anthropic Claude Sonnet 5.5) and saves them to CSV.

## Files
- `8k_product_extraction.ipynb` — the full pipeline (EDGAR download → preprocessing → LLM NER/extraction → CSV)
- `output/new_products.csv` — structured result: `company_name, stock_name, filing_time, new_product, product_description`
- `output/new_products_table.txt` — same data as a `|`-separated table
- `output/llm_extractions.jsonl` — raw LLM output per filing (NER entities + products)

## Results
100 S&P 500 companies scanned → 675 8-K filings downloaded → 252 product-related filings sent to the LLM → **277 new products from 28 companies**.

## Run it
```bash
pip install -r requirements.txt   # Python >= 3.10
```
Create `.env` with:
```
ANTHROPIC_API_KEY=sk-ant-...
SEC_USER_AGENT="Your Name your@email.com"
```
Then run all cells in `8k_product_extraction.ipynb`. Downloads and LLM answers are cached in `cache/`, so re-runs are fast and free.
