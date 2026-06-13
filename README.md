# Crop Recommendation System
Machine Learning model that recommends the most suitable crop based on soil nutrients and climate parameters, achieving **92% classification accuracy**.
## Project Overview
Farmers often struggle to decide which crop to grow based on their soil and local climate conditions. This system solves that problem by taking 7 key input parameters and predicting the most suitable crop using a trained Random Forest classifier.
Built end-to-end — from raw data cleaning and EDA to a deployed Flask REST API.
## Key Results

| Metric          | Value                        |
| --------------- | ---------------------------- |
| Model Accuracy  | 92%                          |
| Algorithm       | Random Forest (Scikit-Learn) |
| Dataset Size    | 2,200+ Records               |
| Number of Crops | 22 Crop Classes              |
| Deployment      | Flask REST API               |

## How It Works
Input Parameters → Preprocessing → Trained Random Forest Model → Crop Prediction
### Input Features
* Nitrogen (N)
* Phosphorus (P)
* Potassium (K)
* Temperature (°C)
* Humidity (%)
* Soil pH
* Rainfall (mm)
### Output
Recommended crop name (Rice, Wheat, Maize, Cotton, etc.)

## Model Performance
* Accuracy: **92%**
* Evaluation Methods:
  * Confusion Matrix
  * Classification Report
  * K-Fold Cross Validation
* Best Performing Algorithm: Random Forest

## Tech Stack

| Category         | Tools               |
| ---------------- | ------------------- |
| Language         | Python              |
| Machine Learning | Scikit-Learn        |
| Data Processing  | Pandas, NumPy       |
| Visualization    | Matplotlib, Seaborn |
| API Framework    | Flask               |
| Model Storage    | Pickle              |
| Notebook         | Jupyter Notebook    |
| Version Control  | Git & GitHub        |

## Project Structure
```text
Crop-Recommendation-System/
│
├── data/
│   └── crop_recommendation.csv
│
├── notebooks/
│   └── EDA_and_Model_Training.ipynb
│
├── model/
│   └── crop_model.pkl
│
├── app.py
├── requirements.txt
└── README.md
```
## Installation
### Clone Repository

```bash
git clone https://github.com/aakash7317/Crop-Recommendation-System.git
cd Crop-Recommendation-System
```
### Install Dependencies
```bash
pip install -r requirements.txt
```
### Run Application

```bash
python app.py
```

### Request

```bash
curl -X POST http://localhost:5000/predict \
-H "Content-Type: application/json" \
-d '{"N":90,"P":42,"K":43,"temperature":20.8,"humidity":82.0,"ph":6.5,"rainfall":202.9}'
```
### Response
```json
{
  "crop": "Rice",
  "confidence": 0.94
}
```
## EDA Highlights
* Analyzed distribution of all 7 features across 22 crop classes.
* Found strong correlation between potassium levels and fruit crops.
* Identified optimal pH range of 5.5–7.0.
* Visualized feature importance across all features.

## Model Comparison

| Algorithm           | Accuracy |
| ------------------- | -------- |
| Random Forest       | 92%      |
| Decision Tree       | 88%      |
| Logistic Regression | 82%      |
| Naive Bayes         | 79%      |

## Author

**Aakash Mishra**
B.Tech CSE (2026)
Krishna Institute of Technology, Kanpur
Email: [aakashmishra8303@gmail.com](mailto:aakashmishra8303@gmail.com)
GitHub: https://github.com/aakash7317
