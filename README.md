# Financial-Scoring-App

This repository provides a financial scoring system designed to evaluate the financial health of families based on various metrics such as income, savings, expenses, and more. The project includes a Flask API and a Streamlit application for an intuitive user interface.

# Table of Contents
1. Features
2. Model Logic
3. Setup Instructions
4. Usage
5. Technologies Used

# Features
1. Flask API
  * Endpoint: /get_financial_score
  * Accepts a JSON payload of financial data and returns a financial score between 0 and 100.
  * Includes error handling for missing or invalid inputs.
    
2. Streamlit Application
  * Provides a web-based interface for users to input financial details and calculate their financial score.
  * Displays a breakdown of financial metrics and visualizes the score.
    
# Model Logic
The financial score is calculated based on the following metrics:
  1. Savings-to-Income Ratio: Rewards higher savings relative to income.
  2. Expenses Ratio: Penalizes higher expenses relative to income.
  3. Loan Payments Ratio: Penalizes higher loan payments as a proportion of income.
  4. Credit Card Spending Ratio: Penalizes excessive credit card usage.
  5. Financial Goals Met (%): Rewards achieving financial milestones.
  6. Discretionary Spending: Penalizes higher spending on travel and entertainment.

# Scoring Formula
The score is computed as a weighted sum of normalized metrics:
  * Savings-to-Income: 25%
  * Monthly Expenses: 25%
  * Loan Payments: 20%
  * Credit Card Spending: 15%
  * Financial Goals Met: 10%
  * Discretionary Spending: 5%
* The final score is scaled to fall between 0 and 100.

# Setup Instructions
**Prerequisites**
- Python 3.8 or above
- Libraries: Flask, pandas, streamlit, base64, matplotlib, seaborn
  
**Step 1: Clone the Repository**
```bash
git clone https://github.com/yourusername/financial-scoring-app.git
cd financial-scoring-app
```

**Step 2: Set Up Virtual Environment**
```bash
python -m venv env
source env/bin/activate  # On Windows: env\Scripts\activate
```

**Step 3: Install Dependencies**
```bash
pip install -r requirements.txt
```

**Step 4: Run the Flask API**
- Navigate to the flask_api.py file and execute:
```bash
python flask_api.py
```
- The API will be available at http://127.0.0.1:5000.

**Step 5: Run the Streamlit App**
- Navigate to the streamlit_app.py file and execute:
```bash
streamlit run streamlit_app.py
```

* The Streamlit app will open in your default browser.

# Usage
**Using the Flask API**
- Send a POST request to ```http://127.0.0.1:5000/get_financial_score``` with the following JSON payload:
```bash
{
  "Income": 50000,
  "Savings": 10000,
  "Expenses": 15000,
  "LoanPayments": 5000,
  "CreditCardSpending": 2000,
  "TravelEntertainment": 3000,
  "Amount": 4000,
  "FinancialGoalsMet": 75
}
```
- The API will return a response with the calculated financial score.
- I used POSTMAN for testing
  
**Using the Streamlit App**
- Input your financial details into the provided fields.
- Click on "Calculate Financial Score" to view your results.
  
**Technologies Used**
- Flask: For creating the backend API.
- Streamlit: For building an interactive frontend application.
- Pandas: For data manipulation and calculations.
- Matplotlib & Seaborn: For data visualization.
- CSV Dataset: Contains sample financial and transactional data for testing.

# Acknowledgments
This project is part of the Sustain Farmers Initiative
