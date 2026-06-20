# Netflix Content Analysis (EDA)

Exploratory data analysis on Netflix's movie and TV show catalog (8,807 titles), looking at how content type, country of origin, release year, and audience rating break down across the platform.

## Business Question
Is Netflix's catalog still primarily a movie platform, and how does its content mix differ by country and audience rating? This matters for understanding content strategy trends — e.g. whether international growth is being driven by TV Shows rather than Movies.

## Dataset
- Source: [Netflix Movies and TV Shows — Kaggle](https://www.kaggle.com/datasets/shivamb/netflix-shows) (`netflix_titles.csv`, included here as `netflix_movie_tvshow.csv`)
- 8,807 rows × 12 columns: `show_id`, `type`, `title`, `director`, `cast`, `country`, `date_added`, `release_year`, `rating`, `duration`, `listed_in`, `description`
- Movies: 6,126 · TV Shows: 2,664

## Repo Structure
```
├── Netflix_Project.ipynb        # Main analysis notebook (cleaning + EDA + charts)
├── netflix_movie_tvshow.csv     # Raw dataset
├── EDA--NETFLIX.pdf             # Pre-rendered notebook output (quick view, no need to run code)
├── Netflix_Project_Final.pptx   # Slide summary of findings
├── requirements.txt
└── README.md
```

## How to Run
```bash
git clone https://github.com/rumman49/Netflix-Data-Analysis-Python.git
cd Netflix-Data-Analysis-Python
pip install -r requirements.txt
jupyter notebook Netflix_Project.ipynb
```
Run all cells top to bottom — the notebook reads `netflix_movie_tvshow.csv` directly from this folder.

If you just want to see the results without running anything, open `EDA--NETFLIX.pdf`.

## Methodology
1. **Load & explore** — shape, dtypes, null counts, duplicate check.
2. **Clean** — fill missing `director`/`cast`/`country` with explicit placeholders; drop the small number of rows with missing `rating`, `duration`, or `date_added` (too few to impute without distorting the distribution).
3. **Analyze & visualize** — content type split, country-wise breakdown, release year trend, top ratings.

## Key Findings
- Movies make up ~70% of the catalog (6,126 vs. 2,664 TV Shows).
- The US leads in total content count, but several countries (Japan, South Korea) skew TV-Show-heavy rather than movie-heavy — content mix differs by market, not just volume.
- The bulk of the catalog was added/released after 2015, consistent with Netflix's international expansion period rather than a deep historical archive.
- TV-MA is the single most common rating (~51%), indicating the catalog leans toward adult content over family programming.

## Tools Used
Python, Pandas, NumPy, Matplotlib, Seaborn, Jupyter

## Possible Extensions
- Break down `listed_in` (genre) for a content-mix view.
- Cross `country` × `release_year` to see how international content investment evolved over time.

## Author
Romaan Uddin Siddiqui
