# Bitcoin Market and Energy Analytics Pipeline

## 📌 Project Overview

This project builds a robust data engineering pipeline to ingest, clean, transform, and analyze large-scale datasets that represent Bitcoin’s market behavior (price, volume, volatility) and its associated environmental impact (energy consumption and emissions).

By constructing automated data workflows and integrating diverse sources (market APIs, CSVs, cloud platforms), we provide an end-to-end system for supporting analytical and predictive modeling tasks. The pipeline also supports sustainability monitoring and predictive alerting for environmental impact metrics in response to cryptocurrency trading trends.

## ⚙️ Technologies Used

- **Python** for pipeline development and transformation
- **Pandas, NumPy, Matplotlib, Seaborn** for data wrangling and EDA
- **Jupyter Notebooks** for prototyping and visual analysis
- **Airflow / Prefect (suggested)** for pipeline orchestration
- **Cloud Storage (AWS S3 or GCP Bucket)** for raw and processed data
- **SQLite / PostgreSQL** for intermediate data storage
- **GitHub Actions** for CI/CD pipeline testing
- **Keras (LSTM)** for time-series modeling
- **Docker (optional)** for containerized environments

## 📁 Project Structure

```
bitcoin-energy-data-pipeline/
│
├── data/                          # Raw and processed data files
│   ├── raw/
│   └── processed/
│
├── notebooks/                     # Analysis and visualization notebooks
│   └── market_energy_analysis.ipynb
│
├── pipeline/                      # Data engineering pipeline scripts
│   ├── ingest.py                  # Ingest from APIs or files
│   ├── clean.py                   # Data cleaning routines
│   ├── transform.py               # Feature engineering
│   └── model.py                   # LSTM and other models
│
├── dags/                          # Airflow DAGs (optional for orchestration)
│   └── data_pipeline_dag.py
│
├── config/                        # Configs and environment settings
│   └── config.yaml
│
├── requirements.txt
└── README.md
```

## 🔄 Data Pipeline Overview

1. **Ingestion**  
   - Pulls historical data from `.xlsx` files and live APIs (e.g., CoinGecko for price data)
   - Stores data into a staging area (local CSV or cloud blob)

2. **Preprocessing**  
   - Handles missing values, duplicates, and type conversions
   - Normalizes time formats for merge alignment

3. **Transformation & Feature Engineering**  
   - Creates engineered features like volatility, energy-to-price ratios
   - Scales features using `MinMaxScaler` and `StandardScaler`

4. **Exploratory Data Analysis (EDA)**  
   - Plots trends over time using boxplots, bubble charts, correlation heatmaps

5. **Modeling (Optional)**  
   - Includes LSTM models for forecasting energy consumption
   - Evaluates using RMSE, R², MAE, MAPE

6. **Integration & Storage**  
   - Pushes processed datasets to SQLite or PostgreSQL
   - Optionally syncs outputs to cloud storage (e.g., AWS S3)

## 🔬 Key Features

- Automated data cleaning and preprocessing
- Time-based joins across datasets
- Integration with external APIs (modular architecture)
- Outlier removal using statistical methods (e.g., z-score)
- Full lifecycle from ingestion → analysis → modeling
- Clear business insight: *How does Bitcoin’s activity impact environmental sustainability?*

## 📊 Key Insights

- Clear correlation found between Bitcoin trading activity and energy consumption.
- Predictive models (e.g., LSTM) achieved up to **93% accuracy** in modeling energy impact.
- Volatility in Bitcoin markets often coincides with spikes in energy usage.
- Supports stakeholders in finance and ESG in understanding crypto's environmental trade-offs.

## 🧪 Setup & Run Locally

```bash
# Clone the repo
git clone https://github.com/rutwizg/bitcoin-energy-data-pipeline.git
cd bitcoin-energy-data-pipeline

# Install dependencies
pip install -r requirements.txt

# Run a pipeline script
python pipeline/ingest.py
python pipeline/clean.py
python pipeline/transform.py
```

## ☁️ Suggested Integrations

| Component           | Suggested Tool     |
|---------------------|--------------------|
| Orchestration       | Airflow / Prefect  |
| API Ingestion       | CoinGecko, figshare|
| Storage             | AWS S3 / GCP       |
| CI/CD               | GitHub Actions     |
| Visualization       | Plotly Dash / Tableau |
| Containerization    | Docker             |

## 🙏 Acknowledgments

- Elharony (2024), Khosravi & Säämäki (2023), Köhler & Pizzol (2019) – for foundational environmental insights
- CoinGecko and figshare – for publicly accessible data
- Green Blockchain initiatives – for sustainability direction

## 📄 License

This project is licensed under the MIT License.
