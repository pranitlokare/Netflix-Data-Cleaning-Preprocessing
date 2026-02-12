## 📌 Objective

The primary objective of this project was to take a raw dataset of Netflix movies and TV shows
and transform it into a high-quality, structured format. By resolving issues like missing values,
inconsistent text casing, and non-standard date formats, to prepare it for
Exploratory Data Analysis (EDA) or visualization.

---

## 📁 Dataset Description

| Column | Description |
|--------|-------------|
| `show_id` | Unique identifier for every movie/show |
| `type` | Identifier (Movie or TV Show) |
| `title` | Name of the content |
| `director` / `cast` | Personnel involved *(contains high null counts)* |
| `country` | Production origin |
| `date_added` | The date content was uploaded to Netflix *(provided as raw text)* |
| `duration` | Time length *(mixed formats: minutes vs. seasons)* |
| `listed_in` | The genres or categories the title belongs to (e.g., `"Documentaries"`, `"International TV Shows"`) |

---

## 🛠️ Key Excel Formulas Used

| Task | Formula |
|------|---------|
| Remove Spaces | `=TRIM(A2)` |
| Standard Casing | `=PROPER(A2)` |
| Handle Nulls | `=IF(A2="", "Unknown", A2)` |
| Extract Month | `=MONTH(DATEVALUE(A2 & " 1"))` |
| Check Duplicates | `=COUNTIF(Range, Criteria)>1` |
| Reconstruct date from MDY format to proper DMY date | `=DATE(C2, MONTH(DATEVALUE(A2 & " 1")), B2)` |

> 💡 Where `A2` = Month, `B2` = Day, `C2` = Year
