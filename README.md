
# 🌱 Crop Recommendation System

An end-to-end **Machine Learning-based Crop Recommendation System** that recommends the most suitable crop based on **soil nutrients and environmental conditions**.

The application takes seven agricultural parameters — **Nitrogen, Phosphorus, Potassium, Temperature, Humidity, Soil pH, and Rainfall** — and uses a trained **Random Forest Classifier** to predict the most suitable crop.

The trained model is integrated into a **Flask web application** with a responsive web interface where users can enter soil and climate parameters and receive a crop recommendation.

---

# 🚀 Features

* 🌱 **Crop Recommendation**

  * Predicts the most suitable crop based on soil and climate conditions.

* 🧪 **Soil Nutrient Analysis**

  * Nitrogen (N)
  * Phosphorus (P)
  * Potassium (K)

* 🌦️ **Environmental Condition Analysis**

  * Temperature
  * Humidity
  * Rainfall
  * Soil pH

* 🤖 **Machine Learning Prediction**

  * Uses a trained Random Forest classification model.

* 📊 **Data Analysis & Visualization**

  * Exploratory Data Analysis performed using Pandas, Matplotlib, and Seaborn.

* ⚙️ **Feature Scaling**

  * Uses MinMaxScaler followed by StandardScaler before prediction.

* 🌐 **Flask Web Application**

  * Provides a browser-based interface for entering agricultural parameters and receiving recommendations.

* 🌾 **22 Crop Classes**

  * The trained system supports prediction across 22 different crop categories.

---

# 🧠 How It Works

```text
        Soil & Climate Parameters
                  │
                  ▼
       ┌──────────────────────┐
       │ Input Validation     │
       └──────────┬───────────┘
                  │
                  ▼
       ┌──────────────────────┐
       │ MinMaxScaler         │
       └──────────┬───────────┘
                  │
                  ▼
       ┌──────────────────────┐
       │ StandardScaler       │
       └──────────┬───────────┘
                  │
                  ▼
       ┌──────────────────────┐
       │ Random Forest Model  │
       └──────────┬───────────┘
                  │
                  ▼
          Predicted Crop
                  │
                  ▼
       ┌──────────────────────┐
       │ Flask Web Interface  │
       └──────────────────────┘
```

---

# 📥 Input Features

The application uses **7 input parameters**.

| Feature        | Description                | Unit    |
| -------------- | -------------------------- | ------- |
| Nitrogen (N)   | Nitrogen content in soil   | Numeric |
| Phosphorus (P) | Phosphorus content in soil | Numeric |
| Potassium (K)  | Potassium content in soil  | Numeric |
| Temperature    | Environmental temperature  | °C      |
| Humidity       | Relative humidity          | %       |
| pH             | Soil acidity/alkalinity    | pH      |
| Rainfall       | Rainfall level             | mm      |

---

# 🌾 Supported Crops

The prediction system contains 22 crop classes:

```text
1. Rice
2. Maize
3. Jute
4. Cotton
5. Coconut
6. Papaya
7. Orange
8. Apple
9. Muskmelon
10. Watermelon
11. Grapes
12. Mango
13. Banana
14. Pomegranate
15. Lentil
16. Blackgram
17. Mungbean
18. Mothbeans
19. Pigeonpeas
20. Kidneybeans
21. Chickpea
22. Coffee
```

---

# 🤖 Machine Learning Pipeline

The project was developed through an end-to-end machine learning workflow.

```text
Raw Dataset
     │
     ▼
Data Exploration
     │
     ▼
Exploratory Data Analysis
     │
     ▼
Feature / Target Separation
     │
     ▼
Train-Test Split
     │
     ▼
MinMax Scaling
     │
     ▼
Standard Scaling
     │
     ▼
Multiple ML Models
     │
     ▼
Model Comparison
     │
     ▼
Random Forest Selection
     │
     ▼
Model Training
     │
     ▼
Model Serialization
     │
     ▼
Flask Application
```

---

# 📊 Model Development

Multiple machine learning algorithms were evaluated during the model development process, including:

* Logistic Regression
* Gaussian Naive Bayes
* Support Vector Classifier
* K-Nearest Neighbors
* Decision Tree
* Extra Tree
* Random Forest
* Bagging Classifier
* Gradient Boosting
* AdaBoost

