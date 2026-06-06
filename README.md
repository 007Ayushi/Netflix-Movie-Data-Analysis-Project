# 🎬 Netflix Movie Data Analysis

A comprehensive Exploratory Data Analysis (EDA) project on a Netflix movie dataset using Python. This project uncovers insights about genre distribution, movie popularity, vote averages, and release trends.

---

## 📁 Dataset

- **File:** `mymoviedb.csv`
- **Records:** 9,827 movies
- **Columns:** 9 (Release_Date, Title, Overview, Popularity, Vote_Count, Vote_Average, Original_Language, Genre, Poster_Url)

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| Python 3 | Core language |
| Pandas | Data manipulation |
| NumPy | Numerical operations |
| Matplotlib | Plotting |
| Seaborn | Statistical visualization |
| JupyterLab | Development environment |

---

## 📊 Project Workflow

### 1. Data Loading & Exploration
- Loaded dataset using `pd.read_csv()`
- Inspected shape, dtypes, and sample records with `head()`, `info()`, `describe()`
- Confirmed **zero duplicate rows** and **zero null values**

### 2. Data Cleaning & Preprocessing
- Converted `Release_Date` from string → `datetime64` → extracted **year** (int32)
- Dropped irrelevant columns: `Overview`, `Original_Language`, `Poster_Url`
- Final working columns: `Release_Date`, `Title`, `Popularity`, `Vote_Count`, `Vote_Average`, `Genre`

### 3. Feature Engineering
- **Vote_Average Categorization:** Built a reusable `categorize_col()` function using `pd.cut()` with quartile-based bin edges to label movies as:
  - `not_popular` | `below_avg` | `average` | `popular`
- **Genre Exploding:** Split comma-separated genre strings and exploded the DataFrame to one genre per row — expanding from **9,827 → 25,552 rows**
- Cast `Genre` column to `category` dtype (19 unique genres)

### 4. Data Visualization

#### Most Frequent Genre
> **Drama** is the most common genre with **3,715 entries**

#### Genre Distribution (Bar Chart)
Top genres by frequency:
1. Drama
2. Comedy
3. Action
4. Thriller
5. Adventure

#### Votes Distribution (Bar Chart)
Vote categories are nearly evenly distributed (~2,400–2,467 each), indicating a balanced dataset across popularity tiers.

#### Release Date Distribution (Histogram)
Movie releases show a strong upward trend toward recent years, with the highest concentration in the most recent decade.

### 5. Popularity Analysis
- **Most Popular Movie:** Spider-Man: No Way Home (2021) — Popularity: 5083.954, Genre: Action/Adventure/Science Fiction
- **Least Popular Movie:** The United States vs. Billie Holiday (2021) — Popularity: 13.354, Genre: Music/Drama/History

---

## 💡 Key Insights

- Drama dominates Netflix's catalog, followed by Comedy and Action
- Recent years (2010s–2020s) account for the majority of content
- Vote averages are evenly distributed across the 4 popularity tiers
- High-popularity films tend to span multiple action-oriented genres

---

## 🚀 How to Run

```bash
# Clone the repository
git clone https://github.com/007Ayushi/Netflix_Movie_DataAnalysis.git

# Install dependencies
pip install pandas numpy matplotlib seaborn jupyter

# Launch Jupyter
jupyter lab Netflix_Movie_DataAnalysis.ipynb
```

---


## 👩‍💻 Author

**Ayushi Gupta**  
GitHub: [@007Ayushi](https://github.com/007Ayushi)
