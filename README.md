# Daily Quest: Data Analyst to AI Engineer 🚀

Welcome to my repository tracking my daily journey to mastering the core fundamentals of AI Engineering: **Data Analytics and Statistics**. 

While it's easy to get caught up in hyperparameter tuning and model architectures, true AI engineering requires a rock-solid foundation in data manipulation and translating business problems into clean, optimized code. This repository documents my daily quests to bridge that gap.

---

## 📅 Day 1 Challenge: Profit Margin Analysis

### The Business Problem
> **Prompt:** Find the top 5 products where the profit margin is more than 15% for "State A", given tables for Product, Location, and fact.

**The Strategy:** Instead of just writing syntax, this challenge focuses on converting standard business metrics ($\text{Profit Margin} = \frac{\text{Profit}}{\text{Revenue}}$) into structured logic: filtering out unwanted geographies first, aggregating revenue metrics, applying safe mathematical division, and isolating top performers.

---

## 🛠️ Technical Breakdown & Methods Used

This challenge was solved using two distinct approaches to mirror real-world production environments: **Relational SQL** and **Vectorized Python (Pandas/NumPy)**.

### 1. SQL Database Methods
The SQL implementation (`.sql`) leverages relational querying, conditional safety logic, and programmatic objects:
*   **Table Joins:** Traditional `JOIN` operations to bridge records across `Fact`, `Product`, and `Location` tables using shared keys (`Area_Code`, `ProductID`).
*   **Aggregation Functions:** `SUM()`, `COUNT()`, `MIN()`, `MAX()`, and `AVG()` for calculating dataset summaries.
*   **Grouping & Filtering Groups:** Using `GROUP BY` to aggregate metrics over subsets, paired with `HAVING` clauses to filter rows based on the calculated profit margins.
*   **Window Functions:** `DENSE_RANK() OVER (ORDER BY ...)` to create seamless, gapless rankings.
*   **Database Objects:** `CREATE PROCEDURE` and user-defined `CREATE FUNCTION` (inline table-valued functions) to build re-runnable query scripts.
*   **Conditional Logic & Set Operations:** `CASE WHEN` constructs for value flagging, alongside `UNION`, `INTERSECT`, and `ROLLUP` for advanced reporting/sub-totals.
*   **Data Modification & Manipulation:** `UPDATE ... SET` and `DELETE FROM` commands, alongside string operations like `SUBSTRING()` and `ASCII()`.

### 2. Python Data Manipulation Methods (Pandas & NumPy)
The Jupyter Notebook (`.ipynb`) replicates the database logic using high-performance data processing libraries:
*   **File I/O & Inspection:** `pd.read_csv()` to import datasets, paired with `.shape` and `.head()` for metadata sampling.
*   **Dataframe Filtering & Slicing:** Boolean indexing patterns and position/label locator structures (`.loc[]`, `.iloc[]`) to isolate specific states.
*   **Value Uniqueness:** Using `.unique()` and `.value_counts()` to identify unique categorical properties.
*   **Aggregation & Grouping:** Python equivalents of group rules using `.groupby()` connected directly to statistical methods (`.sum()`, `.mean()`, etc.).
*   **Merging DataFrames:** Using `pd.merge()` explicitly handling join operations (`how='left'`, `how='inner'`) to mimic relational joins.
*   **Conditional Array Manipulations:** Applying `np.where()` (NumPy conditional logic) and the Pandas `.apply()` method combined with custom Python functions to securely calculate metrics without division-by-zero errors.
*   **Datetime & Structural Modifications:** `pd.to_datetime()` for time-series extraction, `.sort_values()` for ranking, and `pd.concat()` for structural assembly.

---

## 📂 Repository Structure
*   `DataAnalytics_Case_Study_1_Questionnaire.pdf`: The detailed business prompt and context.
*   `Case1(fact,Product,Location).sql`: The optimized relational database query.
*   `Case1(fact,Product,Location).ipynb`: The step-by-step Pandas and NumPy implementation walkthrough.

---
*Connect with me on LinkedIn as I share my daily progression toward AI Engineering!*
