# 🌍 DisasterRelief-AidPredictor

A machine learning project that predicts the required quantities of critical relief supplies (like food, water, shelter, baby food, medicine, and sanitary items) during disasters. The model uses demographic and severity data to make accurate and scalable predictions, assisting NGOs and government agencies in effective resource allocation.

---

## 🚀 Features

- Predicts relief supply needs based on:
  - Disaster type
  - Severity
  - Age-wise and gender-wise population stats
- Uses a **Random Forest Regressor** pipeline with one-hot encoding and feature scaling
- Includes **hyperparameter tuning** using:
  - GridSearchCV
  - RandomizedSearchCV
- Visualizes output in a tabular format using `PrettyTable`
- Export and reuse the trained model using `pickle`

---

## 📁 Project Structure

📦DisasterRelief-AidPredictor/
├── disaster_relief_data.csv # Input dataset
├── disaster_relief_model.pkl # Trained model (Pickle format)
├── disaster_aid_predictor.py # Main Python script
├── README.md # Project documentation
└── requirements.txt # List of required packages

yaml
Copy
Edit

---

## 📊 Dataset Requirements

The CSV file should contain the following columns:

| Feature                | Description                                 |
|------------------------|---------------------------------------------|
| Disaster Type          | Type of disaster (e.g., Flood, Earthquake) |
| Severity Value         | Numeric severity score                     |
| Total Population       | Total number of people affected            |
| Age 0-12               | Number of children                         |
| Age 12-60              | Number of adults                           |
| Age 60+                | Number of elderly                          |
| Female Population      | Number of females                          |
| (Targets: 6 columns)   | Food, water, shelter, baby food, etc.      |

---

## ⚙️ Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/DisasterRelief-AidPredictor.git
   cd DisasterRelief-AidPredictor
Install dependencies:

bash
Copy
Edit
pip install -r requirements.txt
Run the main script:

bash
Copy
Edit
python disaster_aid_predictor.py
🔍 Sample Prediction
python
Copy
Edit
example = predict_aid("Flood", 150, 60000, 12000, 40000, 8000, 30000)
print(example)
Output (Table Format):

java
Copy
Edit
📌 Predicted Aid Requirements for Disaster Scenario

+------------------------+--------------------+
| Aid Type              | Predicted Quantity |
+------------------------+--------------------+
| Food Supply (kg)       | 11789              |
| Water Supply (liters)  | 54789              |
| Shelter Supply (tents) | 234                |
| Baby Food Supply (kg)  | 764                |
| Medicine Supply (kits) | 433                |
| Sanitary Supply (items)| 1400               |
+------------------------+--------------------+
📦 Model Export
The model is saved as a .pkl file for reuse:

python
Copy
Edit
with open("disaster_relief_model.pkl", "wb") as file:
    pickle.dump(tuned_model, file)
📚 Dependencies
text
Copy
Edit
pandas
numpy
scikit-learn
prettytable
Generate with:

bash
Copy
Edit
pip freeze > requirements.txt
✨ Future Enhancements
Incorporate live disaster feeds (e.g., from APIs like NDMA, NASA)

Build a Streamlit dashboard for real-time interaction

Add feature importance analysis and SHAP explainability

Extend to regional-specific supply predictions

🧠 Credits
Developed by [Your Name] | Guided by AI (ChatGPT)

📜 License
This project is licensed under the MIT License.
