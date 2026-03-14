# nlp-poetry-lab

A series of NLP assignments exploring computational linguistics through poetry : from POS tagging and hybrid poem generation to topic modeling, knowledge graphs, and AI-based literary evaluation.

Built for CMPE-257 Machine Learning at SJSU under Prof. Ali Arsanjani (Google).  
**Team:** Ananya

[Quantified Aesthetics: IEEE Paper](./IEEE_paper.pdf)

## Repository Structure

```
nlp-poetry-lab/
│
├── 01_NLP_for_Poems.ipynb
│     Starter notebook — POS substitution intro with Edmund Spenser & Will Rout
│
├── 02_NLP_POS_Substitutions_and_Tones.ipynb
│     Tagore vs. Shakespeare — POS analysis, hybrid poem generation, tonal comparison
│
├── 03_NLP_Computational_Linguistics_4_Poets.ipynb
│     Extended analysis across 4 poets (Shakespeare, Tagore, Frost, Dickinson)
│     Includes 40 poems, 8 hybrid poems, semantic similarity scoring
│
├── 04_NLP_Gold_Standard_vs_Pedestrian.ipynb
│     AI Poetry Judge — 7-step pipeline to score poems on Pushcart Prize probability
│
├── 05_NLP_Knowledge_Graphs_and_Fractal_CoT.ipynb
│     Knowledge graph construction from poems + Fractal Chain-of-Thought evaluation
│
└── README.md
```


## Notebooks at a Glance

### 01 : NLP for Poems (Intro)
POS substitution intro using two poets. Covers scraping, tokenization, and building a foundation for later notebooks.

**Tech:** NLTK, BeautifulSoup, PoetryDB API


### 02 : POS Substitutions & Tones: Tagore vs. Shakespeare
Analyzes 20 poems (10 per poet) scraped from PoetryDB, extracts POS distributions, and generates hybrid poems by swapping vocabulary between poets while preserving syntactic structure.

**Key outputs:**
- POS frequency comparison (verbs, nouns, adjectives, adverbs)
- Hybrid poems: Shakespeare structure + Tagore vocabulary (and vice versa)
- Tonal analysis showing stylistic signatures

**Tech:** spaCy, NLTK, PoetryDB API, pandas


### 03 : Computational Linguistics: 4 Poets
Expanded group analysis across Shakespeare, Tagore, Frost, and Dickinson — 40 poems total, 10 per poet.

| Poet | Unique Verbs | Unique Nouns | Unique Adjectives |
|------|-------------|--------------|-------------------|
| Shakespeare | 377 | 606 | 240 |
| Tagore | 108 | 197 | 46 |
| Frost | 39 | 100 | 31 |
| Dickinson | 83 | 121 | 54 |

**Key outputs:**
- 8 hybrid poems with 4,000 word substitutions
- Semantic similarity scoring via Sentence Transformers (avg 0.29 across hybrids)
- Cross-era style comparison (e.g., Tagore vs. Dickinson: 0.36 similarity)
- 10x speed optimization using SequenceMatcher over semantic embeddings

**Tech:** NLTK, Sentence Transformers (all-MiniLM-L6-v2), BeautifulSoup, pandas, JSON


### 04 : Gold Standard vs. Pedestrian: AI Poetry Judge
A 7-step pipeline that assigns a **Pushcart Prize Probability Score (0–100%)** to any input poem.

**Pipeline:**

| Step | Description |
|------|-------------|
| 0 | Data scraping — Pushcart Prize nominees + Reddit r/OCPoetry (Gemini fallback) |
| 1 | POS statistical profiling — noun/verb ratio, adjective density |
| 2 | LDA topic modeling — detects clichéd vs. unexpected themes |
| 3 | Sentiment analysis — TextBlob polarity scoring |
| 4 | Delta calculation — formalizes Gold vs. Pedestrian gap |
| 5 | Generative AI qualitative analysis — Gemini 2.0 Flash |
| 6 | Fractal Chain-of-Thought — 3 recursive scoring iterations |
| 7 | Batch evaluation across labeled test set |

**Results:**

| Type | Avg. Score |
|------|------------|
| Gold Standard | 35% |
| Pedestrian | 2% |
| **Gap** | **17.5x** |

**Tech:** spaCy, TextBlob, Gensim LDA, Google Gemini 2.0 Flash, BeautifulSoup, Matplotlib, Seaborn


### 05 : Knowledge Graphs & Fractal Chain of Thought
Constructs knowledge graphs from poem text using entity extraction and semantic relationships via spaCy and NetworkX. Applies Fractal Chain-of-Thought prompting for deep multi-iteration literary evaluation via Gemini.

**Key outputs:**
- Entity-relationship graph from poetic text
- Wikipedia-enriched node context
- Multi-hop reasoning chains over poetic structure

**Tech:** spaCy (en_core_web_md), NetworkX, Google Gemini, Wikipedia API, Matplotlib


## Tech Stack

| Category | Tools |
|----------|-------|
| NLP | spaCy, NLTK, TextBlob |
| Topic Modeling | Gensim LDA |
| Semantic Similarity | Sentence Transformers (all-MiniLM-L6-v2) |
| Knowledge Graphs | NetworkX |
| Generative AI | Google Gemini 2.0 Flash |
| Scraping | BeautifulSoup, requests, PoetryDB API |
| Visualization | Matplotlib, Seaborn |
| Data | pandas, numpy, JSON |


## Getting Started

```bash
git clone https://github.com/<your-username>/nlp-poetry-lab.git
cd nlp-poetry-lab
pip install -r requirements.txt
```

Run notebooks in order (01 → 05) for the full progression. Each notebook is self-contained and can also be run independently.

**Requirements:**
```
spacy
nltk
textblob
gensim
sentence-transformers
networkx
google-generativeai
beautifulsoup4
requests
matplotlib
seaborn
pandas
numpy
wikipedia
```


## Key Findings

- **Vocabulary richness as stylistic signature:** Shakespeare's adjective vocabulary is 5x richer than Tagore's, quantifiably reflecting his ornate style.
- **POS ratios predict literary quality:** Prize-winning poems use fewer adjectives (2.0 vs. 3.6) and more balanced noun-to-verb ratios (1.63 vs. 1.98).
- **Hybrid generation preserves coherence:** Average semantic similarity of 0.29 across 8 hybrid poems confirms style transforms while meaning holds.
- **Fractal CoT improves scoring precision:** 3-iteration recursive evaluation captures nuance that single-pass prompting misses.
- **Literary quality is quantifiable:** 17.5x score gap between Gold Standard and Pedestrian poems validates the AI judge framework.


## Academic Context

**Course:** CMPE-257 Machine Learning, SJSU MS Computer Science (Fall 2025)  
**Instructor:** Prof. Ali Arsanjani (Google)    
**Scope:** 5 assignments across 9 weeks — NLP, generative AI, knowledge graphs
