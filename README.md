# Predicting Disease Risk Using Linear Regression

## 📌 Project Overview
This project predicts the risk of cardiovascular disease using **Linear Regression**. The dataset contains health-related parameters such as **age, height, weight, blood pressure, cholesterol, glucose levels, smoking, alcohol consumption, and physical activity** to determine whether a person is at risk.

## 📊 Dataset Information
The dataset used in this project is **cardio_train.csv**, which consists of:
- **ID**: Unique identifier (not used in training)
- **Age**: Patient's age (converted from days to years)
- **Gender**: 1 for female, 2 for male
- **Height & Weight**: Used to calculate BMI
- **Blood Pressure (Systolic & Diastolic)**
- **Cholesterol & Glucose Levels** (Categorical: 1 = Normal, 2 = Above Normal, 3 = High)
- **Smoking, Alcohol Intake, Physical Activity** (Binary: 0 = No, 1 = Yes)
- **Cardio**: Target variable (1 = Disease present, 0 = No disease)

## 🔧 Installation & Setup
### 1️⃣ **Clone the Repository**
```bash
git clone https://github.com/your-username/Predicting-Disease-Risk-Using-Linear-Regression.git
cd Predicting-Disease-Risk-Using-Linear-Regression
```

### 2️⃣ **Install Dependencies**
```bash
pip install -r requirements.txt
```

### 3️⃣ **Run the Jupyter Notebook**
```bash
jupyter notebook
```
Open `main.ipynb` and run the cells step by step.

## 🚀 Model Implementation
### 🔹 **Data Preprocessing**
- Removed unnecessary columns (e.g., ID)
- Converted age from days to years
- Applied **StandardScaler** to normalize numerical features

### 🔹 **Training the Model**
- Used **Linear Regression** from `sklearn`
- Split data into **training (80%)** and **testing (20%)** sets
- Evaluated using **Mean Squared Error (MSE) and R² Score**

### 🔹 **Making Predictions**
A sample new patient data is given as input:
```python
new_patient = np.array([[50, 1.75, 80, 120, 80, 2, 1, 0, 0, 1]])
new_patient[:, :5] = scaler.transform(new_patient[:, :5])
predicted_risk = model.predict(new_patient)
```

### 🔹 **Classifying as "Safe" or "At Risk"**
```python
risk_threshold = 0.5  # Adjust this value as needed
status = "Safe" if predicted_risk < risk_threshold else "At Risk"
print(f"Predicted Disease Risk: {predicted_risk[0]:.2f}")
print(f"The person is classified as: {status}")
```

## 📈 Results
- The model predicts a risk score between **0 and 1**.
- If the score is **below 0.5**, the person is classified as "Safe".
- If the score is **0.5 or higher**, the person is classified as "At Risk".

## 🛠 Technologies Used
- **Python**
- **Pandas, NumPy** (Data Processing)
- **Scikit-Learn** (Machine Learning)
- **Matplotlib, Seaborn** (Visualization)

## 📝 Future Improvements
- Improve accuracy using more advanced models like **Random Forest** or **Neural Networks**.
- Deploy the model as a **Flask API** or a **Web App**.
- Add more **feature engineering** techniques.




