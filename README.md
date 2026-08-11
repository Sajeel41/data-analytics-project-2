# Exploratory Data Analysis

DecodeLabs Data Analytics Internship, Batch 2026  
Project 2: Exploratory Data Analysis  
Prepared by Sajeel Ahmed

## Headline

This dataset is synthetic. It is not suitable for business decisions.

## Overview

Project 1 confirmed this dataset is structurally clean, with no duplicates
and no format errors. Structural cleanliness says nothing about whether the
values are meaningful. This project examines the distributions,
relationships and trends inside the data to find out whether any of it can
support a business conclusion.

The answer is no, and the analysis explains why.

## Files

| File | Purpose |
|---|---|
| `Project2_EDA.ipynb` | Full analysis notebook with charts and commentary |
| `Project 2 Executive Summary.pdf` | Four part summary with findings and recommendations |

The dataset and the Project 1 audit are in the
[Project 1 repository](https://github.com/Sajeel41/data-analytics-project-1).

## Method

Descriptive statistics, distribution shape measured by skew, IQR outlier
detection, correlation analysis, and monthly revenue aggregation across the
30 month period. Python, pandas and matplotlib.

## Key findings

**UnitPrice is uniformly distributed (skew of -0.03).** Prices spread evenly
from 11.39 to 699.93 with no peak anywhere. Real pricing never behaves this
way. This is the strongest single piece of evidence that the values were
generated at random.

**Quantity and ItemsInCart are also almost perfectly symmetrical.** Three of
the four numeric columns are flat.

**TotalPrice is the only skewed column (0.89), but the skew is
mathematical.** TotalPrice equals Quantity multiplied by UnitPrice, and
multiplying two symmetrical values always produces a right skew. Reporting
this as evidence that some customers spend far more would be a false
conclusion.

**Only one genuine correlation exists**, between Quantity and ItemsInCart at
0.650. The correlations between TotalPrice and its own components are
structural and carry no information. ItemsInCart is never lower than
Quantity in any of the 1,200 rows, which points to a generation rule rather
than customer behaviour.

**Monthly revenue shows no trend.** Values move between roughly 28,000 and
68,000 with no direction and no seasonal repetition.

## Outliers

The IQR method flagged 8 orders above 3,330.41. All eight combine the
maximum quantity of 5 with a unit price near the maximum of 699.93. Every
value sits inside the valid range, so none are data entry errors. They are
statistical outliers rather than business outliers, and they were retained.

## Recommendations

Do not use this data for pricing decisions, revenue forecasting, customer
segmentation or geographic analysis. The reasons for each are in the
executive summary.

The dataset is suitable for technical practice, which is what it appears
designed for. Any conclusion about the business it claims to describe would
be invented rather than discovered.