The **Random Forest Classifier** was selected as the final model and serialized using Python's `pickle` module.

---

# 📈 Model Performance

The project reports approximately **92% classification accuracy** for the selected Random Forest model.

The notebooks also include model evaluation using:

* Accuracy Score
* Confusion Matrix
* Classification Report
* Model comparison

The train-test split used in the notebook is:

```python
train_test_split(
    x,
    y,
    test_size=0.2,
    random_state=42
)
```

> The reported accuracy depends on the dataset split and training configuration. It should not be interpreted as a guaranteed real-world prediction accuracy.

---

# ⚙️ Feature Scaling

The application uses two sequential preprocessing steps.

### 1. Min-Max Scaling

```python
MinMaxScaler()
```

### 2. Standard Scaling

```python
StandardScaler()
```

During prediction, the input follows the same preprocessing pipeline used during model training:

```text
Raw Input
   ↓
MinMaxScaler
   ↓
StandardScaler
   ↓
Random Forest
   ↓
Crop Prediction
```

The trained preprocessing objects are saved as:

```text
minmaxscaler.pkl
standardscaler.pkl
```

---

# 🌐 Flask Web Application

The trained model is integrated into a Flask web application.

The application provides a browser-based interface where users can enter:

```text
Nitrogen
Phosphorus
Potassium
Temperature
Humidity
pH
Rainfall
```

After submitting the values, the Flask application:

1. Reads the form inputs.
2. Converts the values to numeric format.
3. Creates the feature array.
4. Applies the saved MinMaxScaler.
5. Applies the saved StandardScaler.
6. Sends the processed features to the Random Forest model.
7. Maps the predicted class to the corresponding crop.
8. Displays the recommendation on the web page.

---

# 🖥️ Application Interface

The frontend is implemented using:

* HTML
* CSS
* JavaScript
* Flask Templates

The interface is designed as a **CropSense AI** dashboard with an agriculture-focused visual theme.

The user enters the required soil and climate parameters and receives a recommendation such as:

```text
Rice is the best crop to be cultivated right there
```

---

# 📂 Project Structure

The repository currently contains the following main components:

```text
Crop-Recommendation-System/
│
├── Crop Recommendation Using Machine Learning.ipynb
├── Crop_Recommendation_EDA_and_Model.ipynb
│
├── Crop_recommendation.csv
│
├── model.pkl
├── minmaxscaler.pkl
├── standardscaler.pkl
│
├── app.py
│
├── templates/
│   └── index.html
│
├── .gitignore
└── README.md
```

### `app.py`

Contains the Flask application and prediction logic.

Responsibilities:

* Flask server
* Form input handling
* Feature preprocessing
* Model prediction
* Crop class mapping
* Result rendering

### `model.pkl`

Serialized Random Forest classification model.

### `minmaxscaler.pkl`

Saved MinMaxScaler used during preprocessing.

### `standardscaler.pkl`

Saved StandardScaler used during preprocessing.

### `Crop_recommendation.csv`

Dataset containing soil, climate, and crop-label information.

### Jupyter Notebooks

Used for:

* Data exploration
* EDA
* Data preprocessing
* Model training
* Algorithm comparison
* Model evaluation
* Model serialization

---

# 🛠️ Technology Stack

| Category                | Technology                   |
| ----------------------- | ---------------------------- |
| Programming Language    | Python                       |
| Machine Learning        | Scikit-Learn                 |
| Model                   | Random Forest Classifier     |
| Data Processing         | Pandas, NumPy                |
| Data Visualization      | Matplotlib, Seaborn          |
| Feature Scaling         | MinMaxScaler, StandardScaler |
| Web Framework           | Flask                        |
| Model Serialization     | Pickle                       |
| Development Environment | Jupyter Notebook             |
| Frontend                | HTML, CSS, JavaScript        |
| Version Control         | Git & GitHub                 |

---

# 📦 Installation

## 1. Clone the Repository

```bash
git clone https://github.com/aakash7317/Crop-Recommendation-System.git
```

Navigate to the project:

```bash
cd Crop-Recommendation-System
```

---

## 2. Create a Virtual Environment

