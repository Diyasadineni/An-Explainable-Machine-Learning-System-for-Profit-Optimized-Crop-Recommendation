# Crop Profit Maximization using Machine Learning

Machine learning based system for **crop recommendation and profit maximization** using agricultural datasets such as **crop yield, soil conditions, and market (mandi) price data**.

The model analyzes environmental and market factors to recommend crops that can provide **higher profitability for farmers**.

---
## Installation

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/crop-profit-maximization.git
cd crop-profit-maximization
```

Install required dependencies:

```bash
pip install pandas numpy scikit-learn matplotlib seaborn
```

---
## Import Modules

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans
from sklearn.preprocessing import StandardScaler
```

---
## Dataset

The project uses two datasets:

### Crop Dataset
Contains agricultural parameters such as:

- Soil type
- Soil quality
- Nutrient levels
- pH value
- Moisture content
- Temperature

### Mandi Dataset
Contains market information such as:

- Crop name
- Market price
- Demand trends

Both datasets are sourced from **Kaggle**.

---
## Data Loading

Example code to load the dataset:

```python
crop_data = pd.read_csv("crop_dataset.csv")
mandi_data = pd.read_csv("mandi_dataset.csv")

print(crop_data.head())
```

---
## Data Preprocessing

```python
features = crop_data[['soil_quality','ph','moisture','temperature']]

scaler = StandardScaler()
scaled_features = scaler.fit_transform(features)
```

---
## Model Training

K-Means clustering is used to group crops based on environmental conditions.

```python
kmeans = KMeans(n_clusters=4, random_state=42)

kmeans.fit(scaled_features)

crop_data['cluster'] = kmeans.labels_
```

---
## Crop Recommendation

Example function for recommending crops:

```python
def recommend_crop(input_data):

    scaled = scaler.transform([input_data])
    cluster = kmeans.predict(scaled)

    recommended = crop_data[crop_data['cluster'] == cluster[0]]

    return recommended['crop_name'].unique()
```

---
## Profit Analysis

The system combines crop clusters with **market price data** to determine profitable crops.

```python
profit_data = crop_data.merge(mandi_data, on="crop_name")

profit_data['expected_profit'] = profit_data['yield'] * profit_data['price']
```

---
## Results

The model helps:

- Identify crops suitable for specific soil conditions
- Analyze market price trends
- Recommend crops with **higher profitability**

---
## Project Structure

```
crop-profit-maximization
│
├── crop_profit_model.ipynb
├── crop_dataset.csv
├── mandi_dataset.csv
└── README.md
```

---
## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Jupyter Notebook

---
## Future Improvements

Possible enhancements:

- Integration with **real-time market price APIs**
- Weather forecasting integration
- Mobile application for farmers
- Deep learning based crop yield prediction

---
