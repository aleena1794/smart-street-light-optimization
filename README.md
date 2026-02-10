# Smart Street Light Optimization – Urban Technology Project
## Overview
This project develops a data-driven framework for optimizing street lighting in Berlin using traffic detector data and machine learning clustering techniques.  
The objective is to identify low nighttime traffic zones where smart dimming strategies can reduce energy consumption while maintaining safety.

## Project Motivation
Urban street lighting is a major contributor to municipal energy consumption. By analyzing traffic patterns, lighting intensity can be dynamically adjusted in low-utilization areas to improve:  
Energy efficiency  
Operational cost savings  
Urban sustainability  

## Datasets
Berlin Street Lights data: https://download.geofabrik.de/europe/germany/berlin.html  
Traffic Detectors Locations: https://daten.berlin.de/datensaetze/standorte-verkehrsdetektion-berlin  
Traffic Detector Count 2024: https://api.viz.berlin.de/daten/verkehrsdetektion?path=2024%2Fneue_qualitaetssicherung%2FFahrstreifendetektoren%2F  
Berlin Districts: https://daten.odis-berlin.de/de/dataset/bezirksgrenzen/

## Methodology
**1. Data Processing** - 
Integrated street lamp and traffic detector datasets  
Computed lamp density per km2, traffic intensity per detector for morning and night hours

**2. Feature Engineering** - 
Features used for clustering:  
Lamp density  
Traffic mean   
Traffic peak   
Morning mean   
Night mean (00:00–05:00)  
Detector presence  

**3. K-Means Clustering** - 
Standardized features using StandardScaler  
Applied K-Means (k=4)  
Identified traffic-based lighting zones  

**4. Dimming Strategy** - 
Defined dimmable lamps as: night_mean ≤ 5 vehicles/hour 

**5. Energy Savings Estimation** - 
Assumptions: 60W LED lamps, 50% dimming, 5 nighttime hours, €0.30 per kWh 
Estimated annual savings per cluster were calculated. 

## Project Structure & Results

The complete implementation of the project is available in Smart_street_light_optim.ipynb  
All generated outputs and visualizations are stored in the results/ folder.  

### Generated Outputs  
lamp_density_map.html - Interactive map of street lamp density per km² in Berlin.  
traffic_intensity_morning_hours.html - Interactive map of traffic intensity per detector during morning hours (5:00–12:00).  
traffic_intensity_night_hours.html - Interactive map of traffic intensity per detector during night hours (00:00–05:00).  
kmeans_clusters_street_light_zones.html - Interactive map of Berlin zones identified using K-Means clustering.  
kmeans_cluster_means.xlsx - Mean feature values per K-Means cluster.  
lamps_percent_dimmable_per_cluster.png - Percentage of lamps that can be dimmed during night hours per cluster.  
energy_cost_savings_per_cluster.png - Estimated energy cost savings per cluster (visualized).  
energy_saving_per_cluster.xlsx - Estimated energy saving results per cluster.  

## Key Results 
Cluster-based zoning successfully separates low, moderate, and high-traffic areas.  
Significant dimming potential identified in low and moderate traffic zones.  
Demonstrates measurable annual energy cost reduction.  

## Interactive Map 
The project includes a Folium-based interactive map:  
Berlin district outlines  
Cluster layers  
Detector-level popups  
Toggleable cluster visualization  

