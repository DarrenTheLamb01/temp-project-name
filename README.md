# Statistical Analysis of Yelp Restaurant Ratings

This project explores how Yelp restaurant ratings vary across contextual factors such as price level, cuisine type, geographic location, and chain status. Rather than treating star ratings as absolute measures of quality, we examine how expectations and norms shape rating distributions across different restaurant contexts.

This repository contains the full data pipeline for the STA 141B final project, including data acquisition, cleaning, transformation, exploratory analysis, and visualization.

## Research Questions

This project addresses the following questions:

1. How are Yelp ratings distributed overall across U.S. restaurants?
2. Do Yelp rating distributions differ across price levels?
3. How do ratings vary by cuisine type, and how does cuisine interact with price level?
4. Are there systematic geographic differences in average Yelp ratings across states?
5. Do chain restaurants exhibit different rating patterns compared to non-chain restaurants?

## Data Source

Data were collected using the **Yelp Fusion API**, sampling approximately 100,000 restaurants from randomly selected cities across all U.S. states.  
(Details of data acquisition are documented in the project report.)

## Repository Structure

Yelp-Rating-Analysis/
│
├── data/
│ ├── raw/ # Raw API responses
│ └── processed/ # Cleaned and analysis-ready datasets
│
├── src/
│ ├── scraping/ # API scraping notebooks
│ ├── processing/ # Data cleaning and transformation notebooks
│ └── visualization/ # Exploratory analysis and visualization notebooks
│
├── figures/ # Exported figures used in the final report
├── docs/ # Final project report (PDF)
│
├── requirements.txt
└── README.md


## Methods Overview

The analysis pipeline consists of:

- **Data cleaning and transformation**
  - Converting price levels and categorical fields into analysis-ready formats
  - Identifying chain vs. non-chain restaurants
  - Standardizing and mapping cuisines into major cuisine groups

- **Exploratory data analysis**
  - Distributional analysis of Yelp ratings
  - Comparisons across price tiers and cuisine groups
  - Geographic aggregation at the state level
  - Chain vs. non-chain comparisons

- **Visualization**
  - Histograms and boxplots
  - Cuisine–price interaction heatmaps
  - Geographic choropleth maps
  - All figures follow visualization best practices and are saved in the `figures/` directory

## Key Findings

- Yelp ratings are highly compressed, with most ratings clustered between 3.5 and 4.5 stars.
- Higher price levels are associated with slightly higher median ratings, though the highest price tier shows greater variability.
- Cuisine type significantly shapes rating distributions, with fast food showing lower and more variable ratings than dessert or café-oriented establishments.
- Geographic differences exist but are modest, suggesting local norms influence ratings.
- Chain restaurants exhibit more standardized ratings, while non-chain restaurants show greater variability.

These results suggest that Yelp star ratings should be interpreted **relative to context**, not as universal measures of restaurant quality.

## Reproducibility

All analyses can be reproduced by running the notebooks in order:

1. `src/scraping/scrape.ipynb`
2. `src/processing/cleaning.ipynb`
3. `src/processing/yelp_transformations.ipynb`
4. `src/visualization/Visualizations.ipynb`

Install dependencies with:

```bash
pip install -r requirements.txt
