# Match Load & Performance Decline in Football
### Project Description

This project analyzes whether accumulated match load leads to performance decline in the last 15 minutes (76’–90’) of professional football matches.
It combines concepts from sports science (load, fatigue, recovery) and research methods with open football data.

### Scientific Question (SQ)
Does accumulated match load reduce performance in the final 15 minutes of professional football matches?

- Population: Professional football teams (example: Premier League 2022–23).

- Intervention (Exposure): Match load — minutes played in the last 7–14 days, rest days, fixture congestion.

- Measurement (Outcome): Performance decline proxy — shots and/or xG in the last 15 minutes compared to earlier periods.

---

### Methods and Approach
1. Data Collection
   - Match-by-match 15 minute splits (shots, goals, xG)
   - Player minutes per game -> compute rolling load (last 7-14 days)
   - Fixture dates -> calculate rest days and congestion
2. Feature Engineering
   - decline_ration = (shots_76_90) / mean (shots_0_75)
   - Load variables: minutes_last_7, minutes_last_14, rest_days, matches_last_7
3. Analysis
   - Descriptive statistics (distribution of decline ratio)
   - Group comparisons: congestion levels vs decline
   - Simple regression: decline_ratio ~ load variables.
4. Visualization
   - Boxplot: decline ratio by matches in last 7 days
   - Scatterplot: rest days vs decline ratio
   - Example match profile (shots/xG per 15 minutes)
  
### Repository Structure
match-load-performance-decline/
├─ data/
│  ├─ raw/            <- original CSVs from FBref/StatsBomb
│  └─ processed/      <- cleaned & engineered datasets
├─ notebooks/
│  ├─ 01_data_collection.ipynb
│  ├─ 02_feature_engineering.ipynb
│  ├─ 03_analysis_plots.ipynb
│  └─ 04_report_tables.ipynb
├─ src/
│  ├─ load_data.py
│  ├─ make_features.py
│  └─ utils.py
├─ figures/
│  ├─ decline_by_congestion.png
│  ├─ rest_days_vs_decline.png
│  └─ example_match_profile.png
├─ README.md
└─ LICENSE

### Deliverables
- Clean dataset with load & performance features
- Visualizations of performance decline vs match load
- Short summary of findings (2–3 bullet points)

### Limitations
- No direct tracking data (e.g., sprint distance). Shots/xG used as proxies.
- Single league/season for scope.
- Results are exploratory, not predictive.
