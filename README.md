# 📊 Clinical Trial Power Analysis: Multi-Endpoint Dose Comparison

This R project performs a **Monte Carlo simulation study** to evaluate statistical power in clinical trials with multiple endpoints and dose comparisons, focusing on Type 2 diabetes treatment trials.

## 🎯 Project Overview

The simulation evaluates three doses (0.25 mg, 0.50 mg, 0.80 mg) against placebo using **two primary endpoints**:
1. **Hemoglobin A1c (HbA1c)** – Primary glycemic control marker
2. **Fasting Serum Glucose** – Secondary glycemic endpoint

The study investigates:
- **Statistical power** across different multiple testing procedures
- **Impact of sample size** on power
- **Effect of endpoint correlation** on inference
- **Dose-response relationships**
- **Weight allocation in fallback procedures**

## 🧪 Methodology

### 📈 Statistical Framework
- **Multiple Testing Procedures**:
  - Fixed-sequence testing
  - Fallback procedure with weighted alpha allocation
  - Gatekeeping procedures (for three endpoints)
- **Simulation Design**:
  - Monte Carlo simulations (n=1000–100,000 iterations)
  - Multivariate normal data generation (`mvtnorm` package)
  - Two-sample t-tests for endpoint comparisons
- **Parameters Varied**:
  - Sample size (40–150 per arm)
  - Endpoint correlation (ρ = 0–1)
  - Standardized effect sizes (0.25–1.0)
  - Alpha allocation weights

### 🔬 Key Analyses
1. **Dose Comparison**: Identify the most statistically significant dose
2. **Power Analysis**: Empirical power calculation for each endpoint
3. **Parameter Sensitivity**: Impact of correlation, sample size, and effect size
4. **Visualization**: ggplot2 plots showing relationships between parameters and power

## 📊 Key Findings
# 🔍 Dose Selection
Dose B (0.50 mg) showed the most statistically significant results across endpoints

Clear dose-response relationship observed

Clinical relevance considered (effects > 0.4 deemed meaningful)

## ⚡ Power Characteristics
Sample size has strong positive correlation with power (ρ ≈ 0.8–0.9)

Endpoint correlation shows complex, sometimes counterintuitive effects on power

Standardized effect size strongly influences power, particularly for the corresponding endpoint

## ⚖️ Multiple Testing Insights
Fixed-sequence procedure: Conservative but clear hierarchical testing

Fallback procedure: More flexible with weighted alpha allocation

Weight distribution significantly impacts endpoint-specific power

Optimal when prioritizing clinically important endpoints

## 📈 Visualizations
The project generates several insightful plots:

Power vs. Sample Size: Positive logarithmic relationship

Power vs. Correlation: Complex, sometimes paradoxical patterns

Power vs. Effect Size: Expected positive monotonic relationships

Dose Comparison: Visual ranking of treatment efficacy

## 🛠️ Technical Implementation
# 🔧 Core Functions
Data Generation: rmvnorm() for correlated endpoints

Statistical Testing: t.test() with multiple comparison adjustments

Power Calculation: Empirical proportion of significant results

Visualization: ggplot2 with custom themes and annotations

## 📦 Key Packages
mvtnorm: Multivariate normal simulation

ggplot2: Publication-quality graphics

gMCP: Graphical multiple comparison procedures (optional)

## 📝 Interpretation Notes
# 🎲 Simulation Assumptions
Endpoints initially assumed independent (ρ = 0)

Equal variance across treatment arms

Normally distributed endpoint measurements

Balanced randomization (equal sample sizes)

## ⚠️ Limitations & Considerations
Simplified covariance structures

Assumption of known variance parameters

Focus on type I error control rather than clinical significance

Results specific to chosen parameter ranges

## 🔮 Future Extensions
Potential enhancements:

Bayesian approaches for dose finding

Adaptive designs with sample size re-estimation

Time-to-event endpoints (survival analysis)

Patient subgroup analyses

Cost-effectiveness integration

## 📚 References
Bretz, F., Maurer, W., Brannath, W., & Posch, M. (2009). A graphical approach to sequentially rejective multiple test procedures. Statistics in Medicine.

Dmitrienko, A., & Tamhane, A. C. (2007). Multiple testing problems in pharmaceutical statistics. Chapman and Hall/CRC.

European Medicines Agency. (2017). Guideline on multiplicity issues in clinical trials.

# 👨‍🔬 Author
Rezaul Karim Tusar,
MSc Epidemiology,
LMU München
