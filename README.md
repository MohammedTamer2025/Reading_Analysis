# What Predicts Reading Behavior?

A data-driven analysis of reading habits among 2,832 Americans, exploring how demographics like education, income, age, and gender predict reading behavior.

## Files

| File | Description |
|------|-------------|
| `Books_Analysis.ipynb` | Main analysis notebook — run this to reproduce all findings |
| `BigML_Dataset_5f50a62795a9306aa200003e.csv` | Raw survey dataset (loaded directly by the notebook) |
| `books_cleaned.csv` | Pre-cleaned version of the dataset (optional use) |
| `Books.ipynb` | Original junior analyst notebook (preserved, not modified) |
| `Presentation.md` | 10-slide presentation in Markdown format |

### Generated Charts

| Image | Description |
|-------|-------------|
| `ch1_demographics.png` | Demographic distributions |
| `ch2_reader_types.png` | Reader type breakdown |
| `ch3_age_reading.png` | Age vs. reading |
| `ch3_education_reading.png` | Education vs. reading |
| `ch3_gender_reading.png` | Gender vs. reading |
| `ch3_income_reading.png` | Income vs. reading |
| `ch3_employment_reading.png` | Employment vs. reading |
| `ch4_formats.png` | Reading format preferences |
| `ch4_acquisition.png` | Book acquisition methods |
| `ch4_supplementary.png` | Supplementary media consumption |
| `ch5_feature_importance.png` | Logistic regression feature importance |

## Setup

Requires Python 3.10+ with the following packages:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

## Usage

```bash
jupyter notebook Books_Analysis.ipynb
```

Run all cells to reproduce the analysis, charts, and model results.

## Key Findings

1. **80% of Americans** read at least one book last year (median: 6 books)
2. **Education is the #1 predictor** — post-grads read ~2x more than HS dropouts
3. **Income correlates** — higher earners read more
4. **Women read more** — 19.7 vs 13.4 books/year for men
5. **Seniors (65-74) read the most** — non-linear age relationship
6. **Printed books dominate** (93%), but 33% use e-books and 16% use audiobooks
7. **Logistic regression** can predict heavy readers from demographics alone

## Data Preprocessing

The notebook performs these cleaning steps on the raw CSV:

- Fixed 1 data entry error in income (`9$100,000 to...` → `$100,000 to...`)
- Renamed columns from `Column Name` to `column_name` (snake_case)
- Filled 58 missing Education values with mode ("High school graduate")
- Set 390 missing reading columns to 0 for non-readers, imputed others with median by education
- Removed 4 duplicate rows
- Ran IQR outlier detection (capped at upper fence)
