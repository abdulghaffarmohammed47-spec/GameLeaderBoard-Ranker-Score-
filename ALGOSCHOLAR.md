<div align="center">

# AlgoScholar

### Find the signal in a sea of research.

An interactive research-paper discovery system that brings together ranked search,
paper relationships, analytics, and hands-on algorithm demos.

[![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/Flask-3.0.3-000000?logo=flask&logoColor=white)](https://flask.palletsprojects.com/)
[![DSA](https://img.shields.io/badge/Focus-Data%20Structures%20%26%20Algorithms-7C3AED)](#algorithm-lab)
[![Repository](https://img.shields.io/badge/GitHub-A5__DSA--3__G4-181717?logo=github)](https://github.com/abdulghaffarmohammed47-spec/A5_DSA-3_G4)

</div>

---

## Explore

| Search | Citation Graph | Analytics | Algorithm Lab |
|:--|:--|:--|:--|
| Discover and rank papers by topic, keywords, or methods. | Explore an interactive, query-focused network of related papers. | Inspect graph statistics, PageRank distributions, and publication trends. | Experiment with editable examples of the algorithms behind the system. |

## What makes it different?

- **Hybrid ranking:** combines BM25 retrieval with fuzzy text alignment, graph importance, recency-aware trend scores, and a prefix-scan boost.
- **More than keyword matching:** Aho-Corasick finds query terms across candidate papers, while Smith-Waterman helps surface partial text matches.
- **Connected discovery:** the graph, metrics, and timeline can be scoped to a search query.
- **Built to explore:** the Algorithm Lab includes live demos, and result cards explain ranking signals.
- **Local-first data:** paper records are loaded from CSV files in `data/` when the Flask app starts.

> **About the graph:** the supplied dataset does not include paper-reference lists. The app builds a *keyword- and year-based relationship graph* instead; its PageRank and graph measures describe that modeled network, not verified scholarly citations.

## Get started

### Requirements

- Python 3.8 or newer
- pip
- Internet access for the D3.js v7 library used by the interactive graph

### Run locally

```powershell
git clone https://github.com/abdulghaffarmohammed47-spec/A5_DSA-3_G4.git
cd A5_DSA-3_G4

python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
python main.py
```

Open **http://127.0.0.1:5000** in your browser. The development server runs on port `5000`.

## Algorithm Lab

| Algorithm | Role in AlgoScholar |
|:--|:--|
| BM25 | Base relevance ranking for paper search |
| Aho-Corasick | Multi-keyword matching |
| Suffix array + Kasai LCP | Suffix and repeated-substring exploration |
| Wagner-Fischer | Edit distance and string similarity |
| Smith-Waterman | Local text alignment and fuzzy relevance |
| PageRank | Importance scoring in the modeled paper graph |
| Dinic's algorithm + min-cut | Maximum-flow and graph-partition demos |
| Hopcroft-Karp | Bipartite matching demo |
| Vertex Cover 2-approximation | Approximate cover selection |
| Greedy Set Cover | Diverse result selection |
| Reservoir Sampling | Streaming sample selection |
| Blelloch Scan | Parallel prefix-sum primitive used in ranking |

## Dataset

The included `data/papers.csv` contains 5,000 paper records. CSV files placed in `data/` are discovered on startup; the loader uses the first alphabetically sorted CSV file.

| Column | Description |
|:--|:--|
| `PaperID` | Paper identifier |
| `Title` | Paper title |
| `Authors` | Author names |
| `Abstract` | Paper abstract |
| `Keywords` | Comma-separated keywords |
| `Year` | Publication year |
| `CitationCount` | Citation-count value supplied with the dataset |

## API

| Method | Endpoint | Purpose |
|:--|:--|:--|
| `POST` | `/api/recommend` | Search and rank papers; JSON body: `{"query": "..."}` |
| `GET` | `/api/graph?query=...&n=200` | Return a query-scoped graph |
| `GET` | `/api/metrics?query=...` | Return graph metrics and distributions |
| `GET` | `/api/trends?query=...` | Return publication and citation-count timeline data |
| `GET` | `/api/papers` | Return the loaded paper records |
| `GET` | `/api/keywords/top?n=12` | Return the most frequent keywords |
| `POST` | `/api/lab/<algorithm>` | Run an Algorithm Lab demo |

## Project layout

```text
.
├── app.py                 # Flask routes, ranking, graph, and algorithms
├── main.py                # Local development entry point
├── requirements.txt       # Python dependencies
├── data/
│   └── papers.csv         # Research-paper dataset
├── static/
│   ├── graph.js           # Interactive graph and visualizations
│   ├── script.js          # Search, analytics, and lab interactions
│   └── style.css          # Application styling
└── templates/
    └── index.html         # Single-page application
```

## Built with

**Python · Flask · Vanilla JavaScript · D3.js · HTML · CSS**

---

<div align="center">
Made for exploring research through algorithms.
</div>
