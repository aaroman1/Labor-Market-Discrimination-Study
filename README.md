# Labor Market Discrimination Study

This repository contains an R Markdown report that reproduces and explores a classic field experiment on labor market discrimination, using the `ResumeNames455` dataset from the **Stat2Data** R package. The analysis focuses on how an applicant’s **name (as a signal of ethnicity)**, **sex**, and **years of experience** relate to the probability of receiving a callback.

## Background

The dataset comes from an experiment inspired by:

> Bertrand, M. & Mullainathan, S. (2004). *Are Emily and Greg More Employable Than Lakisha and Jamal?* American Economic Review, 94(4), 991–1013.

In the experiment, the authors sent out fictitious resumes with racially coded first names to real job openings and recorded whether each resume received a callback.

## Data

The main dataset used in the report is `ResumeNames455` from the **Stat2Data** package.

Key variables:

| Variable      | Description                                                                              |
|--------------|------------------------------------------------------------------------------------------|
| `call`       | Indicator for whether the applicant received a callback (1 = yes, 0 = no)               |
| `ethnicity`  | Name-based ethnicity category (e.g., “Caucasian-sounding” vs “African-American-sounding”) |
| `sex`        | Sex of the applicant                                                                     |
| `quality`    | Indicator for resume quality                                                             |
| `experience` | Number of years of work experience listed on the resume                                  |
| `equal`      | Whether the employer lists equal opportunity employment (EOE)                            |

## Analysis Overview

The R Markdown file walks through the following steps:

- Loading and briefly inspecting the `ResumeNames455` data.
- Fitting a **simple logistic regression** model:
  - `call ~ experience`
  - Summarizing coefficient estimates and interpreting the log-odds and odds ratios.
- Computing and interpreting the predicted probability that an applicant with **5 years of experience** receives a callback.
- Constructing an **empirical logit plot** to check whether the log-odds are approximately linear in experience.
- Fitting **separate logistic models by ethnicity**:
  - Splitting the data by `ethnicity`
  - Fitting `call ~ experience` within each group
  - Visualizing both the raw data and fitted curves on the same axes with `ggplot2`.
- Fitting **separate logistic models by sex** in the same way, and comparing the shapes of the fitted curves.

## Main Takeaways

- **Experience helps everyone**: For all groups, more years of experience are associated with a higher probability of receiving a callback.
- **Baseline differences by name-based ethnicity**: At similar levels of experience, applicants with “Caucasian-sounding” names tend to have a higher modeled callback probability than those with “African-American-sounding” names, suggesting unequal treatment even after controlling for experience.
- **Possible interaction with experience**: The fitted curves suggest that the return to experience may differ slightly across ethnic groups, though there is substantial uncertainty for very high experience levels where data are sparse.
- **Sex differences**: When models are fit separately by `sex`, both curves slope upward with experience. The fitted curve for women appears steeper at higher experience levels, but again, the extreme end is based on relatively few observations and should be interpreted cautiously.

These results reinforce the original study’s conclusion that labor market discrimination remains present in hiring outcomes.

## File Structure

- `Labor Market Discrimination Study.Rmd` – Main R Markdown report containing the full analysis and narrative.
- (Optional) `Labor Market Discrimination Study.pdf` – Knitted PDF output, if you choose to render the report.

## Requirements

To run the analysis, you will need:

- **R** (and ideally **RStudio**)
- The following R packages:

```r
install.packages(c("tidyverse", "Stat2Data", "car", "ggplot2"))
