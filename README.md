# Credit Scoring Prediction 
## 📌 Explanation

### 1. Installing Libraries
Essential Python libraries are imported to handle data processing, visualization, and machine learning tasks:
- **pandas, numpy** → Data manipulation and numerical computations  
- **matplotlib** → Visualization  
- **scikit-learn** → Preprocessing, modeling, and evaluation  
- **faker** → Generating synthetic data  

---

### 2. Generating the Dataset
Since real credit scoring datasets are private and sensitive, a **synthetic dataset** is generated using:
- **NumPy** → For numerical distributions (income, credit score, age, credit history).  
- **Faker** → To simulate realistic data samples.  

The dataset contains **1000 records** with the following columns:
- `income` → Annual income of the person  
- `age` → Age of the person  
- `credit_history` → Credit history length/score  
- `credit_score` → Target label (ranges from 300 to 850)  

---

### 3. Data Preprocessing
Data preprocessing is performed before training the model:
- Standardization using **StandardScaler**.  
- Creating a preprocessing pipeline with **ColumnTransformer**.  
- Splitting the dataset into features (`X`) and target (`y`).  

---

### 4. Splitting the Data
The dataset is divided into:
- **Training set (80%)** → Used for training the model.  
- **Testing set (20%)** → Used to evaluate performance.  

A fixed **random_state** ensures reproducibility of results.  

---

### 5. Training the Regression Model
A **Ridge Regression** model is used because it performs well with continuous numerical predictions and avoids overfitting using L2 regularization.  

Steps include:
1. Creating a **pipeline** with preprocessing and Ridge regression.  
2. Performing **hyperparameter tuning** with `GridSearchCV`.  
3. Training the model on the dataset.  

---

### 6. Evaluating the Model
The model is evaluated on the test dataset using:
- **R² Score** → Measures goodness of fit.  
- **Mean Squared Error (MSE)** → Measures prediction error.  

Example results:
- Best Ridge parameters found via GridSearch.  
- R² Score: ~0.85  
- MSE: Low, meaning good accuracy.  

---

### 7. Making Predictions with New Data
A function `predict_credit_score()` is created to predict a credit score based on new input values:
- Example input:  
  - Income = 60000  
  - Age = 35  
  - Credit history = 5  

- Example output:  Predicted credit score: 678.45
 
