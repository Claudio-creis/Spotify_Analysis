# USA Spotify Streaming Analysis

## Summary

Analysis of the most streamed music in the US using Spotify API data. Tracks were evaluated by release timing, genre, tempo, key, collaboration status, and other audio features to identify patterns correlating with popularity.

## Objectives

- Determine temporal release patterns affecting popularity (year, month, weekday)
- Evaluate influence of collaboration presence on genre-based performance
- Quantify tempo and key distributions linked to popularity
- Establish genre-tempo-popularity interaction zones
- Visualize correlations using statistical plotting libraries

## Data Sources

- Spotify Web API: Used to retrieve track metadata and audio features
- Additional parsing of collaborators and genre strings required due to nested or stringified list structures
- https://www.kaggle.com/datasets/solomonameh/spotify-music-dataset

## Processing Steps

1. Parsed and cleaned collaborator and genre fields
2. Mapped detailed genres to a simplified set (pop, rock, hip hop, edm, reggaeton)
3. Created binary flags for collaboration presence
4. Categorized tempo ranges:  
   - Slow: 60–76 BPM  
   - Medium: 76–120 BPM  
   - Fast: >120 BPM  
5. Grouped and averaged data by genre, tempo, key, and time attributes
6. Filtered to most common keys and tempos to reduce noise

## Tools

- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- Spotipy (Spotify API client)

## Metrics

- Average popularity per group
- Track count per bar and axis label
- Distribution visualizations: bar charts, heatmaps
- Temporal tracking of genre popularity evolution

### Observations

## Overall Trends
- **Average popularity**: 75.79  
- **Hip hop and reggaeton** tracks have an average popularity **2.8% higher than pop**  
- **Track length**: Mean = 3.49 min, Median = 3.41 min  
- **Tempo (BPM)**: Mean = 121.4, Median = 120.0  
- **Most common release day**: **Friday (579 songs)** — 465 more than the next most common, **Thursday**
- There is a strong and statistically significant positive correlation between artist popularity and track popularity (r = 0.52), which aligns with expectations. Additionally, track duration shows a moderate, statistically significant influence on danceability (r = 0.20), suggesting that shorter or longer songs may affect perceived rhythm or movement potential. Notably, duration also correlates significantly with artist popularity, further indicating structural differences in tracks by more prominent artists.

---

## Genre and Collaborations
- Roughly **40% of top songs involve collaborations**
- **Average popularity with collaborators**: 76.07  
- **Without collaborators**: 75.6  
- **EDM (100%)** and **Rock (90%)** tracks predominantly feature solo artists, suggesting more defined individual styles (note: limited sample of top tracks only)  
- **Pop** follows with 65% solo tracks, indicating strong individual artist presence  
- **Hip hop** shows balance: ~50.5% of songs are solo  
- **Reggaeton** is heavily collaborative: only **27.5%** of songs are solo among the 8 most prominent artists  
  - _Possible reason: newer genre, cultural norms, slower average tempo_

---

## Tempo and Key
- The five most common keys: **0, 1, 5, 8, 11**  
- These dominate in tempos above **70 BPM**
- **Keys 1 and 5** are most frequent in top tracks

---

## Release Date and Weekday
- **August** is the peak release month (113 songs) and has the **highest average popularity** (marginally)
- **March**: Best performance for **Friday releases** (high count and high popularity)
- **November**: Inverse trend — fewer non-Friday releases, yet they outperform Friday ones in average popularity
- **1970–1980**: Friday was the dominant release day among top artists
- **1981–2003** (excluding 1984): Majority of top tracks released on non-Fridays
- In recent years: Volume of Friday releases has increased and popularity is balanced, but **Friday releases dominate in quantity**

---

## Shortcomings
- Further analysis could compare **independent vs. signed artists** in terms of release strategy and timing. 
- Larger datasets could shed more light into other parameters such as length and audio features




## Output

Relevant plots are annotated with song counts. Genres, tempos, and keys reduced to dominant segments to avoid dimensional bloat.

## Author

Claudio Creis

## File Structure

- `API.ipynb`: primary notebook containing data acquisition,
- `AnalysisAPI.ipynb`cleaning, transformation, analysis, and visualization
