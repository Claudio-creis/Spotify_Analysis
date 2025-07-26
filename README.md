# US Spotify Streaming Analysis

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

## Observations



## Output

Relevant plots are annotated with song count. Genres, tempos, and keys reduced to dominant segments to avoid dimensional bloat.

## Author

Claudio Creis

## File Structure

- `API.ipynb`: primary notebook containing data acquisition,
- `AnalysisAPI.ipynb`cleaning, transformation, analysis, and visualization