### Windows

```bash
python -m venv venv
```

Activate:

```bash
venv\Scripts\activate
```

### Linux / macOS

```bash
python3 -m venv venv
```

```bash
source venv/bin/activate
```

---

## 3. Install Dependencies

```bash
pip install -r requirements.txt
```

---

# ▶️ Run the Application

Start the Flask application:

```bash
python app.py
```

The application runs on:

```text
http://localhost:5000
```

Open the address in your browser and enter the required soil and climate parameters.

---

# 🧪 Example Input

```text
Nitrogen:     90
Phosphorus:   42
Potassium:    43
Temperature:  20.8
Humidity:     82.0
pH:           6.5
Rainfall:     202.9
```

The system processes the values and predicts the most suitable crop.

Example:

```text
Rice is the best crop to be cultivated right there
```

---

# 🔬 Exploratory Data Analysis

The project includes dedicated notebooks for data exploration and model development.

The EDA covers analysis of the agricultural features across different crop classes.

Key analysis areas include:

* Feature distributions
* Crop-wise feature analysis
* Correlation analysis
* Feature relationships
* Model feature importance
* Classification performance

---

# 📊 Machine Learning Workflow

```text
                 Dataset
                    │
                    ▼
             Data Cleaning
                    │
                    ▼
                  EDA
                    │
                    ▼
            Feature Selection
                    │
                    ▼
             Train/Test Split
                    │
                    ▼
             Feature Scaling
                    │
                    ▼
        ┌───────────────────────┐
        │ Multiple ML Algorithms │
        └───────────┬───────────┘
                    │
                    ▼
             Model Evaluation
                    │
                    ▼
            Random Forest
                    │
                    ▼
             Model Pickling
                    │
                    ▼
             Flask Deployment
```

---

# 🎯 Use Cases

This project can be used as a foundation for:

* 🌾 Smart agriculture systems
* 👨‍🌾 Crop selection assistance
* 🌱 Precision agriculture applications
* 🧪 Soil-based crop analysis
* 📊 Agricultural decision-support systems
* 🎓 Machine learning education projects

---

# 🔥 Key Project Highlights

* Built an end-to-end **Machine Learning crop recommendation system**.
* Used **7 soil and environmental parameters** for prediction.
* Compared multiple classification algorithms.
* Selected **Random Forest Classifier** as the final model.
* Achieved approximately **92% classification accuracy** in the project evaluation.
* Implemented sequential **MinMaxScaler + StandardScaler** preprocessing.
* Serialized the trained model and preprocessing objects using Pickle.
* Integrated the ML pipeline into a **Flask web application**.
* Implemented prediction for **22 different crop classes**.
* Created a responsive agriculture-focused web interface.
* Performed EDA and model evaluation using Jupyter notebooks.

---

# 🚧 Future Improvements

* 🌦️ Integrate real-time weather APIs.
* 📍 Add location-based weather and soil information.
* 🧪 Integrate real-time soil sensor data.
* 📱 Develop a mobile application.
* 📊 Add crop suitability visualizations.
* 💰 Add estimated crop profitability.
* 💧 Add irrigation recommendations.
* 🌱 Add fertilizer recommendations.
* ☁️ Deploy the application to a cloud platform.
* 🔄 Retrain the model using larger and more diverse agricultural datasets.
* 🤖 Compare the Random Forest model with advanced ensemble models.
* 📈 Add probability/confidence visualization for predictions.

---

# ⚠️ Limitations

* The recommendation is based on the features available in the training dataset.
* Real-world crop suitability can depend on additional factors such as soil type, geographic location, season, pests, irrigation, and local weather.
* The reported model accuracy comes from the project's evaluation setup and does not guarantee the same performance on unseen real-world agricultural data.
* The current Flask application uses manually entered values rather than live sensor or weather data.

---

# 👨‍💻 Author

**Aakash Mishra**

B.Tech Computer Science & Engineering — 2026
Krishna Institute of Technology, Kanpur

**Email:** [aakashmishra8303@gmail.com](mailto:aakashmishra8303@gmail.com)

**GitHub:** aakashmishra01

---

# ⭐ Project

If you find this project useful, consider giving the repository a ⭐ on GitHub.

