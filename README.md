Air Quality Monitoring & Management System

Air Quality Monitoring & Management System provides an end-to-end pipeline for ingesting, cleaning, clustering, mining frequent patterns, and visualizing air-quality data. Built for students and researchers who want an interactive dashboard + analytics pipeline to explore pollutant patterns and cluster air-quality regimes.

🚀 Quick links

Repository: https://github.com/saniyapathan1606/Air-Quality-Monitoring-and-Management-System

Dashboard: streamlit_app.py (run locally with Streamlit)

🔍 Features

Data ingestion & preprocessing (handle missing values, feature extraction)

Clustering (K-Means by default; easily swap algorithms)

Frequent pattern mining (Apriori / association rules on clustered data)

Interactive visualization via Streamlit

Exports: clustered datasets, saved model (.pkl), and reports

📁 Repository structure
Air-Quality-Monitoring-and-Management-System/
├─ data/
│  ├─ station_day.csv            # core dataset (example)
├─ models/
│  ├─ air_quality_kmeans.pkl     # trained clustering model (pickle)
├─ notebooks/
│  ├─ EDA_and_modeling.ipynb
├─ src/
│  ├─ preprocessing.py
│  ├─ clustering.py
│  ├─ frequent_patterns.py
│  ├─ utils.py
├─ streamlit_app.py
├─ main.py                       # orchestrates pipeline
├─ requirements.txt
├─ README.md


If your repo differs slightly, update paths accordingly.

🧰 Prerequisites

Python 3.7+

pip (or use conda / virtualenv)

Recommended: create a virtual environment

⚙️ Install & Setup

Clone the repo:

git clone https://github.com/saniyapathan1606/Air-Quality-Monitoring-and-Management-System.git
cd Air-Quality-Monitoring-and-Management-System


(Optional) Create & activate a venv:

python -m venv venv
# macOS / Linux
source venv/bin/activate
# Windows (PowerShell)
.\venv\Scripts\Activate.ps1


Install dependencies:

pip install -r requirements.txt

▶️ Run the full pipeline

Run preprocessing → clustering → frequent pattern mining → outputs:

python main.py


Outputs (examples): clustered_air_quality.csv, models/air_quality_kmeans.pkl, and mining reports in outputs/.

🖥️ Launch the interactive dashboard

Interactive visualization with Streamlit:

streamlit run streamlit_app.py


Open the URL Streamlit prints (usually http://localhost:8501) and explore filters, cluster views, and time series.

🧩 Core modules (what they do)

preprocessing.py — loads station_day.csv, cleans missing values, scales features, and creates derived features (e.g., day-of-week, rolling means).

clustering.py — trains/predicts clusters (k-means default). Save/load model with pickle.

frequent_patterns.py — mines frequent itemsets / association rules per-cluster (e.g., Apriori).

streamlit_app.py — interactive UI to explore clusters, pollutant distributions, and patterns.

main.py — example orchestrator that runs the steps sequentially.

🧪 Example: how clustering is used

Preprocess daily station readings → feature vectors

Fit K-Means (or load saved model)

Assign cluster IDs to days/stations and save clustered_air_quality.csv

Run frequent pattern mining within each cluster to find pollutant co-occurrence rules

📥 Using your own data

Replace data/station_day.csv with your dataset (keep or adapt expected column names).

Typical expected columns: station_id, date, PM2.5, PM10, NO2, SO2, CO, O3, temperature, humidity

If columns differ, adjust preprocessing.py mapping.

♻️ Extend & customize

Swap K-Means for DBSCAN or hierarchical clustering in clustering.py.

Add time-series forecasting (e.g., Prophet, LSTM) to predict pollutant levels.

Add geospatial interpolation and map visualization (Folium, Kepler, or mapbox).

🛡️ Notes about quality & reliability

This project is experimental/educational. For production deployments or public health decisions, validate sensors, calibrate models, and cross-check with official monitoring stations.

Add unit tests for preprocessing and clustering before productionizing.

🤝 Contributing

Contributions are welcome!

Fork the repository

Create a feature branch: git checkout -b feature/my-feature

Commit changes with clear messages

Push and open a PR

Please include a brief description of changes and any dataset transformations used.

📚 Acknowledgments & libraries

Thanks to: pandas, numpy, scikit-learn, mlxtend (for Apriori), streamlit, and other OSS tools.
