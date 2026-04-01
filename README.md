# COMP 3610 Assignment 3 - NYC Taxi Analytics System

An integrated analytics system combining Apache Spark, a RAG pipeline, and an LLM-powered query router to answer natural language questions about NYC taxi data and transportation policy documents.

## Project Structure

```
.
├── assignment3_complete.ipynb   # Main notebook
├── data/
│   ├── raw/                     # Raw Parquet file (not tracked in git)
│   └── processed/               # Spark output (not tracked in git)
├── docs/                        # PDF corpus (see below)
├── chroma_db/                   # Persistent ChromaDB vector store
├── requirements.txt
└── README.md
```

## Setup

### Requirements
- Python 3.10 or 3.11
- Java 17 or 21 (required by PySpark)
- On Windows: `winutils.exe` for Hadoop 3.3.5 placed at `C:\hadoop\bin\`

### Install dependencies
```bash
pip install -r requirements.txt
```

### Data
The NYC Yellow Taxi Parquet file for January 2024 is downloaded automatically on first run if not present. Alternatively, download it manually from:
```
https://d37ci6vzurychx.cloudfront.net/trip-data/yellow_tripdata_2024-01.parquet
```
Place it at `data/raw/yellow_tripdata_2024-01.parquet`.

### PDF Corpus
Place the following PDFs in the `docs/` directory before running Part 2:

| # |Filename | Source |
|---|----------|--------|
| 1 | `2020-tlc-factbook.pdf` |  nyc.gov/ |
| 2 | `14036_paper_DDZKbDhn.pdf` | .aeaweb.org/ |
| 3 | `annual_report_2023.pdf` | nyc.gov/ |
| 4 | `CBDTP_evaluationreport_FIN_v1-1_123125.pdf` | mta.info/ |
| 5 | `CBDTP_Fact Sheet_FINAL.pdf` |  mta.info/ |
| 6 | `tlc.pdf` | 
| 7 | `2022-cms-report.pdf` | nyc.gov/ |

### LLM API
Update the `LLM_API_KEY` variable in the notebook with your API key for the course LLM server at `https://synapse.sergiomathurin.com/v1`.

## Running the Notebook

Open `assignment3_complete.ipynb` in Jupyter and run cells in order. Each part is self-contained but Parts 2 and 3 depend on the PDFs being present in `docs/`.

Parts:
- **Part 1** - Spark data loading, cleaning, SQL analytics, and performance optimization
- **Part 2** - PDF ingestion, chunking, ChromaDB embeddings, and RAG pipeline
- **Part 3** - LLM query router, data query handler, and end-to-end demo

# AI Usage
Claude was used for fomatting and error handling(specifically Hadoop errors)
Copilot was used for autocomleting repetative lines and quickfixes