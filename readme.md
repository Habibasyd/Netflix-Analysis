# 🍿 Netflix Data Analysis Project

This repository contains an exploratory data analysis (EDA) of a dataset featuring TV shows and movies available on Netflix up to 2021. The analysis was conducted using the **Pandas**, **Seaborn**, and **Matplotlib** libraries in Python.

## 🚀 Project Overview

The project involved cleaning the dataset, inspecting data quality, transforming columns for analysis, and extracting key insights about content trends, popular directors, release years, and content ratings.

### 💾 Dataset Snapshot

The primary DataFrame initially contained **7789 rows** and **11 columns**.

| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| **Show\_Id** | `object` | Unique ID for the title. |
| **Category** | `category` | Whether the title is a `Movie` or a `TV Show`. |
| **Title** | `object` | The title of the movie or show. |
| **Director** | `object` | Director(s) of the title. |
| **Cast** | `object` | Main actors/cast members. |
| **Country** | `object` | Country of production. |
| **Release\_Date** | `datetime64[ns]` | Date the title was added to Netflix. |
| **Rating** | `object` | TV rating/Maturity rating. |
| **Duration** | `object` | Runtime or number of seasons. |
| **Type** | `object` | Detailed genres/types. |
| **Description** | `object` | A brief summary. |

### 🛠️ Key Data Operations

* **Duplicate Removal:** 2 duplicate records were identified and removed, leaving **7787** unique records.
* **Missing Values:** Columns like `Director` (2388 nulls), `Cast` (718 nulls), and `Country` (507 nulls) contain missing data. This was visualized using a heatmap.
* **Feature Engineering:**
    * `Release_Date` was converted to datetime format, and a new `year` column was extracted.
    * `Duration` was split into two new columns: `length` and `unit` (min/Seasons).

## 📊 Analysis & Key Findings

### 1. Content Distribution

* **Content Split (Movies vs. TV Shows):**
    * **Movies:** 5377 titles.
    * **TV Shows:** 2410 titles.
    * *Conclusion: Movies significantly outnumber TV Shows in the dataset.*
* **Visualization:** (See accompanying chart for distribution)

### 2. Temporal Analysis

* **Highest Release Year:** The highest number of titles were released in **2019** (2153 titles).
* **Movies in 2000:** There were **no movies** released in the year 2000 in this dataset.

### 3. Directors, Cast, and Duration

* **Top 10 Directors:** The partnership of **Raúl Campos, Jan Suter** is the most prolific, directing **18** titles.
* **Tom Cruise:** After dropping rows with missing values, Tom Cruise was featured in **2 movies** (`Magnolia`, `Rain Man`).
* **Maximum Duration:**
    * Maximum Movie Length (in minutes): **99 minutes**.
    * Maximum TV Show Length (in seasons): **9 Seasons**.

### 4. Geographic and Rating Analysis

* **Highest TV Show Country:** The **United States** has the highest count of TV Shows, with **705** titles.
* **TV Shows from India:** There are **71** TV Shows exclusively from India, such as `Akbar Birbal` and `Typewriter`.
* **Rating Specific Filters:**
    * Movies with a 'TV-14' rating in 'Canada': **11 movies**.
    * TV Shows with an 'R' rating released after 2018: **1 TV Show**.

### 5. Complex Filtering

* **Question:** Find all instances where **(Category is 'Movie' AND Type contains 'Dramas')** OR **(Category is 'TV Show' AND Type contains 'Kids')**.
* **Result:** **2520 records** matched this criteria.

---
*Note: The Jupyter Notebook, `netflix_analysis (1).ipynb`, contains all the code and visual outputs (like the bar graphs and heatmap) that support these findings.*
