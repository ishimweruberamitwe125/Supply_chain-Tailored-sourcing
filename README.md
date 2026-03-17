# Multi-Product Tailored Sourcing: EOQ Comparison

**Comparative analysis of independent, equal-frequency, and tailored aggregation sourcing strategies for multi-product supply chains.**

---

## Overview

This repository provides a **quantitative comparison of three multi-product sourcing strategies** using Economic Order Quantity (EOQ) models. The analysis supports supply chain optimization and continuity planning by identifying which ordering policy minimizes total annual operational cost when products share common ordering costs (e.g., single supplier or shared shipment) while having product-specific ordering and holding costs.

---

## Repository Contents

### Notebook: Multi-Product Tailored Sourcing — EOQ Comparison

**File:** `Multi-Product-Tailored-Sourcing-EOQ-Comparison.ipynb`

The notebook implements and compares **three sourcing strategies** on a four-product dataset:

| Strategy | Description | Use case |
|----------|-------------|----------|
| **Independent sourcing** | Each product is ordered using its own EOQ. Order quantity \(Q_{\text{ind}}\) minimizes that product’s total cost (ordering + holding) using its full ordering cost (common + specific). | Baseline; no coordination across products. |
| **Equal-frequency sourcing** | All products are ordered on the same cycle. A single order quantity \(Q_{\text{eq}}\) is derived from total demand and the common ordering cost, then used to compute system-wide ordering and holding cost. | Full aggregation; simple coordination. |
| **Tailored aggregation** | Order quantity \(Q_{\text{tailored}}\) accounts for a **weighted average of product-specific ordering costs** (by demand) and common ordering cost. Balances coordination benefits with product-level cost differences. | Best cost when products differ in specific costs and demand. |

**Inputs (per product):**

- `demand` — annual demand (units)
- `common_ordering_cost` — cost incurred once per order regardless of product mix
- `specific_ordering_cost` — product-specific ordering cost
- `unit_cost` — cost per unit
- `holding_cost_rate` — annual holding cost as a fraction of unit cost

**Outputs:**

- Annual operational cost (ordering + holding) for **independent sourcing**
- Annual operational cost for **equal-frequency sourcing**
- Annual operational cost for **tailored aggregation sourcing**

The notebook uses the same four-product example across cells, with refinements (e.g., Pandas/NumPy for clarity and rounding). The **tailored aggregation** strategy typically yields the lowest total cost by explicitly modeling the trade-off between common and product-specific ordering costs.

---

## Why This Matters for Supply Chain Resilience

- **Chokepoint visibility:** Common ordering cost represents a shared resource (supplier, truck, facility). Comparing strategies shows how dependent total cost is on that shared cost and helps identify single points of failure.
- **Continuity planning:** Knowing the cost gap between independent and coordinated (equal-frequency vs. tailored) policies supports decisions on when to consolidate orders and when to tailor by product.
- **Optimization:** The analysis is directly applicable to critical manufacturing and defense-related supply chains where multiple parts are sourced from the same supplier or shipment and where minimizing cost supports industrial stability.

---

## Technologies & Methods

- **Python** — core implementation
- **NumPy** — numerical computation and square-root EOQ formulas
- **Pandas** — structured product data and row-wise/aggregate calculations
- **Jupyter Notebook** — reproducible step-by-step analysis and results

Formulas used:

- **Independent:** \(Q_{\text{ind}} = \sqrt{2 D (S_{\text{common}} + S_{\text{specific}}) / (h \cdot c)}\)
- **Equal frequency:** \(Q_{\text{eq}}\) from total demand and common cost; then system ordering + holding cost.
- **Tailored:** weighted specific ordering cost by demand; \(Q_{\text{tailored}}\) from total demand, common cost, and weighted specific cost; then system cost.

---

## How to Run

1. Clone or download this repository.
2. Install dependencies: `numpy`, `pandas`, `jupyter` (or use an environment with these).
3. Open `Multi-Product-Tailored-Sourcing-EOQ-Comparison.ipynb` in Jupyter or VS Code.
4. Run all cells to reproduce the cost comparison for the three strategies.

---

## Author

**David Ishimwe Ruberamitwe**  

