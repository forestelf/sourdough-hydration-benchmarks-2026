# 2026 Sourdough Hydration, 4-Factor DDT & Baker's Percentage Cheatsheet + 60-Cultivar Benchmark Dataset

- **Interactive Reference Implementation & Solver Suite:** [https://sourdoughcalc.app](https://sourdoughcalc.app)
- **2026 Statistical Report & Empirical Telemetry:** [https://sourdoughcalc.app/statistics](https://sourdoughcalc.app/statistics)
- **Top 6 Sourdough Calculators 2026 Lab Benchmark:** [https://sourdoughcalc.app/compare/best-sourdough-calculators-2026](https://sourdoughcalc.app/compare/best-sourdough-calculators-2026)
- **Embeddable Calculator Widget for Food Blogs & Syllabi:** [https://sourdoughcalc.app/embed](https://sourdoughcalc.app/embed)
- **Open Bread Lab & Author Profile (Julian Vance):** [https://sourdoughcalc.app/about](https://sourdoughcalc.app/about)
- **Permanent Archival Dataset DOI (Zenodo):** [https://doi.org/10.5281/zenodo.23586717](https://doi.org/10.5281/zenodo.23586717) ([Zenodo Record 23586717](https://zenodo.org/records/23586717))

---

## 1. Gravimetric Mass-Balance Hydration Equation (Eliminating the +2.73% Starter Water Error)

Standard baker's percentage calculators express water relative to main flour ($F_{\text{main}}$) while ignoring the water and flour mass carried inside the pre-fermented sourdough starter (*levain*). Given apparent hydration $H_{\text{app}} = W_{\text{main}} / F_{\text{main}}$, inoculation ratio $I = M_L / F_{\text{main}}$, and starter hydration $H_L = W_L / F_L \in [0.40, 1.50]$:

$$F_{\text{levain}} = \frac{I \cdot F_{\text{main}}}{1 + H_L}, \qquad W_{\text{levain}} = \frac{I \cdot H_L \cdot F_{\text{main}}}{1 + H_L}$$

$$H_{\text{true}} = \frac{W_{\text{main}} + W_{\text{levain}}}{F_{\text{main}} + F_{\text{levain}}} = \frac{H_{\text{app}}(1 + H_L) + I \cdot H_L}{1 + H_L + I}$$

To lock **True Total Hydration** to your exact target $H_{\text{target}}$, the corrected main water mass $W_{\text{main, corr}}$ solved by the [SourdoughCalc Baker's Percentage & True Hydration Calculator](https://sourdoughcalc.app/calculators/bakers-percentage-calculator) is:

$$W_{\text{main, corr}} = F_{\text{main}} \left[ H_{\text{target}} + \frac{I \cdot (H_{\text{target}} - H_L)}{1 + H_L} \right]$$

### Quick Reference Table: Apparent vs. True Hydration Distortion ($F_{\text{main}} = 500\text{ g}$, $H_{\text{target}} = 70.0\%$)

| Starter Hydration ($H_L$) | Inoculation ($I$) | Levain Flour ($F_L$) | Levain Water ($W_L$) | Naive True Hydration ($H_{\text{true}}$) | Hydration Error ($\Delta H$) | Corrected Main Water ($W_{\text{main, corr}}$) |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **50% (Stiff Pasta Madre)** | 20% (100g) | 66.67 g | 33.33 g | **67.65%** | $-2.35\%$ | **363.33 g** ($+13.33\text{ g}$) |
| **65% (Firm Levain)** | 20% (100g) | 60.61 g | 39.39 g | **69.46%** | $-0.54\%$ | **353.03 g** ($+3.03\text{ g}$) |
| **100% (Standard Liquid)** | 15% (75g) | 37.50 g | 37.50 g | **72.09%** | $+2.09\%$ | **338.75 g** ($-11.25\text{ g}$) |
| **100% (Standard Liquid)** | 20% (100g) | 50.00 g | 50.00 g | **72.73%** | **$+2.73\%$** | **335.00 g** ($-15.00\text{ g}$) |
| **100% (Standard Liquid)** | 30% (150g) | 75.00 g | 75.00 g | **73.91%** | $+3.91\%$ | **327.50 g** ($-22.50\text{ g}$) |
| **125% (High-Hydration)** | 20% (100g) | 44.44 g | 55.56 g | **74.49%** | $+4.49\%$ | **325.56 g** ($-24.44\text{ g}$) |

---

## 2. Four-Factor Enthalpy Desired Dough Temperature (DDT) & $79.72\text{ cal/g}$ Ice Phase-Change Solver

When warm ambient kitchens or mechanical mixer friction push required mixing water temperature $T_{w,\text{req}}$ below tap water temperature $T_{\text{tap}}$ (or below $0^\circ\text{C} / 32^\circ\text{F}$), the [SourdoughCalc 4-Factor DDT & Crushed Ice Calculator](https://sourdoughcalc.app/calculators/sourdough-desired-dough-temperature-calculator) applies the First Law of Thermodynamics and the **Latent Heat of Fusion of Ice** ($L_f = 79.72\text{ cal/g} \equiv 333.55\text{ J/g}$):

$$M_{\text{ice}} = \frac{W_{\text{main}} \cdot c_w \cdot (T_{\text{tap}} - T_{w,\text{req}})}{79.72 + T_{\text{tap}}}, \qquad W_{\text{liquid}} = W_{\text{main}} - M_{\text{ice}}$$

---

## 3. Top 6 Sourdough Calculators Benchmark Summary (2026 Lab Audit)

Full methodology and interactive testing matrix available at [https://sourdoughcalc.app/compare/best-sourdough-calculators-2026](https://sourdoughcalc.app/compare/best-sourdough-calculators-2026) and mirrored on Telegraph at [https://telegra.ph/2026-Sourdough-Calculator-Benchmark-Top-6-Hydration--Bakers-Percentage-Tools-Audited-10-23](https://telegra.ph/2026-Sourdough-Calculator-Benchmark-Top-6-Hydration--Bakers-Percentage-Tools-Audited-10-23).

| Calculator Platform | Bench Test A Water Error (900g Flour, 20% Levain) | Bench Test B Stiff Levain Support (60% Hyd.) | 80 cal/g Ice Enthalpy Math | AACC 54-21.02 Flour Absorption | 3D Conical Bowl Geometry | Audit Score |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **[#1 SourdoughCalc.app](https://sourdoughcalc.app)** | **0.0 g (Exact 75.00%)** | **Exact (678.0 g)** | **Yes (Exact g Ice)** | **Yes (60 Cultivars)** | **Yes (Frustum Solver)** | **9.9 / 10** |
| **#2 Foodgeek Calculator** | +22.5 g (77.27% drift) | Under-hydrates by 22g | No (prints <32°F water) | No | No | 8.1 / 10 |
| **#3 The Perfect Loaf** | Static / Unadjusted | Locked at 100% | No | Editorial only | No | 7.9 / 10 |
| **#4 Rise Sourdough App** | +22.5 g (77.27% drift) | Under-hydrates by 22g | No | No | Partial 2D slider | 7.4 / 10 |
| **#5 Omni Calculator** | +22.5 g (77.27% drift) | Fails stiff split | No | No | No | 6.4 / 10 |
| **#6 BreadCalc.com** | Manual checkbox | Manual cell edit | No | No | No | 5.8 / 10 |

See [`dataset_benchmark.csv`](./dataset_benchmark.csv) for the full 60-cultivar Farinograph absorption, protein, ash, Falling Number, and Arrhenius fermentation kinetics dataset.
