# STOR 455 – Homework 6

This repository contains my completed **Homework 6** for **STOR 455: Statistical Methods II** at UNC–Chapel Hill. The assignment is implemented in **R Markdown** and focuses on applying regression modeling concepts using real data, clear code, and reproducible analysis.

---

## Contents

* `STOR 455 - Homework 6.Rmd`
  Main R Markdown file containing:

  * Data import and cleaning
  * Exploratory summaries and visualizations
  * Model construction (logistic / linear regression as assigned)
  * Interpretation of coefficients and model fit
  * Diagnostic checks and written conclusions

*(If your instructor gave additional starter files or data, list them here as needed.)*

---

## How to Run

1. Open RStudio.
2. Set your working directory to this folder:

   ```r
   setwd("path/to/this/folder")
   ```
3. Open the R Markdown file:

   ```r
   file.edit("STOR 455 - Homework 6.Rmd")
   ```

   or click it in the RStudio Files pane.
4. Install required packages (if not already installed):

   ```r
   install.packages(c("tidyverse", "ggplot2", "dplyr", "readr", "broom"))
   ```
5. Knit the document to HTML or PDF using the **Knit** button in RStudio.

---

## Key Features

* Fully reproducible workflow in one `.Rmd` file
* Clean, commented code written in a style appropriate for upper–level stats coursework
* Emphasis on:

  * Proper model specification
  * Interpreting results in context
  * Comparing models and checking assumptions
  * Professional, readable plots and summaries
