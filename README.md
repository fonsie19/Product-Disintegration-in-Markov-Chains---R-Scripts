## Table of Contents

1. [Overview](#overview)
2. [Prerequisites](#prerequisites)
3. [Functions and Components](#functions-and-components)
4. [Usage](#usage)
5. [Outputs](#outputs)
6. [Customizations](#customizations)

---

## Overview

The script simulates Markov processes with:

- Discrete states for variables **𝜉** and **𝜂**: categorical states (**𝛼**, **𝛽**, **𝛾**, **𝛿**, **𝜀**).
- Discrete states for variable **X**: integer range from 1 to 10.

It allows exploration of the Markov property by generating heatmaps, analyzing transitions, and calculating model selection criteria (AIC/BIC) for different order models.

The code contains the following, separated in chunks:

1. {r 0} - setup
2. {r 1} - analysis of a Markovian process
3. {r 2} - analysis of higher order Markovian process that appears to be uniformly distributed conditionally on X(n-1)
4. {r 3} - analysis of higher order Markovian process that appears to behave similarly to the process in {r 1} conditionally on X(n-1)
5. {r eta} - analysis of the process constructed through random matrices **Z**
6. {r theta} - analysis of the process **𝜗**, constructed through alternating **X** and **𝜂** from the previous chunk

---

## Prerequisites

To run this script, ensure the following packages are installed:

- `ggplot2` for visualizations.
- `reshape2` for data transformations.
- `knitr` for rendering the R Markdown document.

You can install them using:

```R
install.packages(c("ggplot2", "reshape2", "knitr"))
```

Ensure the R environment is updated to support R Markdown and required libraries.

---

## Functions and Components

### 1. **Heatmap Generators**

- `heatmapY`: Plots empirical transition probabilities for **𝜉**.
- `heatmapX`: Plots empirical conditional probabilities for **X(n)** given **X(n-1)**.
- `heatmapXk`: Plots  empirical transition probabilities for **X(n)** given **X(n-1)** and **X(n-k)**.

### 2. **Markovianity Tests**

- `markovtest`: Computes AIC and BIC for first-order and third-order Markov models, based on log-likelihood calculations.

### 3. **Distribution and Transition Definitions**

- `distributionX`: Defines conditional distributions for **X** given **Y**.
- `Py#`: Defines transition probabilities for the processes.

---

## Usage

1. Open the HTML file for the default output, or the R Markdown script in RStudio or another R environment for a customized output.
2. Execute each code block sequentially to ensure all functions and variables are loaded.
3. Modify the transition matrices (`Py#`) to explore different processes.
4. Set different values for the parameters **n** and **k** as needed.

---

## Outputs

### 1. **Visualizations**

- Heatmaps of transition probabilities for **𝜉**, **𝜂**, **𝜗** and **X**.

### 2. **Model Statistics**

- AIC and BIC values for Markovianity tests.

---

## Customizations

- Modify the transition matrices (`Py#`) to explore different processes.
- Set different values for the parameters **n** and **k**

---
