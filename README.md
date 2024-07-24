# Travel Insurance Prediction

This project aims to predict the likelihood of customers purchasing travel insurance based on various features such as age, employment type, annual income, family members, chronic diseases, and travel history. Three different machine learning models are used for this prediction: Logistic Regression, Random Forest and XGBoost.

## Dataset

The dataset contains the following columns:

- `Customer Id`: Unique identifier for each customer.
- `Age`: Age of the customer.
- `Employment Type`: Type of employment (e.g., Private Sector/Self Employed).
- `GraduateOrNot`: Whether the customer is a graduate or not (Yes/No).
- `AnnualIncome`: Annual income of the customer.
- `FamilyMembers`: Number of family members.
- `ChronicDiseases`: Whether the customer has chronic diseases (0/1).
- `FrequentFlyer`: Whether the customer is a frequent flyer (Yes/No).
- `EverTravelledAbroad`: Whether the customer has ever travelled abroad (Yes/No).
- `TravelInsurance`: Target variable indicating if the customer purchased travel insurance (Yes/No).

## Installation

To run the code, you need to have Python installed along with the following packages:

- pandas
- scikit-learn
- xgboost

You can install the required packages using pip:

```sh
pip install pandas scikit-learn xgboost
```

Alternatively, you can create a virtual environment and install the packages:

```sh
python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
pip install pandas scikit-learn xgboost
```

## Usage

1. Clone the repository:

```sh
git clone https://github.com/golnaz76gh/Insurance_forecast.git
cd Insurance_forecast
```

2. Ensure you have the dataset files (`train.csv` and `test.csv`) in the project directory.

3. Open the Jupyter Notebook in Visual Studio Code:

    - Install the Jupyter extension for Visual Studio Code if you haven't already.
    - Open Visual Studio Code and navigate to the project directory.
    - Open the file `insurance.ipynb`.
    - Run all cells to train the models and make predictions on the test dataset.

4. The predictions will be saved in `output.csv` with the following columns:

- `Customer Id`: Unique identifier for each customer.
- `prediction`: The predicted probability of purchasing travel insurance.

## Code Explanation

### Preprocessing

The `preprocess_data` function handles the preprocessing of the training data:

- Categorical variables are encoded using `LabelEncoder`.
- Numerical variables (`Age`, `AnnualIncome`, `FamilyMembers`) are scaled using `StandardScaler`.
- The target variable (`TravelInsurance`) is encoded to numerical values (0 and 1).

The `preprocess_test_data` function applies the same preprocessing steps to the test data.

### Model Training

Three different models are used to train on the preprocessed training data:

1. **Logistic Regression**: A simple and interpretable model for binary classification.
2. **Random Forest Classifier**: An ensemble model that combines multiple decision trees to improve performance and robustness.
3. **XGBoost**: A powerful gradient boosting model known for its performance in various machine learning competitions.

### Predictions

The trained models are used to predict the probabilities of purchasing travel insurance for the test data. These probabilities are saved in `output.csv`.