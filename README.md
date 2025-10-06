# Micro-Level-Analysis-of-Armed-Group-Presence-in-Colombia

_This quantitative political science project examines whether armed group presence in Colombia’s municipalities can be better explained by “ideational” grievance factors — such as political competition and strategic positioning — rather than traditional “greed” factors like resource access._

---

## 🎯 Overview

This study challenges Collier & Hoeffler’s (2004) finding that “grievance” factors are unimportant in explaining civil wars.  
Focusing on Colombia (2002–2011), I test whether the presence of nonstate armed groups (FARC, ELN, AUC) across 1,123 municipalities reflects:

1. **Greed-based incentives** — resource maximization through coca cultivation and land quality.  
2. **Grievance-based incentives** — ideological and political positioning in municipalities with:
   - Narrow electoral wins, or  
   - Party alternation (anti-incumbent victories).

By operationalizing **grievances as political strategies** rather than structural inequalities, the paper seeks to bridge micro-level civil war analysis and macro-level conflict theory.

---

## ⚙️ Methodology

### 1️⃣ Research Design
- **Type:** Quantitative micro-level panel analysis (2002–2011).  
- **Unit of analysis:** Municipality-year (n = 6,732).  
- **Approach:** Logistic regression estimating average marginal effects on the probability of armed group presence.

### 2️⃣ Theoretical Framework
Traditional “grievance” measures (e.g., inequality, ethnicity) fail to capture the **ideological project** of armed groups.  
This paper introduces **“ideational” proxies**:
- **H1:** Narrow-win municipalities → higher likelihood of armed group presence.  
- **H2:** Municipalities with party alternation → higher likelihood of armed group presence.

Armed groups motivated by ideology (FARC, ELN) are expected to locate strategically in politically contested regions, rather than simply where resources are abundant.

### 3️⃣ Data Sources
| Variable | Source |
|-----------|---------|
| Armed group presence | CEDE Panel Dataset (Nieto-Matiz, 2019) |
| Coca crop production | UNODC (2020) |
| Regional election results | Electoral Observation Mission (EOM, 2023) |
| State capacity, population, soil quality | CEDE, AmeriGEO |
| Left-right ideological orientation | Colombian electoral data (2007–2011) |

### 4️⃣ Statistical Models
Average marginal effects (AME) are estimated using logistic regression for:
- **Model 1:** Any armed group presence (FARC, ELN, AUC combined)  
- **Models 2–4:** Group-specific presence for FARC, ELN, AUC

All models control for:
- Population density  
- State capacity  
- Ideological orientation  
- Year fixed effects  

---

## 📈 Results

| Predictor | Estimate | Std. Error | Significance |
|------------|-----------|-------------|--------------|
| Coca Crop (Greed) | **+0.39** | 0.02 | *** |
| Soil Quality (Greed) | **+0.02** | 0.005 | ** |
| Regional Elections (Grievance) | +0.03 | 0.01 | * |
| Narrow Win (Grievance) | **+0.06** | 0.02 | ** |
| Party Alternation (Grievance) | +0.01 | 0.01 | ns |

**Key findings:**
- Greed-based predictors (especially coca crop cultivation) remain strong, increasing the probability of armed group presence by **39%**.
- However, **ideational grievance proxies** also show significant effects:
  - Municipalities with **narrow electoral margins** have a **6% higher probability** of armed group presence.
  - FARC presence, in particular, is jointly predicted by both greed and grievance factors.
- AUC and ELN display weaker or mixed results, suggesting divergent strategic logics.

---

## 🧠 Interpretation

These findings suggest that armed group behavior in Colombia is **not purely resource-driven**, but **politically strategic**.  
- FARC appears to be guided by an “ideological project,” establishing presence where political change is contested or possible.  
- This micro-level evidence contrasts with prior cross-sectional studies that dismissed grievances as unimportant.

Thus, **when grievances are measured ideationally**, rather than structurally, they exhibit explanatory power comparable to economic incentives.

---

## 🧰 Tech & Methods

| Category | Tools |
|-----------|-------|
| Language | R |
| Libraries | `tidyverse`, `dplyr`, `ggplot2`, `sf`, `rdrobust` |
| Methods | Logistic Regression, AME computation, Spatial mapping |
| Data Type | Municipality-year panel (2002–2011) |
| Visualization | Maps and effect plots (ggplot2) |

---

## 🚀 Reproducibility

To replicate the analysis:

```r
# Clone repository
git clone https://github.com/luccarallovander/Colombia-Greed-Grievance-Analysis.git
cd Colombia-Greed-Grievance-Analysis

# Install dependencies
install.packages(c("tidyverse", "sf", "rdrobust", "ggplot2"))

# Run main analysis
source("main_analysis.R")
