# 📊 Large-Scale Data Visualization: COVID-19 Networks & Earthquake Analysis

<div align="center">

![Python](https://img.shields.io/badge/Python-Visualization-3776AB?logo=python)
![Plotly](https://img.shields.io/badge/Plotly-Interactive-3F4F75?logo=plotly)
![NetworkX](https://img.shields.io/badge/NetworkX-Graphs-orange)
![GeoPandas](https://img.shields.io/badge/GeoPandas-Spatial-139C5A)
![Pandas](https://img.shields.io/badge/Pandas-Data-150458?logo=pandas)

**Interactive visualization of global COVID-19 transmission networks and seismic activity patterns**

[Overview](#-overview) • [Visualizations](#-visualizations) • [Methodology](#-methodology) • [Quick Start](#-quick-start)

</div>

---

## 🌍 Overview

This project demonstrates **advanced data visualization techniques** applied to two large-scale, real-world datasets:

1. **COVID-19 Global Transmission Network** - Network analysis of pandemic spread patterns
2. **Global Earthquake Activity** - Geospatial and temporal seismic event analysis

Built using the **What/Why/How** visualization framework, this project showcases interactive, scalable visualization methods for exploring complex data patterns across spatial, temporal, and network dimensions.

### Key Achievements
- ✅ Processed **230+ countries** COVID-19 data from Johns Hopkins CSSE
- ✅ Analyzed **8,943 earthquake events** from USGS global catalog
- ✅ Created **6+ interactive visualizations** with zoom, filter, and exploration capabilities
- ✅ Implemented **network analysis** with degree centrality metrics
- ✅ Built **temporal analysis** showing daily, monthly, and hourly patterns
- ✅ Designed **geospatial visualizations** with regional comparisons

Developed as part of **CSC5356 Data Engineering** coursework at **Al Akhawayn University**, Master of Science in Big Data Analytics program.

---

## 🎨 Visualizations

### 1. COVID-19 Global Transmission Network

![COVID-19 Network](visualizations/covid_network_visualization.png)

**Network Type:** Force-directed graph with community detection  
**Data Points:** 230+ countries, weighted edges by transmission similarity  
**Key Features:**
- Node size represents total confirmed cases
- Node color indicates degree centrality (network importance)
- Edge width shows transmission correlation strength
- Force-directed layout reveals natural clustering patterns

**Insights Revealed:**
- Identified major transmission hubs (high-degree nodes)
- Discovered regional clusters of similar outbreak patterns
- Visualized global connectivity of pandemic spread
- Small island nations often appear isolated with unique patterns

**Technical Implementation:**
- NetworkX for graph construction and centrality metrics
- Plotly for interactive force-directed layout
- Custom color mapping for degree centrality gradients
- Hover tooltips showing country names and case statistics

---

### 2. Earthquake Temporal Analysis

![Earthquake Temporal Patterns](visualizations/earthquake_temporal_analysis.png)

**Analysis Period:** February 22 - March 26, 2025  
**Total Events:** 8,943 earthquakes  
**Visualization Types:** Line charts, bar charts, distribution plots

#### Panel 1: Monthly Frequency Trend
- **Pattern:** Steady increase from 1,300 to 7,500+ events/month
- **Insight:** Shows accumulation pattern over data collection period
- **Use Case:** Long-term seismic activity forecasting

#### Panel 2: Daily Frequency Fluctuation  
- **Pattern:** Oscillating between 220-450 events/day with spike to 480
- **Insight:** Identifies anomaly dates requiring investigation
- **Notable:** Spike on specific date suggests major seismic event or aftershock sequence

#### Panel 3: Hourly Distribution
- **Pattern:** Relatively uniform ~350-400 events/hour
- **Insight:** No significant circadian pattern (expected for natural phenomena)
- **Validation:** Confirms data quality - no systematic collection bias

#### Panel 4: Magnitude Distribution
- **Dominant Range:** 0-2 magnitude (75.7% of all events)
- **Moderate:** 2-4 magnitude (15.2%)
- **Strong:** 4-6 magnitude (9.1%)
- **Major:** 6+ magnitude (0.1%, 6 events)
- **Insight:** Follows expected logarithmic Gutenberg-Richter law

**Technical Implementation:**
- Pandas for time-series aggregation and resampling
- Matplotlib/Seaborn for multi-panel statistical plots
- Datetime parsing with timezone handling
- Custom color schemes for magnitude severity

---

### 3. Regional Earthquake Magnitude Comparison

![Regional Magnitude Analysis](visualizations/regional_magnitude_comparison.png)

**Regions Analyzed:** Top 10 seismically active areas  
**Visualization Type:** Box plot with outlier detection

#### Regional Insights:

| Region | Median Magnitude | Notable Features |
|--------|------------------|------------------|
| **Alaska** | 1.5 | Widest distribution (0-6.3), highest variability |
| **California** | 0.9 | Most frequent events, low median |
| **Puerto Rico** | 2.3 | Highest median, consistent mid-range activity |
| **Nevada** | 1.4 | Moderate activity with outliers up to 3.4 |
| **Texas** | 1.6 | Sparse but notable events |
| **New Mexico** | 1.8 | Second-highest median magnitude |

**Key Findings:**
- Alaska shows extreme variability - most unpredictable seismic region
- California has highest frequency but lower magnitudes (many small tremors)
- Puerto Rico exhibits consistent mid-magnitude activity
- Clear outliers in multiple regions indicate major seismic events

**Technical Implementation:**
- GeoPandas for spatial data handling
- Statistical analysis with quartiles and IQR
- Matplotlib box plots with custom styling
- Outlier detection using 1.5×IQR rule

---

## 🏗️ Methodology: What/Why/How Framework

### WHAT: Dataset Characteristics

#### Dataset 1: COVID-19 Network Data
- **Source:** Johns Hopkins University CSSE COVID-19 Time Series
- **Coverage:** 230+ countries/regions, global scope
- **Temporal Range:** Daily confirmed cases (cumulative)
- **Data Type:** Network/relational data
- **Attributes:** Country, date, confirmed cases, transmission correlations
- **Size:** ~50,000 time-series data points

#### Dataset 2: Earthquake Geospatial Data  
- **Source:** USGS Earthquake Catalog (all_month.csv)
- **Coverage:** Global seismic events
- **Temporal Range:** February 22 - March 26, 2025
- **Data Type:** Geospatial point data with temporal attributes
- **Attributes:** Time, latitude, longitude, depth, magnitude, region
- **Size:** 8,943 earthquake events

---

### WHY: Task Abstraction

#### COVID-19 Network Tasks:
1. **DISCOVER** distribution of pandemic patterns **AMONG** countries
   - Action: Discover → Identify clusters and outliers
   - Target: Network structure and community formation

2. **IDENTIFY** transmission hubs **IN** the global network
   - Action: Identify → Locate high-centrality nodes
   - Target: Critical nodes influencing spread

3. **COMPARE** outbreak severity **BETWEEN** regions
   - Action: Compare → Assess relative impact
   - Target: Node attributes (case counts)

#### Earthquake Analysis Tasks:
1. **EXPLORE** temporal patterns **OF** seismic activity
   - Action: Explore → Discover trends over time
   - Target: Time-series distributions

2. **LOCATE** high-magnitude events **IN** spatial regions
   - Action: Locate → Find geographic hotspots
   - Target: Spatial clusters of severe events

3. **COMPARE** earthquake characteristics **ACROSS** regions
   - Action: Compare → Statistical distribution analysis
   - Target: Magnitude distributions by location

---

### HOW: Visual Encoding & Interaction Design

#### COVID-19 Network Visualization

**Visual Channels:**
- **Position:** Force-directed layout (X, Y coordinates)
- **Size:** Node size ∝ total confirmed cases
- **Color:** Degree centrality (gradient: low=blue → high=yellow)
- **Connection:** Edge presence indicates transmission correlation

**Marks:** Nodes (circles) and edges (lines)

**Manipulations:**
- **Zoom/Pan:** Explore dense network regions
- **Hover:** Tooltips show country details
- **Filter:** (Potential) threshold by case count or centrality

**Derivation:** Calculated degree centrality from network topology

---

#### Earthquake Temporal Visualizations

**Panel 1 (Monthly Trend):**
- Mark: Line
- Channel: Position (X=month, Y=frequency)
- Insight: Long-term accumulation pattern

**Panel 2 (Daily Frequency):**
- Mark: Line with markers
- Channel: Position (X=date, Y=count)
- Insight: Day-to-day variability and anomalies

**Panel 3 (Hourly Distribution):**
- Mark: Bar chart
- Channel: Position (X=hour, Y=count), Height=frequency
- Insight: Temporal uniformity validation

**Panel 4 (Magnitude Distribution):**
- Mark: Bar chart with annotations
- Channel: Color (magnitude severity), Height=count
- Insight: Frequency-magnitude relationship

**Manipulations:**
- **Multi-panel faceting:** Compare temporal granularities
- **Date filtering:** Focus on specific time windows
- **Binning:** Aggregate by time intervals

---

#### Regional Magnitude Box Plot

**Visual Channels:**
- **Position:** X=region (categorical), Y=magnitude (quantitative)
- **Mark:** Box-and-whisker
- **Color:** Region differentiation (viridis gradient)
- **Symbol:** Outlier points (circles)

**Statistical Encoding:**
- Box: Interquartile range (IQR, 25th-75th percentile)
- Line: Median magnitude
- Whiskers: 1.5×IQR range
- Points: Outliers beyond whiskers

**Manipulations:**
- **Compare:** Side-by-side statistical summaries
- **Filter:** Select top N regions by event count
- **Sort:** Order by median magnitude

---

## 🚀 Quick Start

### Prerequisites
```bash
Python 3.8+
Jupyter Notebook or JupyterLab
8GB RAM (for large dataset processing)
```

### Installation

#### 1. Clone Repository
```bash
git clone https://github.com/KenzaBouqdir/Visualization-of-Large-Datasets.git
cd Visualization-of-Large-Datasets
```

#### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

Required packages:
```
pandas>=1.3.0
numpy>=1.21.0
matplotlib>=3.4.0
seaborn>=0.11.0
plotly>=5.0.0
networkx>=2.6.0
geopandas>=0.10.0
jupyter>=1.0.0
```

#### 3. Download Datasets

**COVID-19 Data:**
```bash
# From Johns Hopkins CSSE GitHub
wget https://raw.githubusercontent.com/CSSEGISandData/COVID-19/master/csse_covid_19_data/csse_covid_19_time_series/time_series_covid19_confirmed_global.csv
```

**Earthquake Data:**
```bash
# From USGS Earthquake Catalog
wget https://earthquake.usgs.gov/earthquakes/feed/v1.0/summary/all_month.csv
```

#### 4. Run Notebook
```bash
jupyter notebook KenzaBouqdir_notebook.ipynb
```

---

## 📂 Project Structure

```
Visualization-of-Large-Datasets/
├── KenzaBouqdir_notebook.ipynb          # Main analysis notebook
├── README.md                            # This file
├── requirements.txt                     # Python dependencies
├── data/                                # Dataset directory (not in repo)
│   ├── time_series_covid19_confirmed_global.csv
│   └── all_month.csv
├── visualizations/                      # Output images
│   ├── covid_network_visualization.png
│   ├── earthquake_temporal_analysis.png
│   └── regional_magnitude_comparison.png
└── utils/                               # Helper functions (optional)
    ├── data_loader.py
    └── visualization_helpers.py
```

---

## 🔍 Key Features

### Data Processing
- **Robust data validation:** Handles missing values, invalid coordinates
- **Efficient aggregation:** Pandas groupby for time-series analysis
- **Network construction:** Custom similarity metrics for COVID-19 correlation
- **Spatial indexing:** GeoPandas for region-based filtering

### Visualization Design
- **Interactive plots:** Plotly for zoom, pan, hover interactions
- **Multi-scale analysis:** Daily, monthly, hourly temporal views
- **Statistical rigor:** Box plots with quartiles and outliers
- **Color theory:** Perceptually-uniform colormaps (viridis, plasma)

### Code Quality
- **Modular functions:** Separate data loading, processing, visualization
- **Documentation:** Comprehensive docstrings
- **Error handling:** Try-except blocks for data issues
- **Reproducibility:** Fixed random seeds for network layouts

---

## 📊 Technical Implementation Details

### COVID-19 Network Construction

```python
def build_covid_network(df):
    """
    Constructs transmission network from time-series data
    
    Steps:
    1. Calculate pairwise correlation of case trajectories
    2. Threshold correlations (>0.7) to create edges
    3. Weight edges by correlation strength
    4. Compute degree centrality for node importance
    """
    # Correlation matrix of country time-series
    corr_matrix = df.T.corr()
    
    # Build graph from high-correlation pairs
    G = nx.Graph()
    for country1, country2 in high_corr_pairs:
        G.add_edge(country1, country2, weight=corr_value)
    
    # Calculate centrality metrics
    centrality = nx.degree_centrality(G)
    
    return G, centrality
```

### Earthquake Temporal Aggregation

```python
def aggregate_earthquake_data(df):
    """
    Multi-granularity temporal aggregation
    
    Returns:
    - Monthly: Cumulative count
    - Daily: Event frequency per day
    - Hourly: Distribution across 24 hours
    """
    df['datetime'] = pd.to_datetime(df['time'])
    
    monthly = df.resample('M', on='datetime').size()
    daily = df.resample('D', on='datetime').size()
    hourly = df.groupby(df['datetime'].dt.hour).size()
    
    return monthly, daily, hourly
```

### Magnitude Distribution Analysis

```python
def analyze_magnitude_distribution(df):
    """
    Categorize earthquakes by magnitude ranges
    
    Bins: [0-2], [2-4], [4-6], [6+]
    Follows Gutenberg-Richter logarithmic law
    """
    bins = [0, 2, 4, 6, np.inf]
    labels = ['0-2', '2-4', '4-6', '6+']
    
    df['mag_range'] = pd.cut(df['mag'], bins, labels=labels)
    distribution = df['mag_range'].value_counts()
    
    return distribution
```

---

## 🎯 Use Cases & Applications

### 1. Public Health & Epidemiology
**COVID-19 Network Analysis:**
- Identify countries with similar outbreak patterns for policy sharing
- Predict transmission pathways for intervention planning
- Allocate resources to high-centrality hubs
- **Real-world example:** WHO uses similar network analysis for pandemic response

### 2. Disaster Management & Seismology
**Earthquake Visualization:**
- Monitor seismic activity in real-time dashboards
- Identify regions requiring building code updates
- Predict aftershock sequences from temporal patterns
- **Real-world example:** USGS uses similar visualizations for public alerts

### 3. Data Journalism & Communication
- Translate complex datasets into accessible visualizations
- Tell data-driven stories about global phenomena
- Support evidence-based reporting
- **Real-world example:** NYTimes COVID-19 tracker

### 4. Research & Academia
- Publish reproducible analysis workflows
- Validate geophysical models with observational data
- Teach data visualization best practices
- **Real-world example:** Jupyter notebooks in scientific publications

---

## 🔧 Customization & Extensions

### Add More Network Metrics
```python
# Betweenness centrality (bridge nodes)
betweenness = nx.betweenness_centrality(G)

# Clustering coefficient (local connectivity)
clustering = nx.clustering(G)

# Community detection (Louvain algorithm)
from community import best_partition
communities = best_partition(G)
```

### Interactive Geospatial Map
```python
import folium

# Create heatmap of earthquake epicenters
m = folium.Map(location=[0, 0], zoom_start=2)
HeatMap(data=earthquake_coords).add_to(m)
m.save('earthquake_heatmap.html')
```

### Animated Time-Series
```python
import plotly.express as px

# Animated scatter plot of COVID-19 spread over time
fig = px.scatter_geo(df, 
                     lat='latitude', 
                     lon='longitude',
                     size='cases',
                     animation_frame='date',
                     projection='natural earth')
```

---

## 📈 Performance & Scalability

| Operation | Dataset Size | Processing Time |
|-----------|--------------|-----------------|
| **COVID network construction** | 230 countries × 400 days | ~2.5 seconds |
| **Earthquake temporal aggregation** | 8,943 events | ~0.8 seconds |
| **Regional box plot generation** | 10 regions | ~1.2 seconds |
| **Total notebook execution** | Both datasets | ~15 seconds |

**Optimization Techniques Used:**
- Vectorized Pandas operations (no loops)
- Efficient NetworkX algorithms (O(n log n))
- Matplotlib figure preallocation
- Selective data loading (read only required columns)

---

## 🐛 Troubleshooting

### Issue: "Module not found" errors
```bash
# Ensure all dependencies installed
pip install -r requirements.txt

# For conda users
conda install -c conda-forge geopandas networkx plotly
```

### Issue: Network visualization too dense
```python
# Filter low-weight edges
threshold = 0.8
G_filtered = nx.Graph([(u,v,d) for u,v,d in G.edges(data=True) 
                       if d['weight'] > threshold])
```

### Issue: Out of memory for large datasets
```python
# Process data in chunks
chunk_size = 10000
for chunk in pd.read_csv('large_file.csv', chunksize=chunk_size):
    process(chunk)
```

### Issue: Plotly figures not rendering in Jupyter
```bash
# Enable notebook renderer
import plotly.io as pio
pio.renderers.default = 'notebook'
```

---

## 📚 Resources & References

### Data Sources
- [Johns Hopkins CSSE COVID-19 Data](https://github.com/CSSEGISandData/COVID-19)
- [USGS Earthquake Catalog](https://earthquake.usgs.gov/earthquakes/feed/)

### Visualization Theory
- Munzner, T. (2014). *Visualization Analysis and Design* - What/Why/How framework
- Tufte, E. (2001). *The Visual Display of Quantitative Information*

### Libraries Documentation
- [NetworkX Documentation](https://networkx.org/documentation/stable/)
- [Plotly Python](https://plotly.com/python/)
- [GeoPandas User Guide](https://geopandas.org/en/stable/)
- [Pandas Time Series](https://pandas.pydata.org/docs/user_guide/timeseries.html)

### Earthquake Science
- [Gutenberg-Richter Law](https://en.wikipedia.org/wiki/Gutenberg%E2%80%93Richter_law) - Magnitude-frequency relationship

---

## 👨‍💻 About

**Author:** Kenza Bouqdir  
**Institution:** Al Akhawayn University  
**Program:** Master of Science in Big Data Analytics  
**Course:** CSC5356 – Data Engineering  

**Skills Demonstrated:**
- Large-scale data processing (230+ countries, 8,943 events)
- Network analysis and graph theory
- Geospatial data manipulation
- Time-series analysis and aggregation
- Statistical visualization
- Interactive plotting with Plotly
- Jupyter notebook development
- Data storytelling and insight extraction

---

## 🙏 Acknowledgments

- **Johns Hopkins CSSE** for maintaining comprehensive COVID-19 data
- **USGS** for real-time earthquake monitoring
- **NetworkX & GeoPandas communities** for excellent documentation
- **Plotly** for interactive visualization capabilities

---

## 📄 License

This project is for educational and portfolio purposes as part of academic coursework.

---

<div align="center">

**⭐ If this visualization work inspires you, please star this repository! ⭐**

**Built with 📊 for data-driven insights and visual storytelling**

</div>
