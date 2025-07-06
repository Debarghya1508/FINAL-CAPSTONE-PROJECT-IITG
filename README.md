# Dynamic Pricing for Urban Parking Lots

This project implements a **dynamic pricing engine** for urban parking lots, leveraging real-time data ingestion and machine learning to optimize parking rates. The goal is to balance occupancy and revenue based on demand patterns using a predictive pipeline built on modern data engineering and ML tools.

---

## Overview

Urban parking lots often face congestion, underutilization, or revenue losses due to static pricing. This project introduces a **machine learning-based adaptive pricing solution**. It uses real-time data such as time of day, location, demand, and occupancy rates to predict the optimal price dynamically.

The pipeline is powered by:
- A streaming framework (Pathway)
- A machine learning ensemble model
- Real-time feature engineering
- Interactive visualizations

---

## Tech Stack

| Category | Tools / Libraries |
|---------|-------------------|
| Programming Language | Python |
| Streaming Engine | [Pathway](https://pathway.com/) |
| Feature Engineering | `pandas`, `numpy`, `datetime` |
| Visualization | `bokeh`, `panel` |
| Notebook Interface | Google Colab / Jupyter |
| Model Optimization |  `pandas`, `numpy` |

---
## Project Architecture and Workflow
1. Data Ingestion:
- Real-time parking lot data (timestamp, lot ID, occupancy, etc.) is streamed into the system.

- Handled using Pathway to support real-time data processing.

2. Data Preprocessing:
- Incoming data is cleaned, parsed into a schema, and stored as dynamic Pathway tables.

- Date-time fields are extracted for features such as hour, weekday, is_weekend.

3. Feature Engineering:
- Compute temporal features, occupancy stats, lot popularity index, and traffic intensity.

- Window-based aggregations (e.g., hourly averages) are used to derive trends.


5. Prediction Pipeline:
- New data points trigger real-time predictions using the ensemble model.

- Pathway handles stateful updates and ensures freshness of outputs.

6. Output Handling:
- Predicted prices are served via:

- Live dashboard using bokeh/panel

- Exported tables (CSV/Parquet)

- Potential REST API endpoint

Future Improvements According To My Opinion:
- Incorporate reinforcement learning for dynamic price optimization.

- Integrate weather and traffic APIs to enhance feature richness.

- Develop a user-side mobile app interface for live pricing view and booking.

🔗 References:
- Pathway Documentation

- Scikit-learn Ensemble Models

- Bokeh Interactive Visuals

Contributor:
-Debarghya Das 


##  Architecture Diagram

```mermaid
---
config:
  layout: dagre
  theme: mc
---
flowchart TD
    A["Real-time Parking Data Stream"] --> B["Pathway Data Pipeline"]
    B --> C["Feature Engineering Module"]
    C --> D[" Ensemble Model"]
    D --> E["Predicted Parking Prices"]
    E --> F["Live Dashboard"] & G["Pricing API / Output Table"]



