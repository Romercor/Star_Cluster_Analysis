# Star Cluster Analysis Project

This project explores the characteristics of stars through clustering and classification techniques. With data including attributes like luminosity, temperature, radius, and distance, the analysis focused on grouping stars into clusters and building a model to classify them based on these features. Power BI was used to create interactive visualizations for deeper insights.

## Table of Contents
1. [Project Overview](#project-overview)
2. [Data Preparation](#data-preparation)
3. [Clustering Analysis](#clustering-analysis)
4. [Feature Extraction](#feature-extraction)
5. [Classification Model](#classification-model)
6. [Visualizations](#visualizations)
7. [Technologies Used](#technologies-used)
8. [Conclusion](#conclusion)

---

### Project Overview

The dataset includes various attributes of stars, such as:
- **Distance (ly)**: Distance from Earth in light years
- **Luminosity (L/Lo)**: Luminosity relative to the Sun
- **Radius (R/Ro)**: Radius relative to the Sun
- **Temperature (K)**: Surface temperature in Kelvin
- **Spectral Class**: Spectral classification of stars
- **Cluster**: Cluster label added during analysis

The goal was to explore these attributes through clustering, feature extraction, and classification, ultimately gaining insights into their interrelationships.

### Data Preparation

1. **Numeric Conversion**: 
   - Key columns (`Distance`, `Luminosity`, `Radius`, and `Temperature`) were converted to numeric types to enable calculations and model training.
   - Missing values were filled with default values (e.g., `0`), and rounding was applied where necessary.

2. **Feature Scaling**:
   - Scaling was applied to ensure that clustering and classification models could interpret the numerical values accurately.

### Clustering Analysis

Clustering techniques were applied to uncover natural groupings in the data:

1. **K-Means Clustering**:
   - The K-Means algorithm was initially used to group stars based on selected attributes.
   - After testing various numbers of clusters, an optimal grouping was identified, providing both scientific and visual clarity.

2. **Hierarchical Clustering**:
   - Hierarchical clustering, with a dendrogram for visualization, was used to further analyze relationships among clusters.
   - This approach validated the optimal number of clusters and provided a deeper perspective.

### Feature Extraction

For classification purposes, the `Spectral Class` was broken down into three parts:

1. **Spectral Type**: The main spectral type (e.g., A, B, F, G) was extracted to capture broad categories.
2. **Sub Type**: Numeric subtypes were extracted for finer distinctions within each spectral type.
3. **Luminosity Class**: The luminosity class (e.g., I, II, III, V, Ve) was separated to categorize brightness levels.

Regular expressions were used to parse these elements, creating distinct features for the classification model.

### Classification Model

A classification model was built to predict these spectral features based on the star’s physical properties:

1. **Label Encoding**:
   - `Spectral Type`, `Sub Type`, and `Luminosity Class` were encoded as numeric categories, making them compatible with machine learning models.

2. **Random Forest Classifier**:
   - A Random Forest model was chosen due to its ability to handle structured, complex data and its performance with multi-output classification tasks.
   - Using a multi-output classifier, the model was trained to predict all three target features simultaneously.

3. **Model Evaluation**:
   - The model’s performance was assessed with classification reports, detailing precision, recall, and F1 scores for each class.
   - Confusion matrices for each target variable provided further validation and insights into model accuracy.

### Visualizations

Interactive visualizations were created in Power BI for further exploration:

1. **H-R Diagram**:
   - A scatter plot was used to visualize star clusters based on temperature and luminosity, forming a Hertzsprung-Russell-like diagram.

2. **Cluster Summary**:
   - Summary visuals displayed central tendency measures (mean, median, variance) for each cluster.
   - Drill-through capabilities allowed deeper analysis, enabling users to explore scatter plots by cluster and spectral class.

3. **Star Profiles**:
   - Custom Power BI cards showcased individual stars with unique characteristics, such as the farthest, brightest, largest, and hottest stars.

### Technologies Used

- **Python**: Used for data preprocessing, clustering, feature extraction, and model building
  - Libraries: `pandas`, `sklearn`, `matplotlib`, `seaborn`
- **Power BI**: Enabled the creation of interactive visualizations and the exploration of clustering results

### Conclusion

This project demonstrated the effective use of clustering and classification techniques on stellar data. A model was successfully built to predict spectral classes based on physical properties, complemented by insightful visualizations for interactive analysis. Future work could explore additional classification models or refine feature extraction to improve prediction accuracy further.
