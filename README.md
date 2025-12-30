# nlp-final-research-note
Comparing Probabilistic (LDA) vs. Embedding-Based (BERTopic) Topic Modeling
📌 Project Overview
This project performs a comparative performance analysis between Latent Dirichlet Allocation (LDA) and BERTopic using the IMDB Movie Review dataset. The goal is to evaluate which methodology better captures the intersection of thematic content and sentiment polarity in subjective, evaluative text. This project was part of the final NLP project for the [Data Science for Public Policy]([url](https://www.hertie-school.org/en/study/study-master-of-data-science-for-public-policy?utm_source=google&utm_medium=cpc&utm_campaign=MDS_DE&utm_content=german&utm_term=datenwissenschaft%20studium&gad_source=1&gad_campaignid=22978373653&gbraid=0AAAAAC3lgWJaWexFczraKxNUS3uWtgWvx&gclid=Cj0KCQiA6sjKBhCSARIsAJvYcpNqRxGX1jF7ABnaf7LFG3lRA1946W0zqS-Dst4BjX_WBv3eKF9FiDkaArwwEALw_wcB)) master's programme at Hertie School, Berlin.

Key Research Question:

How do classical probabilistic topic models compare with modern transformer-based architectures in their ability to extract semantically coherent and sentiment-aligned themes?

Key Findings
Thematic Granularity: BERTopic successfully identified niche sub-genres (e.g., Gothic Horror, Rock Documentaries, Hitchcock Suspense) that were conflated into broad categories (e.g., Drama, Horror) by LDA.

Sentiment Alignment: BERTopic's clusters showed significantly higher polarization (e.g., Topic 0 at 84% negative), proving that contextual embeddings are superior at isolating "evaluative language" from "descriptive language."

Noise Handling: Through UMAP and HDBSCAN, BERTopic effectively filtered noise into an "Outlier" category (Topic -1), whereas LDA forced noise into existing thematic clusters.

Data Pipeline
Preprocessing: Tokenization, stop-word removal (using CountVectorizer with max_df=0.95), and text normalization.

LDA Implementation: Trained using scikit-learn to establish a classical bag-of-words baseline.

BERTopic Implementation: Leveraged Sentence-Transformers (all-MiniLM-L6-v2) for contextual embeddings, UMAP for dimensionality reduction, and HDBSCAN for clustering.

Sentiment Mapping: Cross-referenced extracted topics with ground-truth sentiment labels to calculate the "Sentiment Lean" for every identified theme.

Visualizations
The project generates several key visualizations included in the Appendix of the research note:

Grid Word Clouds: Side-by-side comparison of the "thematic fingerprint" of both models.

Sentiment Distribution: Proportional bar charts showing how topics lean positive or negative.

Token Length Distribution: Exploratory data analysis of the IMDB corpus.

Repository Structure
Bash
├── data/                   # Dataset (IMDB Movie Reviews)
├── notebooks/              # Jupyter Notebooks with full implementation
├── figures/                # Exported Word Clouds and Distribution plots
├── research_note.pdf       # The final typeset LaTeX report
├── requirements.txt        # Python dependencies
└── README.md
Installation & Usage
Clone the repo:

Bash
git clone https://github.com/Sattiki/nlp-final-research-note.git
cd nlp-final-research-note
Install dependencies:

Bash
pip install -r requirements.txt
Run the Analysis: Open the Jupyter notebook in notebooks/ to reproduce the LDA and BERTopic models.

📝 Statement on AI Transparency
This project utilized Google Gemini for technical assistance in optimizing the Python data pipeline and refining the LaTeX typesetting for the final research note. All analytical conclusions and thematic interpretations were manually verified by the author.

👤 Author
Sattiki Ganguly Data Science for Public Policy / Hertie School [LinkedIn]([url](https://www.linkedin.com/in/sattikiganguly/)) 
