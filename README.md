# kpop-youtube-network-analysis

## ARMY vs BLINK — Network Analysis of BTS and BLACKPINK YouTube Fan Communities

A social media and network analysis project comparing BTS (ARMY) and BLACKPINK (BLINK) fan communities on YouTube using network centrality, community detection, VADER sentiment analysis, and LDA topic modelling.


## Project Structure

```
kpop-youtube-network-analysis/
├── bts_blackpink_youtube_analysis.ipynb     # Main analysis notebook
├── outputs/
│   ├── plots/                               # Visualisation outputs
│   └── networks/                            # .gefx network files
└── README.md
```


## Research Question

How do BTS and BLACKPINK fan communities compare in terms of user influence, community structure, and sentiment on YouTube, and who are the key users bridging the two fandoms?


## Dataset

- **Source:** YouTube Data API v3 (collected May 2026)
- **Videos:** 10 official music videos per artist (20 total)
- **Raw comments:** 18,735 across both fandoms
- **After preprocessing:** 10,367 comments, 14,537 unique commenters

> **Note:** Raw comment data is not included in this repository in compliance with YouTube's Terms of Service. To reproduce the dataset, obtain a YouTube Data API v3 key from the [Google Cloud Console](https://console.cloud.google.com/) and run the data collection cells in the notebook. See [YouTube Data API v3 documentation](https://developers.google.com/youtube/v3) for setup instructions.


## Methodology

**Network Analysis**
- Directed weighted reply network constructed using NetworkX
- Three networks built: full network, BTS subgraph, BLACKPINK subgraph
- Centrality measures: PageRank, betweenness centrality, in/out-degree
- Community detection via Louvain algorithm

**NLP & Sentiment Analysis**
- Text preprocessing: lowercasing, URL/mention removal, NLTK stopwords + custom K-pop stopword list
- Sentiment analysis using VADER
- Topic modelling using LDA (5 topics per fandom)
- Word frequency analysis


## Key Findings

| Finding | Result |
|---|---|
| Bridge users | Only 33 users (0.4%) engaged with both fandoms — strong homophily |
| BTS top influencer | @bangtanokay — centralised influence structure |
| BLACKPINK influence | Distributed across multiple users |
| Sentiment (BTS) | 47% positive, 17% negative, avg score 0.214 |
| Sentiment (BLACKPINK) | 48% positive, 17% negative, avg score 0.211 |
| Top BTS word | "love" (413 occurrences) — emotionally expressive community |
| Top BLACKPINK word | "blinks" (561 occurrences) — fandom identity driven |

Both fandoms are near-identical in sentiment, challenging the popular narrative of intense rivalry. The ARMY–BLINK conflict on YouTube manifests as structural separation rather than active hostility.


## Network Statistics

| Metric | Full Network | BTS | BLACKPINK |
|---|---|---|---|
| Nodes | 7,936 | 4,115 | 3,821 |
| Edges | 5,980 | 3,047 | 2,876 |
| Communities detected | 1,958 | 1,070 | 946 |
| Largest community | 84 nodes | 53 nodes | 43 nodes |


## Requirements

```
pandas, numpy, matplotlib, seaborn
networkx, python-louvain
vaderSentiment, nltk
gensim, sklearn
google-api-python-client
```


## Authors

Lenisha Dsouza, Adril Vaz & Rohit Haridoss Nair — RMIT University, COSC 2671 Social Media and Network Analysis

