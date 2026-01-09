# Overview

This project simulates the population dynamics of a crab invasion from Montauk to Southampton and New York City using **R** and **R Markdown**. The analysis models population growth and diffusion with uncertainty in key parameters, using **Monte Carlo simulations** to estimate population thresholds and times of establishment and eradication.

The goal is to understand how long it takes for crab populations to reach **minimum and maximum thresholds** at different locations and to quantify uncertainty in predictions.

---

# Key Components

## 1. Parameters

**Distance:**
- `Distance_SH = 27` – Montauk → Southampton (miles)
- `Distance_NYC = 118` – Montauk → NYC (miles)

**Population dynamics:**
- `r_mean = 0.81` – per capita monthly growth
- `K_mean = 943` – carrying capacity
- `D_mean = 0.22` – diffusion constant (miles/month)

**Thresholds:**
- `min_threshold = 8.1` – population per mile for establishment
- `max_threshold = 202` – population per mile for maximum density

---

## 2. Functions

- `crab_invasion(r, K, D, dx, Tmax, max_dist, N0)` – Simulates crab population over space and time using a **1D diffusion + logistic growth model**.
- Monte Carlo simulations apply **uncertainty** to `r`, `K`, and `D` to generate distributions of population outcomes.

---

## 3. Monte Carlo Simulation

- **Loops:** 1000 iterations
- **Uncertain parameters:** `r_mc`, `K_mc`, `D_mc` sampled from normal distributions with ±5% standard deviation.

**Calculates:**
- `reachSH_mc` – time until minimum threshold is reached in Southampton
- `maxSH_mc` – time until maximum threshold is reached in Southampton
- `reachNYC_mc` – time until minimum threshold is reached in NYC

---

## 4. Outputs

- **Time series plots** for mean population and 95% confidence intervals at Southampton and NYC.
- **Histograms** showing distributions of establishment and eradication times.


Quantitative summaries:

95% confidence intervals for establishment and max population thresholds.

Mean times for population establishment and maximum thresholds.
