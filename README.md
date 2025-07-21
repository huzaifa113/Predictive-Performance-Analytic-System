# Predictive-Performance-Analytic-System
Predictive Performance Analytic System to predict students performance and scenario simulations

Overview
The Predictive Performance Analytics System (PPAS) is a machine learning pipeline designed to predict student academic performance and assess risk levels based on key educational metrics. This project leverages synthetic student data to train a model that predicts final grades and provides insights into potential interventions to improve student outcomes. The system includes an interactive web interface built with Gradio for real-time predictions and scenario simulations.
Key features:

Grade Prediction: Predicts a student's final grade based on attendance, previous exam marks, assignment submission rate, engagement metrics, and historical GPA.
Risk Assessment: Classifies students into "High Risk," "Medium Risk," or "Low Risk" based on predicted grades.
Scenario Simulation: Allows users to simulate the impact of increasing specific features (e.g., attendance) on predicted grades.

Usage
The notebook is divided into several steps, each with a specific purpose. Follow these steps to execute the project:

Step 0: Data Generation

Generates a synthetic dataset of 1000 students with features like attendance, previous exam marks, assignment submission rate, engagement metrics, historical GPA, and final grades.
Output: Saves student_data.xlsx in the working directory.


Step 1: Data Pre-Processing

Loads the dataset, checks for missing values, visualizes feature distributions, analyzes outliers, and performs correlation analysis.
Scales features using MinMaxScaler and splits the data into training, validation, and test sets.


Step 2: Model Training and Evaluation

Trains an XGBoost model within a scikit-learn pipeline, optimized using GridSearchCV.
Evaluates the model using metrics like Mean Absolute Error (MAE), Mean Squared Error (MSE), and R² score.
Visualizes feature importance to understand key predictors.


Step 3: Gradio Interface

Launches an interactive web interface using Gradio.
Predict Grade: Enter student data (attendance, marks, etc.) to get a predicted grade and risk level.
Run Scenario Simulation: Simulate interventions by increasing a selected feature (e.g., attendance by 10%) to see the impact on the predicted grade.



Try it out here:
https://huggingface.co/spaces/huzaifa113/PPAS

<img width="1350" height="619" alt="1" src="https://github.com/user-attachments/assets/ffa9a4ec-4e92-4efb-b0f4-b20ef40bb60f" />
<img width="1349" height="316" alt="2" src="https://github.com/user-attachments/assets/245f6d80-3668-4198-8183-81c57c8fb6d8" />


Example

Predict Grade:
Input: Attendance=75%, Marks=80%, Assignment=70%, Engagement=65%, GPA=3.0
Output: Predicted Grade: ~78.50%, Risk Level: Low Risk


Run Simulation:
Increase Attendance by 10%
Output: Original Grade: 78.50% (Low Risk), New Grade: ~81.20% (Low Risk)


Notes

GPU Support: The notebook is configured to use a GPU (e.g., T4 in Colab) for faster model training. Ensure GPU runtime is enabled in Colab if desired.
File Outputs: The synthetic dataset (student_data.xlsx) and model visualizations are saved in the working directory.
Gradio Interface: In Colab, the Gradio interface generates a public URL (valid for 72 hours). For local execution, it runs on localhost.
Converting to .py: To convert the notebook to a Python script, run:jupyter nbconvert --to python PPAS_Model.ipynb


License
This project is licensed under the MIT License. See the LICENSE file for details.
