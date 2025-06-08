# Stroke Prediction Web App

This web application predicts the likelihood of a stroke based on user-provided health information.

## Overview

The application uses a machine learning model to assess stroke risk. Users input their health data through a web form, and the app displays the model's prediction, along with advice.

## Features

* **Input Form:** Users provide their health information, including gender, age, BMI, and smoking status.
* **Stroke Risk Prediction:** The application predicts the likelihood of a stroke (Likely/Low).
* **Results Page:**
    * If the prediction is "Likely," the page displays recommended measures to take.
    * If the prediction is "Low," the page displays a congratulatory message and encourages a healthy lifestyle.

## Technologies Used

* **Frontend:** HTML, CSS, Bootstrap
* **Backend:** Python, Flask
* **Machine Learning:** Pandas, Scikit-learn, joblib
* **Model:** Logistic Regression

## Files

* `app.py`: Flask application. It handles user input, loads the pre-trained machine learning model, makes predictions, and renders the results.
* `index.html`: HTML file for the main input form.
* `result.html`: HTML file for displaying the prediction results.
* `Stroke Prediction Using Python (3).ipynb`: Jupyter Notebook containing the data analysis, model training, and saving.
* `model.joblib`: Serialized machine learning model (not provided, but its loading is referenced in `app.py`)
* `train.csv`: Training dataset (used in the Jupyter Notebook).
* `test.csv`: Testing dataset (used in the Jupyter Notebook).
* `sample_submission.csv`: Sample submission file.

## Data Preprocessing and Model Training (Notebook)

The `Stroke Prediction Using Python (3).ipynb` notebook contains the following steps:

1.  **Import Libraries:** Import necessary libraries like pandas and numpy.
2.  **Load Data:** Load the training, testing, and sample submission data using pandas.
3.  **Explore the data:** Display the first few rows of the training data.
4.  **Check the distribution of the target variable:** Check how many patients had a stroke and how many didn't.
5.  **Check Data info:** Display info about the data.
6.  **Describe the data:** Display statistical details of the numerical features.
7.  **Check for null values:** The notebook checks for missing values in the dataset.
8.  **Impute missing values:** The missing values in the 'bmi' column are filled with the mean.
9.  **Outlier Analysis:** The code performs an outlier analysis.
10. **Label Encoding:** The notebook encodes categorical features like 'gender', 'ever_married', 'work_type', 'Residence_type', and 'smoking_status'.
11. **Scaling Numerical Features:** The numerical features are scaled using StandardScaler.
12. **Splitting the data:** The data is split into training and testing sets.
13. **Balancing the data:** The notebook uses SMOTE (Synthetic Minority Oversampling Technique) to address the class imbalance in the target variable ('stroke').
14. **Model Training:** A Logistic Regression model is trained on the balanced training data.
15. **Model Evaluation:** The model's performance is evaluated.
16. **Model Saving:** The trained model, along with the preprocessor, is saved to a file named "model.joblib".

## How to Run

1.  **Clone the repository:**
    ```bash
    git clone <your_repo_url>
    ```
2.  **Navigate to the project directory:**
    ```bash
    cd stroke-prediction-app
    ```
3.  **Set up a virtual environment (recommended):**
    ```bash
    python3 -m venv venv
    source venv/bin/activate  # On Linux/macOS
    .\venv\Scripts\activate   # On Windows
    ```
4.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
    (Note: You might need to create a `requirements.txt` file. A basic one is provided below, but ensure it includes all necessary packages.)
5.  **Run the Flask application:**
    ```bash
    python app.py
    ```
6.  **Open your web browser:**
    Open your browser and go to `http://localhost:5000` to access the application.

 # Author: Yashwanth Kumar R
