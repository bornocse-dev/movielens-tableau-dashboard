# MovieLens Ratings Dashboard | Tableau Portfolio Project

An interactive Tableau dashboard exploring movie ratings, genre performance, and user engagement using the MovieLens dataset.

![Dashboard Preview](dashboard_preview.png)

## 📊 Project Overview

This project analyzes ~100,000 user ratings across ~9,700 movies to answer a few core questions:
- Which genres tend to be rated highest on average?
- Which specific movies are the most acclaimed (with enough ratings to be credible)?
- How are ratings distributed overall — are users generous or harsh raters?
- Who are the platform's most active users, and how do they rate?

## 🗂️ Dataset

**Source:** [MovieLens Latest Small (GroupLens / Kaggle)](https://www.kaggle.com/datasets/grouplens/movielens-latest-small)

The raw data includes ~100,836 ratings and ~3,683 tags across 9,742 movies from 610 users.

Sheets used:
| Sheet | Description |
|---|---|
| `movies.csv` | movieId, title, genres |
| `ratings.csv` | userId, movieId, rating, timestamp |
| `tags.csv` | userId, movieId, tag, timestamp (referenced, not joined) |

**Join:** `ratings` → `movies` on `movieId` (inner join), so every rating carries its movie's title and genre.

## 🛠️ Tools Used

- **Tableau Public** — data visualization and dashboard design
- **Tableau Calculated Fields** — genre splitting (pipe-delimited field), rating count filter logic
- **Excel/CSV** — source data prep

## 📈 Dashboard Highlights

**1. Average Rating by Genre**
Bar chart comparing average rating across all 19 genres, color-coded by genre. Reveals that niche genres (Documentary, Film-Noir) tend to skew higher-rated than mainstream ones like Action or Comedy — likely a self-selection effect, since people who watch niche films are already inclined to like them.

**2. Top 10 Highest-Rated Movies**
Filtered to movies with 50+ ratings to avoid single-vote outliers skewing the ranking, then ranked by average rating. Classics like *Apocalypse Now*, *Casablanca*, and *The Godfather* dominate the list — a good sanity check that the filtering logic worked as intended.

**3. Rating Distribution**
Histogram binning all ~100K ratings in 0.5-star increments. The vast majority of ratings cluster in the 3–4.5 star range, showing users lean toward positive ratings rather than a normal distribution centered on 2.5.

**4. Most Active Users**
Stacked bar chart of the top-10 most prolific raters by user ID, colored by genre, showing not just *how much* each user rated but *what* they tend to watch.

## 🔗 Key Insights

- Ratings skew positive — most users rate movies 3 stars or higher, so a "5-star" average scale in practice behaves more like a 2.5–5 scale.
- Reliability matters: without the 50+ rating filter, several obscure films with a single 5-star vote would have outranked genuine classics.
- The most active users aren't necessarily genre specialists — several rate broadly across Action, Drama, and Sci-Fi rather than sticking to one lane.

## 🚀 View the Dashboard

**Tableau Public:** *[add your published link here]*

## 📁 Repo Structure

```
movielens-tableau-dashboard/
├── data/
│   ├── movies.csv
│   ├── ratings.csv
│   └── tags.csv
├── dashboard_preview.png
└── README.md
```

## 👤 Author

Borno — [GitHub](https://github.com/bornocse-dev)
