# Delhi House Price Analysis

This repository contains a data analysis project focused on understanding the factors influencing residential property prices in Delhi, India, based on data scraped from MagicBricks.

## Project Description

The goal of this project is to perform an exploratory data analysis (EDA) on a dataset of Delhi house listings to identify key features that correlate with property prices. The analysis involves data cleaning, handling missing values, and visualizing relationships between different property attributes and the price.

## Dataset

The dataset used is `house pricing delhi- MagicBricks.csv`. It includes the following columns:

*   `Area`: Size of the property (likely in sq ft).
*   `BHK`: Number of Bedrooms, Hall, and Kitchen.
*   `Bathroom`: Number of bathrooms.
*   `Furnishing`: Furnishing status (Furnished, Semi-Furnished, Unfurnished).
*   `Location`: Specific locality within Delhi.
*   `District`: District in Delhi.
*   `Locality`: Detailed locality information (often includes descriptive text).
*   `Parking`: Number of parking spots.
*   `Status`: Property status (Ready to Move, Almost Ready).
*   `Transaction`: Transaction type (Resale, New Property).
*   `Type`: Property type (Apartment, Builder Floor).
*   `Per_Sqft`: Price per square foot.
*   `Price`: The final price of the property.

## Analysis Steps

The analysis was performed using Python and the following libraries:
*   `pandas` for data manipulation and analysis.
*   `numpy` for numerical operations.
*   `matplotlib.pyplot` and `seaborn` for static visualizations.
*   `plotly.express` for interactive visualizations.
*   `statistics` (though primarily standard pandas/numpy functions were used).

The key steps involved:

1.  **Data Loading:** The dataset was loaded from the provided CSV file into a pandas DataFrame.
2.  **Initial Data Exploration:**
    *   Viewing the first few rows (`df.head()`).
    *   Checking data types and non-null counts (`df.info()`).
    *   Generating descriptive statistics for numerical columns (`df.describe()`).
    *   Identifying columns with missing values (`df.isnull().sum()`).
3.  **Data Cleaning:**
    *   Calculated the percentage of missing values per column.
    *   Filled missing values in `Type` with its mode ('Builder_Floor').
    *   Filled missing values in `Parking` with its median (1.0).
    *   Filled missing values in `Bathroom` with its median (2.0).
    *   Filled missing values in `Per_Sqft` with a value close to its median (11000).
    *   Confirmed that all missing values were handled.
4.  **Exploratory Data Analysis (EDA):**
    *   Examined correlations between numerical features and the `Price`.
    *   Visualized the correlation of numerical features with `Price` using a bar plot.
    *   Analyzed the relationship between `Price` and categorical variables (`Furnishing`, `Status`, `Transaction`, `Type`, `District`, `Location`) through visualizations like pie charts and scatter plots colored by category.
    *   Calculated and visualized average prices based on the number of bathrooms, BHK, and District.
    *   Visualized the relationship between `Area` and `Price` using a scatter plot.
    *   Visualized the price distribution across different locations and property types.

## Key Findings (Conclusions)

Based on the analysis, the following key insights were drawn regarding Delhi house prices:

*   **Missing Data:** The dataset had missing values, particularly in the `Per_Sqft` column (around 20%), which were addressed by filling them with median values.
*   **Numerical Correlations:** `Price` showed strong positive correlations with the number of `Bathroom`s, `Area`, and `BHK`. `Parking` and `Per_Sqft` had weaker correlations in this dataset.
*   **Impact of Amenities:** The average price generally increases with the number of bathrooms and BHKs.
*   **Property Characteristics:** The type of property (`Apartment` vs `Builder_Floor`), transaction status (`New_Property` vs `Resale`), and furnishing status (`Furnished`, `Semi-Furnished`, `Unfurnished`) all influence the distribution of total property value.
*   **Geographical Influence:** Property prices vary significantly across different Districts and specific Locations within Delhi.
