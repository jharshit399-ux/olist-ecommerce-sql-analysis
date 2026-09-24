# Olist E-Commerce SQL Analysis

SQL analysis of a real 100,000-order Brazilian e-commerce dataset (Olist) — turning raw, multi-table data into three operational business insights using SQL.

## Why I built this

I'm HackerRank SQL (Intermediate) certified, and I wanted to prove that skill on real data rather than just claim it. This is a self-directed learning project: I used SQL to answer three questions a business actually cares about — how revenue is growing, where the money comes from, and whether delivery is reliable.

## The dataset

- **Source:** Olist Brazilian E-Commerce public dataset (~100,000 orders, 2016–2018)
- **Tables used:** `orders`, `order_items`, `products`, `customers`, `cat_translation`
- **Environment:** SQLite, run in a Kaggle notebook
- Revenue = sum of item `price` (freight excluded); values in Brazilian Reais (R$).
  
## Questions & findings

**1. How has monthly revenue trended over time?**  
Revenue grew almost 8x in 18 months, from about BRL 120k (Jan 2017) to about BRL 920k per month across 2018. Growth was steady through 2017, then November 2017 was the single biggest month (about BRL 1M, roughly 1.5x the prior month), matching Black Friday and Brazil's "13th salary" season — a predictable peak a business could plan capacity around.

**2. Which product categories drive the most revenue?**  
Revenue is highly concentrated: of 71 categories, the top 5 (health & beauty, watches & gifts, bed/bath/table, sports & leisure, computers & accessories) each earn about BRL 0.9 to 1.3M, while a long tail of about 66 categories contributes very little (smallest under BRL 1,000). A handful of categories carry the business.

**3. How reliable is delivery against the promised date?**  
Orders take about 12.6 days on average to arrive, and only about 8% arrive after the estimated date, so about 92% are on time or early. Strong reliability, though it may partly reflect conservative delivery estimates rather than pure speed.

## SQL techniques used

Multi-table JOINs (2- and 3-table) · aggregation with GROUP BY (SUM, COUNT, AVG) · date handling (`strftime`, `julianday` date differences) · conditional logic with CASE · percentage calculations (handling integer division)

## Files

- [olist-analysis.ipynb](olist-analysis.ipynb) — full notebook with every query, result, and notes

---
*A self-directed SQL learning project by Harshit Joshi.*
