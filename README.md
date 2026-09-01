# Laurent Lanteigne

> **Quant**
> *Bridging high-level financial strategy with low-level systems engineering.*

Based in **Chicago, IL** (via Québec, Canada).

---

### Workflow Setup 
You can access most of [my configs here](https://github.com/lanteignel93/dot_files).  
* **Editor:** Neovim (Lua-configured, custom TUI integrations) 
* **Terminal:** Kitty + Zsh
* **Multiplexer:** TMUX
* **Environment:** Linux/Ubuntu
* **Note taking:** Obsidian 
* **Python tooling:** uv, ruff, pre-commit, pytest
* **AI leverage:** Heavy, by design. Claude Code wired into the daily workflow through a set of private repos — custom hooks, slash commands, subagents, persistent memory, an engineering journal it writes, and an Obsidian vault it reads. Runs as:
  * *Research assistant* — strategy research logs, registered-hypothesis workflows, pitch/review passes.
  * *Executive assistant* — task tracking, briefings, weekly reviews, meeting-note sync.
  * *Pair programmer* — every repo above was built in that loop.
* **Additional CLI/TUI Tools**:
  * fzf
  * scooter
  * lazygit
  * eza
  * gh

---

### Technical Stack

| Domain | Technologies |
| :--- | :--- |
| **Quant Finance** | Python (**Polars**, Pandas), **R** (Time Series), SQL, LaTeX |
| **Systems & Speed** | C++ (intermediate), Linux |
| **AI Engineering** | Multi-Agent Orchestration, LLM Integration, CI/CD Pipelines |

---

### Markets
* **Focus:** Volatility arbitrage, Mid-Frequencies strategies, and Market Microstructure.
* **Philosophy:** "Don't just analyze the data; build the engine that analyzes the data."

---

### Research & Case Studies

#### **[Trade Analysis: 1-DTE Weekend Gap](https://github.com/lanteignel93/trade_analysis_example)**
* A quantitative post-mortem of a short-duration volatility strategy. 
* Analyzes theta decay vs. gamma risk exposure, specifically focusing on the PnL variance caused by weekend gap risk.

#### **[Replication Price Sensitivity](https://github.com/lanteignel93/replication_prices)**
* Stress-testing the Black-Scholes model.
* This study quantifies the replication error (PnL leakage) that occurs when theoretical assumptions—specifically continuous hedging and log-normal distribution—are violated by real-world market conditions.
    
---

### Market Strategies
* [**Moisson — Daily Put-Ladder Skew Harvest**](https://github.com/lanteignel93/moisson_trade_public) — Sell the SPX 20Δ put ladder every day against a 50Δ straddle and a far-OTM tail strip; one scale knob, no signals, holdout-validated.
* [**Dispersion Skew Trade**](https://github.com/lanteignel93/skew_implied_corr_trade) — Short the SPX put wing, long single-name puts, vega-flat: harvesting the implied-correlation premium that lives in the index wing.
* [**Skew Trade**](https://github.com/lanteignel93/skew_trade_public) — PCA-isolated put-skew steepness (PC2) mean reversion, expressed in delta-hedged 1×2 put ratio spreads.
* [**ONE DTE Trade**](https://github.com/lanteignel93/one_dte_trade_public) — Long/short 1-DTE SPX straddles sized by a mean-reversion signal on recent straddle returns, with weekend-gap-aware position rules.
* [**VIX Futures PCA Trade**](https://github.com/lanteignel93/vix_pca_futures_trade_public) — PC1-neutral relative value on the VIX futures curve: level shocks hedged out, roll-down and curvature kept.
* [**Earning Trade**](https://github.com/lanteignel93/earning_trade_public) — Delta-neutral ATM straddles around earnings: long the pre-announcement IV ramp, short the announcement crush.
* [**VXX Trade**](https://github.com/lanteignel93/vxx_trade) — An earlier end-to-end build: a VXX vol strategy as the vehicle for packaging, OOP design, and backtest engineering practice.

---

### Other Active Projects

#### [`matching_engine`](https://github.com/lanteignel93/matching_engine)
A limit order book and matching engine in modern C++ — successor to [`order_book_cpp`](https://github.com/lanteignel93/order_book_cpp), which is kept as the "before" picture.
* **Format:** Milestone-driven — the docs teach, every line is hand-written, pre-written doctest suites judge it.
* **Engine:** Price-time priority LOB, rebuilt then optimized: ~0.8M msgs/s (the old design) → ~10.6M msgs/s (reference V2) on the same 1M-message replay data.
* **Tech:** C++20, CMake presets, ASan/UBSan/TSan, benchmark harness; fully offline (vendored test framework, shipped data).
* **Status:** *Active*

#### [`hft_market_making_theory`](https://github.com/lanteignel93/hft_market_making_theory)
HJB solvers, closed forms, and a limit-order-book simulator for the optimal market-making problem.
* **Source:** Cartea, Jaimungal & Penalva, *Algorithmic and High-Frequency Trading* (CUP 2015), Ch. 10 — plus extensions that go past the book.
* **Method:** Each notebook derives the HJB, solves it (closed form where one exists, numerically otherwise), then verifies against an independent check — Monte Carlo,
matrix exponential, or an analytic limit.
* **Coverage:** Inventory aversion, at-the-touch, adverse selection, multi-level ladders, exogenous and filtered alpha, LOB-aware simulation — 11 notebooks, read in
order.
* **Numerics:** Explicit / implicit / Crank-Nicolson, with convergence-order and stability analysis.
* **Tech:** Python 3.13, `uv`, unit-tested solvers in `src/mm_theory/`, CI on every push.
* **Status:** *Active*

--- 

### Offline
* **Sports:** Marathon training, skiing, tennis.
* **Audio:**
  * *Headphones*: Schiit Stack + Beyerdynamic.
  * *Desktop Monitors*: Fosi Audio v3 + Wharfedale Diamond 12.0.
  * *TV Setup*: Yamaha A-S301 Integrated Amplifier + Monitor Audio Bronze 2. 
* **Others**: Cooking, wine, and making cocktails. 
