# Laurent Lanteigne

> **Quant**
> *Bridging high-level financial strategy with low-level systems engineering.*

Based in **Chicago, IL** (via Québec, Canada).

---

### Markets
* **Focus:** Volatility arbitrage, Mid-Frequencies strategies, and Market Microstructure.
* **Philosophy:** "Don't just analyze the data; build the engine that analyzes the data."
* **Process:** Every strategy carries registered hypotheses, a sealed holdout, and stated kill criteria. One of them is public and killed.

---

### Market Strategies
*Named on a ski theme — each name encodes the character of the trade.*

* [**Schuss — One-DTE Volatility Strategy**](https://github.com/lanteignel93/schuss_trade_public) — Long/short 1-DTE SPX straddles sized by a mean-reversion signal on recent straddle returns, with weekend-gap-aware position rules.
* [**Traverse — Index-vs-Name Skew Dispersion**](https://github.com/lanteignel93/traverse_trade_public) — Short the SPX put wing, long single-name puts, vega-flat: harvesting the implied-correlation premium that lives in the index wing.
* [**Corduroy — Daily Put-Ladder Skew Harvest**](https://github.com/lanteignel93/corduroy_trade_public) — Sell the SPX 20Δ put ladder every day against a 50Δ straddle and a far-OTM tail strip; one scale knob, no signals, holdout-validated.
* [**Cornice — SPX Put-Skew Mean Reversion**](https://github.com/lanteignel93/cornice_trade_public) — PCA-isolated put-skew steepness (PC2) mean reversion, expressed in delta-hedged 1×2 put ratio spreads.
* [**Snowpack — VIX Curve Relative Value**](https://github.com/lanteignel93/snowpack_trade_public) — PC1-neutral relative value on the VIX futures curve: level shocks hedged out, roll-down and curvature kept.
* [**Slab — Earnings Straddle Book**](https://github.com/lanteignel93/slab_trade_public) — Delta-neutral ATM straddles around earnings: long the pre-announcement IV ramp, short the announcement crush.
* [**Slush — VXX Research Project**](https://github.com/lanteignel93/slush_trade_public) — An earlier end-to-end build: a VXX vol strategy as the vehicle for packaging, OOP design, and backtest engineering practice.

---

### Other Active Projects

#### [`lob-engine`](https://github.com/lanteignel93/lob-engine)
A limit order book and price-time priority matching engine in C++20 — successor to [`order_book_cpp`](https://github.com/lanteignel93/order_book_cpp), which is kept as the "before" picture.
* **Engine:** Price ladder, pooled intrusive FIFOs, open-addressed order-id index, and an SPSC feed → book pipeline. ~0.8M msgs/s (old design) → 3.95M (map-based book) → **15.5M msgs/s** on the same 1M-message replay.
* **Correctness:** One contract suite for both books, a 50k-op differential fuzz of fast vs. reference book, and a golden `trade_hash` replay over every fill.
* **Measured, not asserted:** Every optimization commit carries its before/after numbers — including the ones that surprised (a textbook hash that lost to `std::unordered_map`; a reserve fix visible only in `max` latency).
* **Tech:** C++20, CMake presets, gcc/clang × ASan/UBSan/TSan CI, clang-tidy, benchmark harness.
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

### Research & Case Studies

#### **[Trade Analysis: 1-DTE Weekend Gap](https://github.com/lanteignel93/trade_analysis_example)**
* A quantitative post-mortem of a short-duration volatility strategy. 
* Analyzes theta decay vs. gamma risk exposure, specifically focusing on the PnL variance caused by weekend gap risk.

#### **[Replication Price Sensitivity](https://github.com/lanteignel93/replication_prices)**
* Stress-testing the Black-Scholes model.
* This study quantifies the replication error (PnL leakage) that occurs when theoretical assumptions—specifically continuous hedging and log-normal distribution—are violated by real-world market conditions.

---

### Technical Stack

| Domain | Technologies |
| :--- | :--- |
| **Quant Finance** | Python (**Polars**, Pandas), **R** (Time Series), SQL, LaTeX |
| **Systems & Speed** | C++ (intermediate), Linux |
| **AI Engineering** | Multi-Agent Orchestration, LLM Integration, CI/CD Pipelines |

---

### Working with AI

Claude Code is wired into the daily loop through a set of private repos — custom hooks,
slash commands, subagents, persistent memory, an engineering journal it maintains, and an
Obsidian vault it reads. It runs as *research assistant* (strategy logs,
registered-hypothesis workflows, review passes), *executive assistant* (task tracking,
briefings, weekly reviews), and *pair programmer*.

A sanitised public release of that setup is in
[`dotclaude.public`](https://github.com/lanteignel93/dotclaude.public) — task engine,
journal, briefing and research-note scaffolding — with
[`work-journal.public`](https://github.com/lanteignel93/work-journal.public) as its
companion. The claim below is meant to be checkable rather than rhetorical.

Stated plainly: much of the systems code here is substantially AI-assisted. The research
discipline is built around that rather than in spite of it — registered hypotheses, sealed
holdouts and stated kill criteria mean verification does not rest on the author's
confidence.

---

### Workflow Setup 
See my whole setup in [`dotfiles.public`](https://github.com/lanteignel93/dotfiles.public): Neovim, tmux, zsh, kitty and an awesome WM + polybar desktop.  
* **Editor:** Neovim (Lua-configured, custom TUI integrations) 
* **Terminal:** Kitty + Zsh
* **Multiplexer:** TMUX
* **Window manager:** awesome WM + polybar
* **Environment:** Linux/Ubuntu
* **Note taking:** Obsidian 
* **Python tooling:** uv, ruff, pre-commit, pytest
* **Additional CLI/TUI Tools**:
  * fzf
  * scooter *(find-and-replace TUI)*
  * lazygit
  * eza
  * gh

---

### Themes
*Two palettes, one switch. Each ships as a Neovim colorscheme, and the same palette dresses the terminal, prompt, tmux, window manager, Obsidian and Spotify, flipped together by one command.*

* [**spacecowboy.nvim**](https://github.com/lanteignel93/spacecowboy.nvim) — A desert at night: umber ground, sand text, and two hue families only, cactus green and dust orange.
* [**voidrunner.nvim**](https://github.com/lanteignel93/voidrunner.nvim) — Near-black ground, pale accents: lime for what is yours, mint for what arrives, lavender for what is elsewhere.

| spacecowboy | voidrunner |
| :---: | :---: |
| [<img src="https://raw.githubusercontent.com/lanteignel93/spacecowboy.nvim/main/screenshots/cpp.png" width="420" alt="spacecowboy.nvim: C++ and Python in Neovim">](https://github.com/lanteignel93/spacecowboy.nvim) | [<img src="https://raw.githubusercontent.com/lanteignel93/voidrunner.nvim/main/screenshots/cpp.png" width="420" alt="voidrunner.nvim: C++ and Python in Neovim">](https://github.com/lanteignel93/voidrunner.nvim) |

---

### Offline
* **Sports:** Marathon training, skiing, tennis.
* **Audio:**
  * *Headphones*: Schiit Stack + Beyerdynamic.
  * *Desktop Monitors*: Fosi Audio v3 + Wharfedale Diamond 12.0.
  * *TV Setup*: Yamaha A-S301 Integrated Amplifier + Monitor Audio Bronze 2. 
* **Others**: Cooking, wine, and making cocktails.
