# 🌿 Average Rainfall by Species in the *Jacksonia* Genus

**Practical 1 – March 21, 2025**  
**Author:** Jane Maguire  

## 📌 Project Overview

This project investigates the differences in **average annual rainfall** experienced by species within the *Jacksonia* genus. The goals are to:

- Estimate **means and confidence intervals** of rainfall by species
- Test whether rainfall values **differ significantly** between species
- Visualize variation using statistical and graphical techniques

## 🌱 Motivation

I chose the *Jacksonia* genus because it's an interesting group of Australian plants. The goal is to better understand how **species in a single genus vary in their climate preferences**, specifically through annual rainfall.

## 📊 Data Sources

This study uses a cleaned dataset derived from:

- **The Atlas of Living Australia (ALA)**
- **WorldClim**

The original dataset includes all known plant observations and local climate data in Australia. For computational efficiency, we used a subset with **100 random observations per species**.

## 📦 R Packages Used

- `tidyverse`  
- `easystats`

## 🧹 Data Cleaning

Key cleaning steps include:

- Merging plant and genus data
- Filtering for *Jacksonia* species
- Removing:
  - Unrealistic precipitation values (e.g., bio12 > 2000 mm/yr)
  - A placeholder species name (*Jacksonia thisisanerrorensus*)
  - A clear outlier in *Jacksonia ramosissima*

## 🧪 Statistical Analysis

- Fit a **linear model**:  
  `bio12 ~ species`
- Checked assumptions:
  - Linearity
  - Normality of residuals
  - Constant variance
  - No influential outliers
- Calculated **means and 95% confidence intervals** for each species
- Ran **ANOVA**  
  Result: _p_ < 2.2e-16 → highly significant differences between species
- Conducted pairwise **post-hoc comparisons** using `estimate_contrasts()`

## 🔬 Notable Findings

Species with similar rainfall preferences (not significantly different):

- *Jacksonia ramulosa* and *Jacksonia foliosa*
- *Jacksonia fasciculata* and *Jacksonia epiphyllum*
- *Jacksonia fasciculata* and *Jacksonia condensata*
- *Jacksonia epiphyllum* and *Jacksonia condensata*
- *Jacksonia epiphyllum* and *Jacksonia angulata*
- *Jacksonia condensata* and *Jacksonia angulata*

All other pairs showed **significant differences** in average rainfall, many with _p_ < 0.001.

## 📈 Visualizations

- Boxplots and violin plots of rainfall distribution by species  
- A final plot showing **species-level means** with **confidence intervals**

## ⚠️ Limitations

- Subsampling (100 observations/species) may limit representation
- Potential geographic bias in occurrence records
- Other environmental factors (soil, temperature, etc.) not considered
- Outlier removal could exclude rare but valid data points

## 🚀 Future Work

- Incorporate additional environmental predictors
- Use full occurrence dataset
- Explore spatial or multivariate ecological modeling approaches
