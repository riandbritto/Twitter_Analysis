# 🐦 Twitter Influencer Engagement ROI Analysis

![Python](https://img.shields.io/badge/Python-3.8+-blue?logo=python)
![NLP](https://img.shields.io/badge/NLP-NLTK%20%7C%20TextBlob-green)
![Sentiment](https://img.shields.io/badge/Analysis-Sentiment%20%7C%20Keyword-yellow)
![Tableau](https://img.shields.io/badge/Viz-Tableau%20%2F%20Sankey-orange)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Score](https://img.shields.io/badge/Grade-12.5%20%2F%2015-blue)

> A data analytics and NLP project that categorizes Twitter influencers into 5 content categories, performs sentiment analysis and keyword extraction on 24,000+ tweets, and identifies which influencer category delivers the **highest engagement ROI** — measured by followers, retweets, and likes.

---

## 📌 Table of Contents
- [Project Overview](#project-overview)
- [Research Question](#research-question)
- [Dataset](#dataset)
- [Tech Stack](#tech-stack)
- [Project Workflow](#project-workflow)
- [Key Findings](#key-findings)
- [Visualizations](#visualizations)
- [How to Run](#how-to-run)
- [Project Structure](#project-structure)
- [Learnings & Takeaways](#learnings--takeaways)
- [Team](#team)

---

## Project Overview

Brands and marketers investing in influencer marketing face a critical question: **which type of influencer gives you the best return on your investment?** This project answers that question using a real Twitter dataset of 127 influencer accounts, 24,216 tweets, and 278,329 like records.

We applied **Natural Language Processing (NLP)** to classify influencers into 5 content categories, extracted trending keywords, ran **sentiment analysis** on tweet text, and built a **Sankey chart dashboard** to visualize how engagement flows from influencer category → followers/retweets/likes → trending topics.

**Final answer: The Creative category delivers the highest engagement ROI. The keyword "Python" emerged as the most engaging topic across the dataset.**

---

## Research Question

> **"Which category of influencers yields the maximum ROI in terms of engagement?"**

Engagement ROI is defined as the combined signal from:
- **Followers count** (reach)
- **Retweet count** (amplification)
- **Likes count** (resonance)

The goal is to help brands make data-driven decisions when selecting influencer partnerships — moving beyond follower count alone to true engagement impact.

---

## Dataset

**Source:** Twitter dataset provided via course (IE7275 — Data Mining in Engineering, Northeastern University)

The dataset consists of **5 linked CSV files**, all connected via `twitterUserId`:

| File | Records | Key Fields |
|---|---|---|
| **Users** | 127 | twitterUserId, name, profile, location, country, join_date |
| **Profile Snapshots** | 3,999 | followers_count, following_count, likes_count, tweets_count, checktime |
| **Tweets** | 24,216 | tweetId, text, favorite_count, retweet_count, lang, source, createdEastern |
| **Likes** | 278,329 | tweetId, twitterUserId, liking_twitterUserId, liking_username |
| **Followers** | 127 | twitterUserId, follower_twitterUserId, check_date |

### Scale Summary
- 👤 **127 unique influencer accounts**
- 🐦 **24,216 tweets** analyzed
- ❤️ **278,329 like interactions** tracked
- 📸 **3,999 profile snapshots** over time

---

## Tech Stack

| Tool | Purpose |
|---|---|
| **Python 3.8+** | Core language |
| **pandas & NumPy** | Data loading, cleaning, aggregation |
| **NLTK** | Natural Language Processing — tokenization, stopword removal, keyword extraction |
| **TextBlob** | Sentiment analysis (polarity scoring on tweet text) |
| **Matplotlib & Seaborn** | EDA charts — distributions, bar charts, topic frequency |
| **Tableau / Sankey Chart** | Interactive dashboard — influencer category → engagement flow |
| **PowerPoint** | Final presentation deck (`visuals_and_dashboard.pptx`) |

---

## Project Workflow

```
5 CSV Files (Users, Tweets, Likes, Followers, Profile Snapshots)
        ↓
1. Data Loading & Schema Mapping
   (join all files on twitterUserId)
        ↓
2. Data Cleaning
   (parse dates, handle nulls, standardize text fields)
        ↓
3. NLP — Influencer Categorization
   (NLTK: tokenize profile_card + tweets → assign 1 of 5 categories
    using trending keywords and topic modeling)
        ↓
4. Sentiment Analysis (TextBlob)
   (polarity score per tweet → aggregate by influencer category)
        ↓
5. Keyword Extraction (NLTK)
   (most frequent & most engaging keywords per category)
        ↓
6. Engagement ROI Calculation
   (followers × retweet_count × likes_count → ROI score per category)
        ↓
7. EDA & Visualization
   (Sankey chart, bar charts, sentiment chart, topic frequency chart)
        ↓
8. Dashboard Build (visuals_and_dashboard.pptx)
        ↓
9. Conclusion: Creative category = highest ROI | "Python" = top keyword
```

---

## Key Findings

### 🏆 Influencer Category ROI Ranking
| Rank | Category | Engagement Signal |
|---|---|---|
| 1 | **Creative** ✅ | Highest combined ROI across followers, retweets, and likes |
| 2–5 | Other categories | Lower engagement per follower ratio |

### 🔑 Top Keyword
> **"Python"** was identified as the single most engaging keyword across all tweets — generating the highest combined likes and retweet activity.

### 📊 Engagement Flow (Sankey)
- Influencer categories with more targeted, niche content (Creative) consistently outperformed broad or generic accounts
- Retweet amplification was the strongest differentiator between high-ROI and low-ROI categories
- Follower count alone was a **weak predictor** of engagement ROI — a smaller creative account often outperformed a larger generalist account

### 😊 Sentiment Analysis
- Sentiment polarity was analyzed across all 5 categories using **TextBlob**
- Categories with more positive sentiment in tweet text showed higher like engagement
- Negative sentiment tweets drove higher retweet counts (controversy amplification effect)

---

## Visualizations

| Visualization | What It Shows |
|---|---|
| **Sankey Chart** | Flow from influencer category → followers/retweets/likes → trending topics |
| **Category Bar Charts** | Engagement metrics broken down by influencer category |
| **Topic Frequency Chart** | Most discussed topics per influencer category |
| **Sentiment Analysis Chart** | Sentiment distribution across influencer categories |
| **Keyword Annotation** | Category-level keyword tags overlaid on visualizations |

> 📎 All visualizations are included in `visuals_and_dashboard.pptx`

---

## How to Run

### Setup
```bash
# 1. Clone this repo
git clone https://github.com/your-username/twitter-influencer-roi
cd twitter-influencer-roi

# 2. Install dependencies
pip install -r requirements.txt

# 3. Add the 5 CSV data files to the /data folder
#    (users.csv, tweets.csv, likes.csv, followers.csv, profile_snapshots.csv)

# 4. Launch Jupyter
jupyter notebook Twitter_Analysis.ipynb
```

### Requirements
```
pandas
numpy
matplotlib
seaborn
nltk
textblob
```

### NLTK Setup (run once)
```python
import nltk
nltk.download('punkt')
nltk.download('stopwords')
nltk.download('averaged_perceptron_tagger')
```

---

## Project Structure

```
twitter-influencer-roi/
│
├── Twitter_Analysis.ipynb          # Main analysis notebook
├── visuals_and_dashboard.pptx      # Final dashboard & presentation slides
├── data/
│   ├── users.csv                   # 127 influencer accounts
│   ├── tweets.csv                  # 24,216 tweets
│   ├── likes.csv                   # 278,329 like interactions
│   ├── followers.csv               # Follower relationships
│   └── profile_snapshots.csv       # Time-series profile metrics
├── requirements.txt                # Python dependencies
└── README.md                       # Project documentation
```

---

## Learnings & Takeaways

- **Follower count ≠ engagement ROI** — this project quantitatively confirms that niche, high-quality creative accounts consistently outperform large generalist accounts in actual engagement impact
- **NLP unlocks hidden signals** — classifying influencers by tweet content using NLTK gave far more nuanced categories than manual tagging or follower-count buckets
- **Sankey charts are powerful but complex** — they effectively show multi-step flows (category → engagement type → topic), but require careful width scaling to avoid misleading the audience
- **Sentiment drives different engagement types** — positive sentiment → likes; negative/controversial sentiment → retweets; this asymmetry has practical implications for content strategy
- **Keyword specificity matters** — "Python" outperforming broad keywords suggests that niche technical content builds more engaged communities than generic posts

---

## Future Improvements

- [ ] Expand influencer categorization beyond 5 categories using LDA topic modeling
- [ ] Add time-series analysis of follower growth vs. engagement rate over profile snapshot windows
- [ ] Apply more robust sentiment models (VADER or fine-tuned BERT) for improved accuracy
- [ ] Build an interactive Tableau dashboard with filterable influencer profiles
- [ ] Include network analysis of follower/following relationships to identify influencer clusters

---

## Team — Group: Incognito

| Name | NUID |
|---|---|
| **Rian D'Britto** | 002026598 |
| Poornika Jalavadi | 002021693 |

**University:** Northeastern University


---

*📧 Rian D'Britto — dbritto.r@northeastern.edu | [LinkedIn](https://linkedin.com/in/rian-dbritto) | [GitHub](https://github.com/rian-dbritto)*
