# 📊 Indian IPO Event Study: Testing Market Efficiency (2021-2024)

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Latest-green.svg)](https://pandas.pydata.org/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

> A comprehensive quantitative analysis of 40 Indian IPOs to test market efficiency and debunk common investment myths using statistical hypothesis testing.

**Author:** Eshita Sarawgi | CFA Level 2 Candidate  
**Analysis Period:** January 2021 - December 2024  
**Sample Size:** 40 IPOs (NSE/BSE)

---

## 🎯 Project Overview

This project investigates **three popular beliefs** in the Indian IPO market using rigorous statistical analysis:

1. **Do high-subscription IPOs consistently show first-day pops (gains)?**
2. **Does listing-day premium sustain over a 30-day window?**
3. **Are retail-heavy IPOs more volatile post-listing?**

**Spoiler Alert:** All three hypotheses were **REJECTED** (p > 0.05), suggesting the IPO market is more efficient than commonly believed.

---

## 🔍 Key Findings

| Hypothesis | Popular Belief | Reality | Statistical Result |
|-----------|---------------|---------|-------------------|
| **A** | High subscription = Guaranteed gains | No correlation found | p = 0.7477 ❌ |
| **B** | Listing premiums sustain for 30 days | Classic "pop and drop" pattern | p = 0.3589 ❌ |
| **C** | Retail-heavy IPOs are more volatile | No significant difference | p = 0.2105 ❌ |

### 💡 What This Means
- **Simple signals don't work:** Subscription levels and investor mix don't predict returns
- **Market efficiency:** Publicly available information is already priced in
- **IPO investing requires deeper analysis:** Fundamentals matter more than hype

---

## 📂 Project Structure

```
IPO-Event-Study/
│
├── Notebooks/
│   ├── Notebook_01_Data_Cleaning.ipynb                     # Importing, Cleaning and Processing of Sample Data    
│   ├── Notebook_02_Event_Study_Returns.ipynb               # Relevant Calculation    
│   ├── Notebook_03_Hypothesis_Testing.ipynb                # Pipeline Hypotheses and Relevant Calculations
│   ├── Notebook_04_Dataloader_And_Builder.ipynb            # Loading Mainboard IPO Data & NIFTY Data & Processing
│   ├── Notebook_05_Enriched_Hypotheses.ipynb               # Statistical Testing of the target hypotheses    
│   ├── Notebook_06_Visuals_And_Dashboards.ipynb            # Professional charts & dashboards
│   └── Notebook_07_OutputReport_And_Summary.ipynb          # Executive summary & conclusions
│
├── IPO_Meta/
│   ├── ipo_metadata_enriched.csv               # IPO metadata (subscription, retail%)
│   ├── df_pooled_master.csv                    # Aggregated returns & volatility
│   ├── df_final_for_viz.csv                    # Final merged dataset
│   └── final_report_summary.csv                # Hypothesis test results
│
├── visualizations/
│   ├── hypothesis_a_analysis.png               # Subscription vs Returns
│   ├── hypothesis_b_analysis.png               # Premium Sustainability
│   └── hypothesis_c_analysis.png               # Volatility Analysis
│
├── requirements.txt                             # Python dependencies
├── README.md                                    # This file
└── LICENSE                                      # MIT License

```

---

## 🛠️ Technologies & Tools

**Programming & Data Analysis:**
- Python 3.8+
- Pandas (Data manipulation)
- NumPy (Numerical computing)
- SciPy (Statistical testing)

**Data Collection:**
- Yahoo Finance API (yfinance)
- Web scraping (BeautifulSoup/Selenium)
- Manual data collection from public sources

**Visualization:**
- Matplotlib (Charts)
- Seaborn (Statistical plots)

**Statistical Methods:**
- Two-sample t-tests (Welch's test)
- Paired t-tests
- Mann-Whitney U test
- Levene's test for variance equality
- Cohen's d (Effect size calculation)

---

## 📊 Methodology

### Data Collection
- **40 IPOs** from NSE/BSE (equal split: 20 high-subscription, 20 low-subscription)
- **Daily price data** scraped via Yahoo Finance
- **Metadata collected:** Subscription levels, retail participation %, issue size, sector

### Key Metrics Calculated
- **First-Day Return:** `(Listing Price - Issue Price) / Issue Price`
- **30-Day CAR (Cumulative Abnormal Return):** Market-adjusted returns over 30 trading days
- **30-Day Volatility:** Standard deviation of daily returns post-listing

### Statistical Testing
- **Significance Level:** α = 0.05 (95% confidence)
- **Tests Used:** t-tests, Mann-Whitney U, Levene's test
- **Effect Sizes:** Cohen's d to measure practical significance

---

## 📈 Detailed Results

### Hypothesis A: High-Subscription → First-Day Pops
**Popular Belief:** "If an IPO is heavily oversubscribed, it will definitely list at a premium"

**Results:**
- High-Subscription IPOs: Mean return = 0.72%
- Low-Subscription IPOs: Mean return = 1.43%
- **p-value = 0.7477** (NOT SIGNIFICANT)
- **Conclusion:** ❌ Subscription levels do NOT predict first-day returns

**Why?** Market already prices in demand; issue pricing may be aggressive when demand is high.

---

### Hypothesis B: Listing Premium Sustains 30 Days
**Popular Belief:** "If an IPO lists at a premium, the momentum continues for at least a month"

**Results:**
- Mean First-Day Return: 5.98%
- Mean 30-Day CAR: 3.15%
- Mean Premium Decay: 2.82%
- **p-value = 0.3589** (NOT SIGNIFICANT)
- **Conclusion:** ❌ IPO premiums do NOT sustain; classic "pop and drop"

**Why?** Mean reversion, profit booking, lack of fundamental support for elevated valuations.

---

### Hypothesis C: Retail-Heavy IPOs → Higher Volatility
**Popular Belief:** "IPOs with high retail participation are more volatile due to emotional trading"

**Results:**
- Retail-Heavy IPOs: Mean volatility = 4.72%
- Institutional-Heavy IPOs: Mean volatility = 4.07%
- Mean Difference: +0.64%
- **p-value = 0.2105** (NOT SIGNIFICANT)
- **Conclusion:** ❌ Investor composition does NOT significantly affect volatility

**Why?** Both retail and institutional investors trade actively; SEBI regulations dampen extremes.

---

## 🚀 How to Run This Project

### Prerequisites
```bash
Python 3.8 or higher
pip (Python package manager)
```

### Installation

1. **Clone the repository:**
```bash
git clone https://github.com/[YourUsername]/IPO-Event-Study.git
cd IPO-Event-Study
```

2. **Install dependencies:**
```bash
pip install -r requirements.txt
```

3. **Run the notebooks in order:**
```bash
jupyter notebook
```
Open and execute notebooks sequentially: `Notebook_01` → `Notebook_07`

### Required Libraries
```
pandas>=1.5.0
numpy>=1.23.0
matplotlib>=3.5.0
seaborn>=0.12.0
scipy>=1.9.0
yfinance>=0.2.0
beautifulsoup4>=4.11.0
requests>=2.28.0
```

---

## 📸 Visualizations

### Hypothesis A: Subscription vs First-Day Returns
![Hypothesis A](visualizations/hypothesis_a_analysis.png)
*Box plots and distribution analysis showing NO significant difference between high and low subscription IPOs.*

### Hypothesis B: Premium Sustainability
![Hypothesis B](visualizations/hypothesis_b_analysis.png)
*Scatter plot demonstrating the "pop and drop" pattern - premiums decay within 30 days.*

### Hypothesis C: Volatility by Investor Composition
![Hypothesis C](visualizations/hypothesis_c_analysis.png)
*Comparative analysis showing similar volatility across retail-heavy and institutional-heavy IPOs.*

---

## 💼 Practical Investment Guidelines

### ✅ DO:
- Focus on company fundamentals, not subscription hype
- Analyze issue pricing relative to peers and growth prospects
- Consider booking profits on listing day if premium > 15-20%
- For long-term holdings, wait 2-4 weeks post-listing for better entry

### ❌ DON'T:
- Chase IPOs solely based on high oversubscription numbers
- Buy at listing premium expecting short-term momentum
- Assume high retail participation means higher risk
- Ignore valuation just because "everyone is applying"

---

## 📚 Limitations & Future Work

### Limitations
- Sample size: 40 IPOs (moderate for statistical tests)
- Time period includes varying market regimes (2021 bull, 2022 correction, 2023-24 recovery)
- Gray market data not included due to availability constraints
- Transaction costs not factored in

### Future Research Opportunities
- Expand to 100+ IPOs for more robust results
- Sector-specific analysis (Tech vs Manufacturing vs Finance)
- Include gray market premium as predictor variable
- Longer-term performance (90, 180, 365 days)
- Machine learning models for return prediction
- Impact of anchor investors and lock-up expiry

---

## 🤝 Contributing

Contributions are welcome! If you'd like to:
- Add more IPOs to the dataset
- Improve statistical models
- Create additional visualizations
- Fix bugs or improve documentation

Please fork the repository and submit a pull request.

---

## 📧 Contact

**Eshita Sarawgi**  
- LinkedIn: www.linkedin.com/in/eshita-sarawgi1410
- Email: esarawgi2004@gmail.com
 

**CFA Level 2 Candidate** | Passionate about quantitative finance,programmig, alpha generation and evidence-based investing

---

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- Yahoo Finance for providing historical price data
- NSE/BSE for IPO metadata
- Python data science community for excellent libraries
- CFA Institute for rigorous financial analysis training

---

## ⭐ If you found this project helpful, please consider starring the repository!

**Disclaimer:** This analysis is for educational purposes only and should not be considered investment advice. Always conduct your own research and consult with financial advisors before making investment decisions.

---

*Last Updated: [Current Date]*
