Smart Street Light Optimization – Urban Technology Project
Overview

This project develops a data-driven framework for optimizing street lighting in Berlin using traffic detector data and machine learning clustering techniques.

The objective is to identify low nighttime traffic zones where smart dimming strategies can reduce energy consumption while maintaining safety.

Project Motivation

Urban street lighting is a major contributor to municipal energy consumption. By analyzing traffic patterns, lighting intensity can be dynamically adjusted in low-utilization areas to improve:

Energy efficiency

Operational cost savings

Urban sustainability

Methodology
1. Data Processing

Integrated street lamp and traffic detector datasets

Cleaned missing traffic values

Computed lamp density per 200m grid

2. Feature Engineering

Features used for clustering:

Lamp density

Traffic mean

Traffic peak

Morning mean

Night mean (00:00–05:00)

Detector presence

3. K-Means Clustering

Standardized features using StandardScaler

Applied K-Means (k=4)

Identified traffic-based lighting zones

4. Dimming Strategy

Defined dimmable lamps as:

night_mean ≤ 5 vehicles/hour

5. Energy Savings Estimation

Assumptions:

60W LED lamps

50% dimming

5 nighttime hours

€0.30 per kWh

Estimated annual savings per cluster were calculated.

Key Results

Cluster-based zoning successfully separates low, moderate, and high-traffic areas.

Significant dimming potential identified in low and moderate traffic zones.

Demonstrates measurable annual energy cost reduction.

Interactive Map

The project includes a Folium-based interactive map:

Berlin district outlines

Cluster layers

Detector-level popups

Toggleable cluster visualization
