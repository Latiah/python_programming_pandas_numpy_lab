
# TMDB Movie Data Analysis Pipeline

A comprehensive data analysis pipeline built with **Python** and **Pandas** that extracts, cleans, and analyzes movie data from **The Movie Database (TMDB) API**.

##  Project Overview
This project investigates the performance of a **predefined sample size** of movies by transforming raw, **nested JSON-like fields** into a structured analytical framework. It utilizes **feature engineering** to compare **Franchise vs. Standalone** performance and evaluates **Director success** through various **performance indicators**.

##  Technical Stack
*   **Language:** Python
*   **Libraries:** 
    *   **Pandas:** Data manipulation, **aggregation**, and transformation.
    *   **NumPy:** Handling missing data (**NaN**) and numerical operations.
    *   **Matplotlib:** Data visualization and trend analysis.
    *   **Requests:** **API data extraction**.

##  Methodology

### 1. Data Cleaning & Transformation
*   **API Extraction:** Fetched data using the TMDB API, utilizing `append_to_response=credits` to retrieve metadata.
*   **JSON Flattening:** Transformed **nested JSON-like fields** (Genres, Production Companies, Spoken Languages) into pipe-separated strings.
*   **Normalization:** 
    *   Converted budget and revenue to **Million USD (MUSD)** for consistent scaling.
    *   Handled unrealistic values (0 budget/revenue) by converting them to **NaN**.
    *   Converted date columns to appropriate **datetime** objects.

### 2. Feature Engineering & KPI Implementation
Two primary financial metrics were engineered to assess **financial efficiency**:
*   **Profit** = Revenue - Budget
*   **ROI (Return on Investment)** = Revenue / Budget
*   Developed a **User-Defined Function (UDF)** to rank movies across ten unique **performance indicators** (Highest Revenue, Highest ROI, Most Voted, etc.).

### 3. Advanced Filtering & Aggregation
Implemented complex boolean indexing to perform multi-variable **search queries**, identifying specific actor-director pairings. Data was further processed through **aggregation** to compare the success of movie collections versus standalone films.

##  Key Performance Insights
*   **Financial Efficiency:** While some films recorded the **Highest Budget**, others achieved superior **ROI**, proving that high production expenditure does not strictly correlate with financial margins.
*   **Franchise Dynamics:** Franchise movies benefit from significantly higher **Mean Popularity** and **brand recognition**, yet standalone movies in this sample exhibited higher **Median ROI**.
*   **Collection Success:** The **Avengers Collection** emerged as the most successful **aggregation** by total revenue.

##  Visualizations
The project utilizes **Matplotlib** to examine relationships within the dataset:
*   **Scatter Plots:** Investigating the correlation between **Revenue and Budget** and **Popularity versus Rating**.
*   **Box Plots:** Analyzing **ROI distributions** across different genres.
*   **Line Charts:** Visualizing **yearly trends** in box office performance.
*   **Bar Charts:** Comparing **Mean Revenue** and **Mean Budget** for Franchise vs. Standalone success.

##  Limitations
*   **Sample Size:** Analysis is restricted to a **predefined sample size** of 18 movies.
*   **Economic Factors:** Revenue and budget values were not **adjusted for inflation**.
*   **Scope:** Profit calculations exclude marketing, distribution, and other production-related expenses.


---

### How to Run
1. Clone the repository.
2. Install dependencies: `pip install pandas matplotlib requests`.
3. Add your TMDB API Key to the configuration variable.
4. Execute the Jupyter Notebook.
