Predicting the Most Common POI Type in a Region using GIS and ML
This project uses OpenStreetMap data and spatial features (POI density, land use, place type) to predict the most common point-of-interest (POI) type per 500m grid cell across the West Midlands region.

This repository demonstrates an end-to-end workflow for a complex geospatial prediction task. It showcases a pragmatic, iterative approach to machine learning, from initial data engineering and feature creation to model comparison and refinement. The project serves as a powerful framework for data-driven location analysis, with applications in urban planning, retail site selection, and strategic resource allocation.

📦 Data
To run this project:

Download the West Midlands shapefiles from Geofabrik

Place them in the west-midlands-latest-free/ folder (which is ignored by version control).

🛠️ Methodology & Workflow
The project followed a structured, multi-stage workflow, from geospatial data engineering to iterative modelling.

1. Geospatial Feature Engineering
The first step was to transform raw geospatial data into a structured format suitable for machine learning.

Grid Creation: A 500x500 meter grid was created to cover the entire West Midlands region, forming the base unit of analysis.

Target Variable Creation: POIs were spatially joined to the grid. For each grid cell, the most frequently occurring POI type (fclass) was assigned as the target label (e.g., most_common_poi_type = 'school'). This revealed a significant challenge: 84 unique POI types, creating a severe class imbalance problem.

Feature Engineering: A rich set of features was engineered for each grid cell by spatially joining various data layers. Key features included:

poi_count: The total number of POIs in a cell.

poi_diversity: The number of unique POI types in a cell.

Land use features (e.g., counts of residential, commercial, industrial polygons).

place_type: The type of locality (e.g., town, suburb).

2. Iterative Modelling & Evaluation
The initial model, a RandomForest classifier trained on all 84 classes, performed poorly (accuracy ~5%) due to the extreme class imbalance. This led to a more refined, pragmatic approach.

Model Refinement: To create a more tractable problem, the dataset was filtered to focus on predicting only the top 15 most common POI types. This is a common and necessary step in real-world machine learning projects.

Model Comparison:

A RandomForest model was trained on the reduced dataset. Performance improved but was still modest (accuracy ~15%), with difficulty predicting many classes.

An XGBoost classifier was then implemented. This model showed a significant improvement, achieving a final accuracy of 29%. While still a challenging problem, the XGBoost model demonstrated a much stronger ability to capture the complex relationships in the data.

📊 Results & Key Findings
The final XGBoost model provided several key insights:

Feature Importance: The most predictive features were consistently poi_count and poi_diversity, indicating that the density and variety of existing points of interest are the strongest signals for a grid cell's primary character.

Model Performance: The model excelled at identifying certain POI types, such as 'pitch' (sports fields), achieving a high recall of 76%. This suggests that certain land uses have very distinct and predictable "fingerprints."

Challenges: The model struggled with classes that are often co-located or have less distinct geospatial signatures, such as 'school' and 'pub', highlighting the complexity of urban modeling.

💻 Tech Stack
Python

GeoPandas for core geospatial data manipulation

Pandas & NumPy for data wrangling

Scikit-learn for machine learning and preprocessing

XGBoost for gradient boosted models

Matplotlib & Seaborn for data visualisation

👤 Author
Hema Priya Akkili

[GitHub](