Focus: supply chain optimization, multi-product sourcing strategies, and quantitative models for resilient manufacturing and continuity planning.

# Multi-Product Tailored Sourcing: EOQ Comparison

**Comparative analysis of independent, equal-frequency, and tailored aggregation sourcing strategies for multi-product supply chains.**

---

## Overview

This repository provides a **quantitative comparison of three multi-product sourcing strategies** using Economic Order Quantity (EOQ) models. The analysis supports supply chain optimization and continuity planning by identifying which ordering policy minimizes total annual operational cost when products share common ordering costs (e.g., single supplier or shared shipment) while having product-specific ordering and holding costs.

---

## Repository Contents

### Notebook: Multi-Product Tailored Sourcing — EOQ Comparison

**File:** `Multi-Product-Tailored-Sourcing-EOQ-Comparison.ipynb`

The notebook implements and compares **three sourcing strategies** on a four-product dataset:

| Strategy | Description | Use case |
|----------|-------------|----------|
| **Independent sourcing** | Each product is ordered using its own EOQ. Order quantity \(Q_{\text{ind}}\) minimizes that product’s total cost (ordering + holding) using its full ordering cost (common + specific). | Baseline; no coordination across products. |
| **Equal-frequency sourcing** | All products are ordered on the same cycle. A single order quantity \(Q_{\text{eq}}\) is derived from total demand and the common ordering cost, then used to compute system-wide ordering and holding cost. | Full aggregation; simple coordination. |
| **Tailored aggregation** | Order quantity \(Q_{\text{tailored}}\) accounts for a **weighted average of product-specific ordering costs** (by demand) and common ordering cost. Balances coordination benefits with product-level cost differences. | Best cost when products differ in specific costs and demand. |

**Inputs (per product):**

- `demand` — annual demand (units)
- `common_ordering_cost` — cost incurred once per order regardless of product mix
- `specific_ordering_cost` — product-specific ordering cost
- `unit_cost` — cost per unit
- `holding_cost_rate` — annual holding cost as a fraction of unit cost

**Outputs:**

- Annual operational cost (ordering + holding) for **independent sourcing**
- Annual operational cost for **equal-frequency sourcing**
- Annual operational cost for **tailored aggregation sourcing**

The notebook uses the same four-product example across cells, with refinements (e.g., Pandas/NumPy for clarity and rounding). The **tailored aggregation** strategy typically yields the lowest total cost by explicitly modeling the trade-off between common and product-specific ordering costs.

---

## Why This Matters for Supply Chain Resilience

- **Chokepoint visibility:** Common ordering cost represents a shared resource (supplier, truck, facility). Comparing strategies shows how dependent total cost is on that shared cost and helps identify single points of failure.
- **Continuity planning:** Knowing the cost gap between independent and coordinated (equal-frequency vs. tailored) policies supports decisions on when to consolidate orders and when to tailor by product.
- **Optimization:** The analysis is directly applicable to critical manufacturing and defense-related supply chains where multiple parts are sourced from the same supplier or shipment and where minimizing cost supports industrial stability.

---

## Technologies & Methods

- **Python** — core implementation
- **NumPy** — numerical computation and square-root EOQ formulas
- **Pandas** — structured product data and row-wise/aggregate calculations
- **Jupyter Notebook** — reproducible step-by-step analysis and results

Formulas used:

- **Independent:** \(Q_{\text{ind}} = \sqrt{2 D (S_{\text{common}} + S_{\text{specific}}) / (h \cdot c)}\)
- **Equal frequency:** \(Q_{\text{eq}}\) from total demand and common cost; then system ordering + holding cost.
- **Tailored:** weighted specific ordering cost by demand; \(Q_{\text{tailored}}\) from total demand, common cost, and weighted specific cost; then system cost.

---

## How to Run

1. Clone or download this repository.
2. Install dependencies: `numpy`, `pandas`, `jupyter` (or use an environment with these).
3. Open `Multi-Product-Tailored-Sourcing-EOQ-Comparison.ipynb` in Jupyter or VS Code.
4. Run all cells to reproduce the cost comparison for the three strategies.

---

## Author

**David Ishimwe Ruberamitwe**  

Focus: supply chain optimization, multi-product sourcing strategies, and quantitative models for resilient manufacturing and continuity planning.
