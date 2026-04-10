# Clustering-Based Anomaly Detection on Sales Transactions

## Project Overview
In this project, I worked with weekly retail sales data to understand product behaviour and identify unusual patterns.

I used K-Means clustering to group products with similar sales trends, and then applied a simple distance-based approach to detect anomalies. The goal was to see how unsupervised learning can help in identifying products that behave differently from the rest.

This kind of analysis can be useful in real-world scenarios like spotting underperforming products, detecting data issues, or identifying seasonal trends.

---

## Objectives
- Group products based on their weekly sales patterns  
- Identify products that behave differently from their cluster  
- Visualise high-dimensional data using PCA  
- Extract useful insights that can support business decisions  

---

## Dataset
- Source: UCI Machine Learning Repository  
- Dataset: Sales Transactions Dataset (Weekly)  
- Description:
  - Contains weekly sales data (W0 – W51)  
  - Each row represents a product  

---

## Approach

### Data Preprocessing
I selected only the weekly sales columns and applied standard scaling to make sure all features contribute equally during clustering.

### Dimensionality Reduction
Since the dataset has 52 features, I used PCA to reduce it to 2 dimensions for visualisation. This made it easier to understand the cluster structure.

### Clustering
I applied K-Means clustering and tested different values of k (from 2 to 9).  
The final number of clusters was selected based on silhouette score and overall cluster separation.

### Anomaly Detection
After clustering, I calculated the distance of each product from its cluster centre.  
The top 5% of points (based on distance) were marked as anomalies, assuming they deviate significantly from normal behaviour.

---

## Results
- The data was grouped into 3 main clusters  
- 24 products were identified as anomalies  
- A few products showed very unusual sales patterns compared to others  

---

## Visualisations
- PCA scatter plot showing clusters and anomalies  
- Distance distribution plot used to identify the anomaly threshold  

---

## Key Takeaways
- K-Means works well for grouping similar sales patterns  
- Distance from centroid is a simple but effective way to detect outliers  
- PCA helps in making high-dimensional data easier to interpret  
- Combining clustering with anomaly detection gives more meaningful insights  

---

## Limitations
- K-Means assumes clusters are spherical, which may not always be true  
- PCA reduces dimensionality but may lose some information  
- The 5% anomaly threshold is a simple assumption and may not be optimal  

---

## Future Improvements
- Try DBSCAN for better handling of irregular clusters  
- Use Isolation Forest for more advanced anomaly detection  
- Explore time-based models to capture seasonality  
- Experiment with different anomaly thresholds  

---

## Tech Stack
- Python  
- Pandas, NumPy  
- Scikit-learn  
- Matplotlib  

---

## Project Structure
Data/  
Notebook/  
Report/  
README.md  

---

## How to Run
Clone the repository and run the notebook:

```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
pip install -r requirements.txt
jupyter notebook
