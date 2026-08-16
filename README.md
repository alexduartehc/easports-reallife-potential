# EA FC Ratings vs. Real-Life Performance
 
Do EA Sports FC (FIFA) player ratings actually track how players perform on the pitch? This project merges EA Sports FC 23 player attribute data with real 2022–23 season statistics for Europe's top five leagues (Premier League, La Liga, Bundesliga, Serie A, Ligue 1), then analyzes where a player's in-game **potential** rating lines up — or doesn't — with their real-world output.
 
## What's in the notebook
 
`RealLife-Potential.ipynb` walks through the full pipeline:
 
- **Data cleaning & preprocessing** — dropping irrelevant columns, handling missing values, fixing data types, de-duplicating, and standardizing club/stat naming
- **Merging** — matching players across the two datasets by name using fuzzy string matching (`rapidfuzz`), since names aren't formatted consistently between sources
- **Feature engineering** — performance metrics, potential-vs-performance differentials, position-specific metrics, and interaction/ratio features
- **Analysis** — descriptive stats, goals by position, segmenting players by EA potential tier, identifying over- and under-performers (overall and by position), age-group trends, positional analysis, league comparisons, a correlation matrix, contract-year effects on performance, and an interactive Plotly visualization
- 
## Data
 
The notebook expects two source files:
 
- **EA Sports FC player database** — attribute and potential ratings export (FIFA 23)
- **2022–23 season stats** — advanced on-pitch statistics (shooting, passing, defense, goalkeeping, etc.) for the top five European leagues

## Conclusions

#### 1. **Key Findings**
   - *Are high-potential players performing better in real life?* Players with a higher potential than 85 have a higher performance index and this index is based on positional metrics. The median for the "High Potential" group is significantly higher than the median for the "Lower Potential" group.

   - *Which players are overperforming their potential?* Most of the players who over performed had a lower potential and this is expected because players with a higher rating most likely had the correct potential assigned to them.  
      
   - *Are younger players (under 23) living up to their potential?* There is a positive correlation between EA Potential Rating and Performance Index for players below 23 years, indicating that players with higher potential ratings tend to have better overall performance. This shows that most of the young players are living up to their potential and the ones with low performance index could be caused by them having limited playing time.

## Limitations and Considerations

The analysis was based on a single season’s data (2022/2023), which may limit the generalizability of findings over time. Additionally, the sample size of players is constrained to the top five European leagues, potentially excluding emerging talents from less prominent leagues that might offer further insights into player potential and performance. 

Real-life player performance is highly dynamic and can fluctuate due to various factors such as team strategy changes, coaching adjustments, or individual form. Additionally, injuries or off-field issues can cause inconsistencies that are not reflected in a single-season analysis.
 
## Tech stack
 
- Python (pandas, numpy)
- rapidfuzz — fuzzy name matching across datasets
- seaborn, matplotlib, plotly — static and interactive visualization

## Getting started
 
```bash
git clone <your-repo-url>
cd easports-reallife-potential
pip install -r requirements.txt
jupyter notebook RealLife-Potential.ipynb
```
 
## Repo structure
 
```
.
├── RealLife-Potential.ipynb   # full analysis notebook
├── requirements.txt
├── data folder
└── README.md
```
