# Twitter Influencer Analysis

A data visualization project exploring influencer engagement patterns on Twitter. The central research question: **which category of influencers yields the maximum engagement ROI?**

---

## Dataset

Five interrelated CSV files linked by `twitterUserId`:

| File | Records | Description |
|------|---------|-------------|
| `users.csv` | 127 | Core account info (handle, location, country, join date) |
| `profile_snapshots.csv` | 3,999 | Time-series snapshots of follower/following/likes/tweet counts |
| `tweets.csv` | 24,216 | Individual tweets with engagement metrics (favorites, retweets, replies, quotes) |
| `likes.csv` | 278,329 | Like relationships between accounts and tweets |
| `followers.csv` | 127 | Follower relationships between accounts |

All tables join on `twitterUserId`. See the schema diagram in `/docs` for full field descriptions.

---

## Project Structure

```
.
├── data/               # Raw CSV files
├── notebooks/          # Analysis and visualization code
├── visuals/            # Exported charts and figures
├── docs/               # Project brief, schema diagram, presentation slides
└── README.md
```

---

## Visualizations

- **Sankey chart** — flow from influencer categories to engagement metrics (followers, retweets, likes) and topic areas
- **Category bar charts** — engagement breakdown by influencer category
- **Topic frequency chart** — distribution of retweets/likes across topic clusters
- **Sentiment analysis** — display name categorization by sentiment

---

## Milestones

| Milestone | Date |
|-----------|------|
| Desk crits | Week of 2/26 |
| Project pinup | Week of 3/11 |
| Mid-term presentation | Week of 3/18 |

---

## Usage

1. Clone the repo and place the raw CSV files in `/data`
2. Run the notebooks in order inside `/notebooks`
3. Exported visualizations will be saved to `/visuals`

All code to reproduce the visualizations is included. Any post-processing done in external tools (e.g. Illustrator) is noted inline in the relevant notebook.

---

## Requirements

- Python 3.x
- Pandas, Matplotlib / Seaborn (or equivalent charting library)
- Any additional dependencies listed in `requirements.txt`
