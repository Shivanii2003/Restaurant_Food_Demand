# 🍽️ Restaurant Food Order Forecasting

## 📌 Overview
The **Restaurant Food Order Forecasting** project predicts the **number of food orders** for different meals across multiple fulfillment centers using historical sales data.  
The model helps restaurants **optimize inventory**, **reduce food waste**, and **improve customer satisfaction**.

This project uses **XGBoost Regressor** for prediction and is deployed as an **interactive Streamlit web application**.

---

## 📊 Dataset
We used three datasets:

1. **train.csv** – Historical demand data for meals.
2. **fulfilment_center_info.csv** – Metadata about fulfillment centers (location, type, operational area).
3. **meal_info.csv** – Metadata about meals (category, cuisine).

**Key Features:**
- `week` – Week number of the year
- `center_id` – Fulfillment center identifier
- `meal_id` – Meal identifier
- `checkout_price` – Final price paid by customer
- `base_price` – Base price of the meal
- `emailer_for_promotion` – Whether the meal was promoted via email
- `homepage_featured` – Whether the meal was featured on homepage
- `category`, `cuisine` – Meal type
- `city_code`, `region_code` – Location details
- `center_type` – Type of fulfillment center
- `op_area` – Operational area size
- `num_orders` – Number of orders (Target Variable)

---

## ⚙️ Steps Involved
### 1. Data Loading
Merging all datasets into a single DataFrame.

### 2. Data Preprocessing
- Handling missing values
- Encoding categorical variables (Label Encoding)
- Feature scaling for numerical variables

### 3. Feature Engineering
- Calculated **price difference** and **discount percentage**
- Converted boolean values to integers

### 4. Model Training
- **Algorithm Used:** XGBoost Regressor
- Train-Test Split: 80%-20%
- Hyperparameter tuning for best results

### 5. Model Evaluation
Metrics Used:
- **R² Score**
- **Mean Squared Error (MSE)**

### 6. Deployment
- **Framework:** Streamlit
- Input form for user-provided feature values
- Real-time order prediction

---

## 🚀 How to Run
1. Clone the repository:
```bash
git clone https://github.com/Shivanii2003/Restaurant_Food_Demand
```
2. Install dependencies:
```bash
pip install -r requirements.txt
```
3. Run the Streamlit app:
```bash
streamlit run app.py
```

---

## 📌 Example Prediction
User provides:
- Week: `33`
- Center ID: `55`
- Meal ID: `1885`
- Checkout Price: `240`
- Base Price: `270`
- Email Promotion: `1`
- Homepage Featured: `0`
- Category: `Beverages`
- Cuisine: `Indian`
- City Code: `3`
- Region Code: `56`
- Center Type: `Type A`
- Operational Area: `3.5`

💡 **Predicted Orders:** `246`

---

## 📈 Results
The XGBoost model provided:
- **R² Score:** ~0.88
- **MSE:** Low enough for reliable forecasts

---

## 📌 Future Improvements
- Include external factors like holidays, festivals, and weather
- Implement real-time order forecasting
- Deploy on cloud (AWS, Azure, GCP)
- Build an automated inventory ordering system

