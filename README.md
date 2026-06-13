 Crop Recommendation System
 
Machine Learning model that recommends the most suitable crop based on soil nutrients and climate parameters — achieving 92% classification accuracy.
📌 Project Overview
Farmers often struggle to decide which crop to grow based on their soil and local climate conditions. This system solves that problem by taking 7 key input parameters and predicting the most suitable crop using a trained Random Forest classifier.
Built end-to-end — from raw data cleaning and EDA to a deployed Flask REST API.

🎯 Key Results
MetricValueModel Accuracy92%AlgorithmRandom Forest (Scikit-Learn)Dataset Size2,200+ recordsNumber of Crops22 crop classesDeploymentFlask REST API

🧠 How It Works
Input Parameters → Preprocessing → Trained RF Model → Crop Prediction
Input features:
N — Nitrogen content in soil
P — Phosphorus content in soil
K — Potassium content in soil
Temperature (°C)
Humidity (%)
pH level of soil
Rainfall (mm)
Output: Recommended crop name (e.g., Rice, Wheat, Maize, Cotton, etc.)
📊 Model Performance
Accuracy: 92% on test set
Evaluation methods: Confusion Matrix · Classification Report · K-Fold Cross-Validation
Best performing algorithm: Random Forest (compared against Logistic Regression, Decision Tree, Naive Bayes)

🛠️ Tech Stack

CategoryToolsLanguagePython 3.xML LibraryScikit-LearnData ProcessingPandas, NumPyVisualizationMatplotlib, SeabornAPI FrameworkFlaskModel SavingPickleNotebookJupyter NotebookVersion ControlGit & GitHub

📁 Project Structure

Crop-Recommendation-System/
│
├── data/
│   └── crop_recommendation.csv      # Dataset (2200+ records)
│
├── notebooks/
│   └── EDA_and_Model_Training.ipynb # Full analysis notebook
│
├── model/
│   └── crop_model.pkl               # Trained Random Forest model
│
├── app.py                           # Flask API application
├── requirements.txt                 # Dependencies
└── README.md

🚀 How to Run Locally

1. Clone the repository

bashgit clone https://github.com/aakash7317/Crop-Recommendation-System.git
cd Crop-Recommendation-System

2. Install dependencies

bashpip install -r requirements.txt

3. Run the Flask API

bashpython app.py

4. Make a prediction (API call)

bashcurl -X POST http://localhost:5000/predict \
  -H "Content-Type: application/json" \
  -d '{"N": 90, "P": 42, "K": 43, "temperature": 20.8, "humidity": 82.0, "ph": 6.5, "rainfall": 202.9}'

Expected response:

json{
  "crop": "Rice",
  "confidence": 0.94
}


📈 EDA Highlights
Analyzed distribution of all 7 features across 22 crop classes
Found strong correlation between K levels and fruit crops (mango, grapes, watermelon)
Identified optimal pH range (5.5–7.0) common across most crops
Visualised feature importance — Rainfall and Humidity were top predictors

🔍 Model Comparison

AlgorithmAccuracyRandom Forest92%Decision Tree88%Logistic Regression82%Naive Bayes79%

👨‍💻 Author

Aakash Mishra
B.Tech CSE 2026 — Krishna Institute of Technology, Kanpur
📧 aakashmishra8303@gmail.com
📞 8948830317
🔗 LinkedIn
🐙 GitHub
⭐ If this project helped you, please give it a st
