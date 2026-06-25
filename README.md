# Edu-Predict
Link to DataSet: https://archive.ics.uci.edu/dataset/320/student+performance
## Intro
EduPredict is an end-to-end AI solution designed to identify "at-risk" students early in the academic cycle. Unlike standard predictive models, EduPredict not only forecasts academic outcomes (Pass/Fail) but also acts as a Prescriptive AI Agent, searching for the specific behavioral changes a student needs to make to succeed.

👥 Project Team
Hassan Ali (F2023266683)
Muhammad Abdullah Bin Sultan (F2023266663)
🚀 Key Features
Metaheuristic Feature Selection: Implements a custom Binary Snake Optimizer (BSO) to search for the most influential features among 30+ variables.
Predictive Engine: Leverages Random Forest and XGBoost classifiers for high-accuracy forecasting.
Class Imbalance Handling: Utilizes balanced class weighting to ensure at-risk students (the minority class) are correctly identified, solving the "Accuracy Paradox."
Heuristic Intervention Agent: A decision-support tool that performs a State-Space Search to recommend a "Path to Success" (e.g., how much to increase study time to flip a predicted Fail to a Pass).
🧠 AI Techniques Implemented
1. Binary Snake Optimizer (BSO)
Inspired by snake foraging behavior, this metaheuristic search algorithm explores the feature space to find an optimal subset of data. It balances Predictive Accuracy (70%) with Feature Parsimony (30%), ensuring the model is both accurate and interpretable.
2. Random Forest Classification
The "Predictive Brain" of the system. It processes lifestyle, demographic, and academic factors to predict whether a student's final grade (
G
3
G3
) will be a Pass (
≥
10
≥10
) or Fail (
<
10
<10
).
3. Heuristic Search Agent
When a student is predicted to fail, this agent takes over. It iterates through Actionable Features (Study Time, Absences, Social Habits) and queries the model until it finds the minimum change required for a passing prediction.
📊 Dataset
The project utilizes the UCI Student Performance Dataset (Mathematics and Portuguese).
Inputs: 30+ features (Parental education, study time, alcohol consumption, absences, etc.)
Target Variable: 
G
3
G3
 (Binarized into Pass/Fail).
📈 Results
Optimized Accuracy: ~83% using BSO-selected features.
Balanced Sensitivity: By adjusting class weights, the system improved its detection of failing students from 0% (Baseline) to 40%+ (Optimized).
Intervention Logic: Successfully generates prescriptive advice (e.g., "Increase study time AND reduce absences") for 95% of failing test cases.
