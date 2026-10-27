# Digital Payments Market Prioritization

**Where should a digital payments app investigate a potential pilot?**

A Python analysis of the World Bank **Global Findex Database 2025** (2024 survey data) that screens lower- and middle-income markets for a possible digital payments pilot. The goal is to find countries where access to the internet and financial accounts is relatively widespread but reported digital merchant-payment use remains lower than in comparable markets.

## Key finding

**Investigate Ecuador first, while keeping Bolivia as an alternative.** Ecuador's reported digital merchant-payment use in 2024 was **20.8% of adults**, compared with **26.0% in Paraguay** and **27.6% in the Dominican Republic**, two regional comparison markets. This is a recommendation to *conduct feasibility research*, not a claim that Ecuador is the best country for a commercial launch.

## What the notebook does

- Cleans and filters World Bank Global Findex survey aggregates to comparable 2024 country-level observations.
- Explores variation in internet use, account ownership, and reported digital merchant payments.
- Uses **standardized internet access and account ownership** with **K-means clustering** to define exploratory peer groups.
- Ranks candidate countries by the gap between their merchant-payment usage and the median for their peer group, subject to access and population screens.
- Compares Ecuador with Paraguay and the Dominican Republic, including 2021–2024 trends and differences by income and gender.
- Tests sensitivity to different account-ownership screening thresholds and **2, 3, or 4** K-means peer groups.
- Recommends what to investigate before any pilot decision.

## Repository contents

- [`digital_payments_market_analysis.ipynb`](digital_payments_market_analysis.ipynb) — complete analysis and saved visualizations. **GitHub can display the notebook without running it.**
- [`requirements.txt`](requirements.txt) — Python packages used in the analysis.
- [`data/README.md`](data/README.md) — how to obtain the publicly available source CSV.

## Run locally (optional)

1. Download the **country-level CSV** from the [World Bank Global Findex 2025 download page](https://www.worldbank.org/en/publication/globalfindex/download-data).
2. Save it as `data/GlobalFindexDatabase2025.csv` (rename the downloaded file if necessary).
3. Install the packages:

   ```bash
   pip install -r requirements.txt
   ```

4. Open `digital_payments_market_analysis.ipynb` in Jupyter Notebook or another notebook environment and run the cells in order.

The source CSV is **not included** in this repository. The uploaded notebook preserves its existing outputs, so the charts and findings can still be inspected on GitHub without downloading the data.

## Interpretation and limitations

- Global Findex measures **survey responses**, not transaction volumes or product demand.
- Differences between countries or clusters do **not** establish a causal explanation for payment adoption.
- K-means clusters and the shortlist depend on the selected indicators and screening thresholds.
- Ecuador falls below a stricter **65% account-ownership threshold** and Bolivia enters the shortlist when the baseline threshold is reduced to **55%**.
- Competition, merchant acceptance, local regulation, customer-acquisition costs, and unit economics require separate research before any launch decision.

**Data source:** World Bank, *Global Findex Database 2025*, country-level data: https://www.worldbank.org/en/publication/globalfindex/download-data
