# Urban Mobility Optimization: Strategic Hub Localization in Buenos Aires
### A Graph-Theory & Clustering Approach to Logistics Expansion

## Project Overview
This project develops a data-driven framework for optimizing the entry of a ride-hailing service (like DiDi or Uber) into a new urban market. Using the city of **Buenos Aires (CABA)** as a case study, the model identifies optimal supply hubs to minimize **Estimated Time of Arrival (ETA)** and maximize network resilience.

Instead of a broad-brush launch, this project applies **Operations Research (OR)** principles to identify "Gravity Centers" based on historical transport demand (official taxi infrastructure), ensuring that the initial fleet is positioned where the city naturally flows.

## Key Features
* **Location-Allocation Modeling:** Solves the P-Median problem using **K-Means Clustering** to find 10 strategic "Expansion Hubs."
* **Graph Theory Analysis:** Models the city as a complex network using **NetworkX**. Calculates **Degree Centrality** to identify hubs that act as critical articulation points for fleet rebalancing.
* **Spatial ETL:** Custom Python pipeline to process and clean Open Data (WKT/POINT geometry) from the Buenos Aires Data Portal.
* **Interactive Cartography:** Dynamic visualization using **Folium** (Leaflet.js) to overlay the optimized supply network on the real urban grid.

## 🛠️ Tech Stack
* **Language:** Python 3.10+
* **Data Analysis:** `Pandas`, `NumPy`, `SciPy`
* **Machine Learning:** `Scikit-Learn` (K-Means)
* **Graph Theory:** `NetworkX`
* **Visualization:** `Folium`, `Matplotlib`, `Seaborn`

## Methodology

### 1. Spatial Discretization
The project consumes open data of taxi stops in CABA. This data serves as a **high-fidelity proxy** for validated historical demand. By extracting coordinates through RegEx and spatial processing, we create a point-cloud of the city's transport pulse.

### 2. Hub Optimization (The "Where")
Using Unsupervised Learning, we discretize the city into 10 clusters. The centroides represent the mathematical optimal for fleet staging, minimizing the "Within-Cluster Sum of Squares" (WSSR), which in business terms translates to **minimizing the distance to the next passenger.**

### 3. Network Topology (The "How")
By connecting hubs within a 3km threshold, we build a **Network Graph**. Nodes with higher centrality represent areas where a driver can serve multiple high-demand zones with minimal dead-mileage, providing a buffer against local demand spikes.

## Visual Results
The final output is an interactive `HTML` map (`red_transporte_grafo.html`) that allows stakeholders to:
1.  Identify high-density neighborhoods (Palermo, Recoleta, Retiro).
2.  Visualize the connectivity backbone between supply hubs.
3.  Drill down into specific "Hotspots" for targeted driver marketing campaigns.

## Project Structure
```text
├── data/
│   └── paradas_taxis.csv         # Raw infrastructure data
├── notebooks/
│   └── expansion_strategy.ipynb  # Full analysis & code
├── outputs/
│   ├── cluster_map.png           # Static visualization
│   └── red_transporte_grafo.html # Interactive map
└── README.md
```

 ## 🔗 Links
[![portfolio](https://img.shields.io/badge/my_portfolio-000?style=for-the-badge&logo=ko-fi&logoColor=white)](https://tinyurl.com/matiasgangui)
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/matias-gangui-660654175/)
[![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white)](https://github.com/matias258)
