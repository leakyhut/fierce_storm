
# Thermodynamic Amplification of Global Tropical Cyclones (1999–2024)

**Course:** DATA 608 — Visual Analytics  
**Institution:** CUNY School of Professional Studies (CUNY SPS)  
**Author:** Dariusz
**Live Application:** [`temperature_v6.html`](./temperature_v6.html)

---

## 1. Project Overview & Research Thesis

A widespread misconception across media and climate discourse is that anthropogenically driven global warming causes a continuous surge in the *annual frequency* of tropical cyclones.

This visual analytics research project synthesizes 26 years of high-resolution observational records (**1999–2024**) sourced from **NOAA NCEI**, **NASA GISTEMP v4**, and **IBTrACS v04r00**.

### Core Climatological Findings
1. **Global Frequency Invariance:** Annual global tropical cyclone counts remain stationary ($\mu = 85.3 \pm 2.8\text{ storms/yr}$). Statistical testing confirms zero correlation between surface temperature anomalies and global annual frequency ($r = -0.042,\; p = 0.84$). Tropical cyclogenesis is capped by upper-tropospheric thermal stabilization and vertical wind shear boundaries.
2. **Kinetic & Thermodynamic Escalation:** Rising sea surface temperatures (SST) and Upper Ocean Heat Content ($0\text{–}700\text{m}$) act as thermodynamic fuel. The proportion of high-destruction Category 4–5 cyclones has expanded from **22.8%** (1999–2003 baseline) to **35.4%** (2019–2024 window), representing a $+12.6\%$ increase ($p < 0.01$).
3. **Compound Ground Vulnerability:** Every $+1^\circ\text{C}$ of atmospheric warming elevates atmospheric water-vapor capacity by $\approx 7\%$ (Clausius-Clapeyron equation), while secular sea-level rise ($+23\text{ cm}$) elevates base storm surge run-up, creating unprecedented compound flooding risks even from systems that stall or weaken before inland penetration.

---

## 2. Statistical & Theoretical Frameworks

### 2.1 Emanuel Maximum Potential Intensity (MPI)
The theoretical upper limit of tropical cyclone central wind speed is governed by Carnot heat engine thermodynamics:

$$V_{max}^2 = \frac{C_k}{C_D} \left( \frac{T_s - T_o}{T_o} \right) (k_s^* - k)$$

Where:
* $T_s$: Sea surface temperature (K)
* $T_o$: Outflow temperature at the tropopause (K)
* $C_k / C_D$: Ratio of surface exchange coefficients of enthalpy to momentum
* $k_s^* - k$: Thermodynamic air-sea enthalpy disequilibrium

### 2.2 Accumulated Cyclone Energy (ACE)
Kinetic energy integration across storm lifecycles is quantified using the NOAA/Colorado State ACE formulation:

$$\text{ACE} = 10^{-4} \sum_{i=1}^{N} v_{\max, i}^2$$

Where $v_{\max, i}$ is the estimated maximum sustained wind speed (in knots) recorded at standard 6-hour synoptic intervals for all active tropical systems with winds $\ge 35\text{ kt}$.

### 2.3 Clausius-Clapeyron Atmospheric Scaling
The saturation vapor pressure ($e_s$) over water scales quasi-exponentially with temperature ($T$):

$$\frac{de_s}{dT} = \frac{L_v \cdot e_s}{R_v \cdot T^2} \implies \frac{\Delta e_s}{e_s} \approx 7\% \text{ per } 1^\circ\text{C warming}$$

---

## 3. Visualization Structure & Academic Design Choices

| Figure | Metric / Focus | Chart Type | Academic Rationale |
| :--- | :--- | :--- | :--- |
| **Figure 1.1** | Surface Temperature Anomaly | Filled Area Line + OLS Fit | Instrumental anomalies with fitted Ordinary Least Squares linear trend ($+0.033^\circ\text{C}/\text{yr},\; R^2 = 0.831$) contextualizing post-2015 acceleration. |
| **Figure 1.2** | The Decoupling Paradox | Dual-Axis / Normalized Index | Solves dual-axis scale distortion critiques by providing an interactive toggle between raw secondary axes and a normalized baseline index ($1999=100$). |
| **Figure 2.1** | Structural Intensity Shift | 100% Stacked Bar Chart | Aggregates cyclones into 5-year climatological windows to smooth out short-term ENSO noise, isolating the secular growth of Cat 4–5 storms relative to Cat 1–2 systems. |
| **Figure 2.2** | Kinetic Power Surge | Multi-Variable Line | Pairs Upper Ocean Heat Content ($0\text{–}700\text{m}$, $10^{22}\text{ J}$) with ACE index, illustrating how subsurface thermal energy sustains eyewall structures. |
| **Figure 3.1** | Geographic Synthesis GIS | Standalone Vector SVG Map | Zero-dependency vector layer mapping warm pools ($>28.5^\circ\text{C}$), historical Cat 5 tracks (Milton, Otis, Haiyan), and dynamic basin telemetry. |
| **Figure 4.1** | Compound Deluge & Surge Impact | Multi-Pillar Metric Cards | Translates physical equations into observable damage mechanics: Clausius-Clapeyron $+7\%$ moisture capacity, $+23\text{ cm}$ sea-level rise baseline, and CAPE convective instability. |

---

## 4. Key Empirical Findings (1999–2024 Synthesis)

| Metric | 1999 Baseline | 2024 Observation | Net Delta / Trend | Statistical Significance |
| :--- | :---: | :---: | :---: | :---: |
| **NASA Surface Anomaly** | $+0.45^\circ\text{C}$ | $+1.28^\circ\text{C}$ | $+0.83^\circ\text{C}$ | OLS slope $= +0.033^\circ\text{C}/\text{yr}\; (p < 0.001)$ |
| **Annual Cyclone Count** | 88 storms | 84 storms | $-4$ storms | Pearson $r = -0.042,\; p = 0.84$ (Stationary) |
| **Category 4–5 Ratio** | 22.8% (1999–03) | 35.4% (2019–24) | $+12.6\%$ shift | Two-proportion $z$-test: $z = 3.12,\; p < 0.005$ |
| **Upper OHC ($0\text{–}700\text{m}$)** | $4.2 \times 10^{22}\text{ J}$ | $33.6 \times 10^{22}\text{ J}$ | $+29.4 \times 10^{22}\text{ J}$ | Record high thermal accumulation |
| **Global ACE Index** | 670 | 990 | $+320\text{ points}$ | Secular increase matching SST trends |

---
