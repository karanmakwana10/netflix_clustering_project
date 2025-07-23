# netflix_clustering_project

Clustering Netflix Movies and TV Shows dataset (2019) using TF-IDF and KMeans to analyze content trends, genres, and recommendations.

# Netflix Movies and TV Shows Clustering

## Overview
This project explores and clusters the Netflix Movies and TV Shows dataset (2019) to uncover content trends and patterns.  
We analyze which types of content are popular, how Netflix has evolved over the years, and use **TF-IDF + KMeans clustering** to group similar titles based on descriptions and genres.  

The goal is to gain insights into Netflix's content strategy and demonstrate how clustering can be used for **recommendation systems** and **content segmentation**.

---

## Business Context
In 2018, Flixable reported that the number of TV shows on Netflix has nearly tripled since 2010, while movies have decreased by 2,000+ titles.  
This project answers questions like:
- What kind of content is most common in different countries?
- Is Netflix focusing more on TV shows than movies?
- Can we group similar content using clustering?

---

## Dataset
- **Source:** [Flixable](https://www.flixable.com/) (3rd-party Netflix search engine).
- **Size:** 7787 rows × 12 columns.
- **Columns:**
  - `show_id`: Unique ID.
  - `type`: Movie or TV Show.
  - `title`: Title of the content.
  - `director`: Director name(s).
  - `cast`: Main actors.
  - `country`: Country of origin.
  - `date_added`: Date when added to Netflix.
  - `release_year`: Year of original release.
  - `rating`: Content rating (e.g., PG, TV-MA).
  - `duration`: Movie duration (mins) or number of seasons.
  - `listed_in`: Genres.
  - `description`: Brief description.

---

## Key Steps
1. **Data Loading & Cleaning**
   - Handled missing values (`director`, `cast`, `country`, `rating`).
   - Extracted `year_added` and `month_added` from `date_added`.
   - Converted `duration` into numeric fields (`duration_min`, `duration_seasons`).

2. **Exploratory Data Analysis (EDA)**
   - Movies vs. TV shows.
   - Content addition trend over years.
   - Top countries and genres.
   - Rating distributions.

3. **Feature Engineering**
   - Combined `description` and `listed_in` into a `text_features` column.
   - Cleaned text and applied **TF-IDF vectorization** (5000 features).

4. **Clustering**
   - Used **Elbow Method** to find optimal K (K=5).
   - Applied **KMeans** clustering to group similar content.

5. **Insights**
   - Clusters represent different categories like romantic/comedy, documentaries, horror/thriller, kids content, etc.

---

## Insights
- Netflix is adding **more TV shows** than movies since 2015.
- **USA, India, and UK** dominate Netflix's content library.
- Most popular ratings are **TV-MA** and **TV-14**.
- Clustering groups similar titles, which can be used for **recommendation systems**.

---

## Results
- **5 clusters** were created using KMeans:
  - Cluster 0: Romantic & Comedy Movies.
  - Cluster 1: Documentaries & Biographical titles.
  - Cluster 2: Thriller & Horror Movies.
  - Cluster 3: Action/Drama TV Shows.
  - Cluster 4: Kids & Animated Content.

