<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Stroke Prediction Web App</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
            color: #333;
            line-height: 1.6;
        }
        h1 {
            text-align: center;
            padding: 20px 0;
            background-color: #eee;
            margin: 0 0 20px 0;
        }
        h2 {
            margin-top: 30px;
            padding-bottom: 5px;
            border-bottom: 1px solid #ddd;
        }
        h3 {
            margin-top: 20px;
        }
        p {
            margin-bottom: 10px;
        }
        ul, ol {
            margin-bottom: 10px;
        }
        ul li {
            list-style-type: disc;
            margin-left: 20px;
        }
        ol li {
            margin-left: 20px;
        }
        .highlight {
            background-color: #fff8dc;
            padding: 2px 5px;
            border-radius: 3px;
        }
        pre {
            background-color: #f7f7f7;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            overflow-x: auto;
            margin: 10px 0;
            font-size: 14px;
            line-height: 1.4;
            white-space: pre-wrap;
            word-wrap: break-word;
        }
        code {
            font-family: monospace;
            font-size: 14px;
        }
        .container {
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
            background-color: #fff;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }
        @media screen and (max-width: 600px) {
            .container {
                padding: 10px;
            }
            pre {
                font-size: 12px;
            }
            code {
                font-size: 12px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Stroke Prediction Web App</h1>
        <p>This web application predicts the likelihood of a stroke based on user-provided health information.</p>

        <h2>Overview</h2>
        <p>The application uses a machine learning model to assess stroke risk. Users input their health data through a web form, and the app displays the model's prediction, along with advice.</p>

        <h2>Features</h2>
        <ul>
            <li><strong>Input Form:</strong> Users provide their health information, including gender, age, BMI, and smoking status.</li>
            <li><strong>Stroke Risk Prediction:</strong> The application predicts the likelihood of a stroke (Likely/Low).</li>
            <li><strong>Results Page:</strong>
                <ul>
                    <li>If the prediction is "Likely," the page displays recommended measures to take.</li>
                    <li>If the prediction is "Low," the page displays a congratulatory message and encourages a healthy lifestyle.</li>
                </ul>
            </li>
        </ul>

        <h2>Technologies Used</h2>
        <ul>
            <li><strong>Frontend:</strong> HTML, CSS, Bootstrap</li>
            <li><strong>Backend:</strong> Python, Flask</li>
            <li><strong>Machine Learning:</strong> Pandas, Scikit-learn, joblib</li>
             <li><strong>Model:</strong> Logistic Regression</li>
        </ul>

        <h2>Files</h2>
        <ul>
            <li><code>app.py</code>: Flask application. It handles user input, loads the pre-trained machine learning model, makes predictions, and renders the results.</li>
            <li><code>index.html</code>: HTML file for the main input form.</li>
            <li><code>result.html</code>: HTML file for displaying the prediction results.</li>
            <li><code>Stroke Prediction Using Python (3).ipynb</code>: Jupyter Notebook containing the data analysis, model training, and saving.</li>
            <li><code>model.joblib</code>: Serialized machine learning model (not provided, but its loading is referenced in <code>app.py</code>)</li>
            <li><code>train.csv</code>: Training dataset (used in the Jupyter Notebook).</li>
            <li><code>test.csv</code>: Testing dataset (used in the Jupyter Notebook).</li>
            <li><code>sample_submission.csv</code>: Sample submission file.</li>
        </ul>

        <h2>Data Preprocessing and Model Training (Notebook)</h2>
        <p>The <code>Stroke Prediction Using Python (3).ipynb</code> notebook contains the following steps:</p>
        <ol>
            <li><strong>Import Libraries:</strong> Import necessary libraries like pandas and numpy.</li>
            <li><strong>Load Data:</strong> Load the training, testing, and sample submission data using pandas.</li>
            <li><strong>Explore the data:</strong> Display the first few rows of the training data.</li>
            <li><strong>Check the distribution of the target variable:</strong> Check how many patients had a stroke and how many didn't.</li>
            <li><strong>Check Data info:</strong> Display info about the data.</li>
            <li><strong>Describe the data:</strong> Display statistical details of the numerical features.</li>
            <li><strong>Check for null values:</strong> The notebook checks for missing values in the dataset.</li>
            <li><strong>Impute missing values:</strong> The missing values in the 'bmi' column are filled with the mean.</li>
            <li><strong>Outlier Analysis:</strong> The code performs an outlier analysis.</li>
            <li><strong>Label Encoding:</strong> The notebook encodes categorical features like 'gender', 'ever_married', 'work_type', 'Residence_type', and 'smoking_status'.</li>
            <li><strong>Scaling Numerical Features:</strong> The numerical features are scaled using StandardScaler.</li>
            <li><strong>Splitting the data:</strong> The data is split into training and testing sets.</li>
            <li><strong>Balancing the data:</strong> The notebook uses SMOTE (Synthetic Minority Oversampling Technique) to address the class imbalance in the target variable ('stroke').</li>
            <li><strong>Model Training:</strong> A Logistic Regression model is trained on the balanced training data.</li>
            <li><strong>Model Evaluation:</strong> The model's performance is evaluated.</li>
            <li><strong>Model Saving:</strong> The trained model, along with the preprocessor, is saved to a file named "model.joblib".</li>
        </ol>

        <h2>How to Run</h2>
        <ol>
            <li><strong>Clone the repository:</strong>
                <pre><code>git clone &lt;your_repo_url&gt;</code></pre>
            </li>
            <li><strong>Navigate to the project directory:</strong>
                <pre><code>cd stroke-prediction-app</code></pre>
            </li>
            <li><strong>Set up a virtual environment (recommended):</strong>
                <pre><code>python3 -m venv venv
source venv/bin/activate  # On Linux/macOS
venv\Scripts\activate  # On Windows</code></pre>
            </li>
            <li><strong>Install dependencies:</strong>
                <pre><code>pip install -r requirements.txt</code></pre>
                <p>(Note: You might need to create a <code>requirements.txt</code> file. A basic one is provided below, but ensure it includes all necessary packages.)</p>
            </li>
            <li><strong>Run the Flask application:</strong>
                <pre><code>python app.py</code></pre>
            </li>
            <li><strong>Open your web browser:</strong>
                <p>Open your browser and go to http://localhost:5000 to access the application.</p>
            </li>
        </ol>

        <h2>requirements.txt</h2>
        <p>A basic <code>requirements.txt</code> file should contain:</p>
        <pre><code>Flask
pandas
scikit-learn
joblib</code></pre>

        <h2>Important Notes</h2>
        <ul>
            <li>The <code>model.joblib</code> file, which contains the trained machine learning model, is assumed to be present. The application will not run without it. This file is generated by the <code>Stroke Prediction Using Python (3).ipynb</code> notebook.</li>
            <li>The application expects the data columns to match those used during training (see the notebook).</li>
            <li>Ensure that the versions of the libraries in your environment match those used during model training to avoid compatibility issues.</li>
            <li>The notebook contains the model training process, including data preprocessing, feature engineering, and model selection.</li>
            <li>The web application provides a user-friendly interface for getting stroke predictions.</li>
        </ul>
    </div>
</body>
</html>
