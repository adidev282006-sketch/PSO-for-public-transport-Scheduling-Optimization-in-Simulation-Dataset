# 🚍 AI-Based Public Transport Scheduling Optimization using PSO

## 📌 Project Overview

This project presents an intelligent public transport scheduling system that combines **Machine Learning, Particle Swarm Optimization (PSO), data analysis, and interactive visualization**.

A simulated transportation dataset containing **500,000 records and 17 features** is generated using Python. A **Random Forest Classifier** is then used to classify passenger demand into different demand levels. The predicted demand is subsequently used in a Particle Swarm Optimization framework to explore bus allocation strategies.

The project also includes an interactive **Gradio dashboard** for exploring transportation demand, model evaluation, visualizations, and optimization-related outputs.

---

## 🎯 Objectives

- Generate a large simulated public transportation dataset.
- Analyze passenger demand and transportation-related factors.
- Classify passenger demand into different demand categories.
- Apply Random Forest for demand classification.
- Tune model hyperparameters using GridSearchCV.
- Apply Particle Swarm Optimization for bus allocation.
- Design a fitness function based on unmet demand and unused capacity.
- Visualize demand and machine learning performance.
- Develop an interactive dashboard for system exploration.

---

## 🧠 Project Workflow

```text
Simulated Transport Dataset
            ↓
     Data Preprocessing
            ↓
 Exploratory Data Analysis
            ↓
   Demand Classification
            ↓
   Random Forest Model
            ↓
 GridSearchCV Optimization
            ↓
 Predicted Passenger Demand
            ↓
 Particle Swarm Optimization
            ↓
    Bus Allocation Analysis
            ↓
 Interactive Gradio Dashboard
```
-----

📊 Dataset

The project generates a simulated transportation dataset using NumPy and Pandas.

Dataset Size
Records: 500,000
Features: 17
Main Features
Feature	Description
route_id	Public transport route identifier
bus_id	Bus identifier
hour	Hour of the day
day_of_week	Day of the week
month	Month
distance_km	Route distance
weather	Weather condition
fuel_price	Fuel price
traffic_level	Simulated traffic level
passenger_demand	Simulated passenger demand
delay_minutes	Estimated transportation delay
cost	Simulated transportation cost

Additional noise features are also included to make the simulated dataset more realistic for experimentation.


🔎 Data Generation

Passenger demand is generated using multiple factors including:

Time of day
Day of week
Weather
Random variation

Traffic level is also generated based on the hour of the day and random variation.

Transportation cost incorporates factors such as:

Distance
Traffic
Passenger demand
Delay
Fuel price
Time-related effects
Random noise

The generated dataset is saved as:

ultimate_transport_dataset.csv


🤖 Machine Learning
Demand Classification

A Random Forest Classifier is used to classify passenger demand.

The demand is converted into three classes:

Class 0 → Low Demand
Class 1 → Medium Demand
Class 2 → High Demand

The machine learning pipeline includes:

StandardScaler
      ↓
Random Forest Classifier


⚙️ Hyperparameter Tuning

GridSearchCV is used for hyperparameter tuning.

The search space includes:

n_estimators = [50, 100]
max_depth = [5, 10]

The best configuration recorded in the notebook was:

n_estimators = 50
max_depth = 5


📈 Model Evaluation

The notebook evaluates the classification model using:

Accuracy
Precision
Recall
F1-score
ROC-AUC
Confusion Matrix
ROC Curve
Recorded Test Result
Accuracy: 1.00
ROC-AUC: 1.00

However, the test set used in the notebook contains only 10 samples, so these metrics should be considered experimental rather than representative of real-world model performance.

🐝 Particle Swarm Optimization
What is PSO?

Particle Swarm Optimization (PSO) is a population-based optimization algorithm inspired by the collective behavior of groups such as birds or fish.

In this project, PSO is used to search for bus allocation strategies across different time slots and stops.


⚙️ PSO Configuration

The recorded implementation uses:

Number of particles: 30
Maximum iterations: 50

Inertia weight (w): 0.5
Cognitive coefficient (c1): 1.5
Social coefficient (c2): 1.5

Each particle represents a possible bus allocation solution.

The allocation is constrained between:

0 to 10 buses

per time-slot/stop combination.


💰 Fitness Function

The optimization uses a custom fitness function based on:

1. Unmet Passenger Demand

A penalty is applied when the available bus capacity is lower than passenger demand.

Unmet Demand Penalty = unmet demand × 2
2. Unused Bus Capacity

A smaller penalty is applied when bus capacity exceeds passenger demand.

Unused Capacity Penalty = unused capacity × 0.5

The overall objective is to minimize the total scheduling cost.


📊 PSO Experiment

The notebook recorded the following result for the PSO experiment:

Baseline Cost: 1000.0
PSO Cost:      1375.0

The corresponding PSO allocation was:

[[1 1 2 2 2]
 [0 1 1 2 1]
 [1 1 2 1 3]
 [3 1 1 1 1]
 [1 1 2 1 2]
 [0 1 1 0 2]
 [1 0 2 2 0]
 [1 1 1 2 2]
 [1 2 1 2 2]
 [4 2 2 2 1]]
⚠️ Current Optimization Status

The recorded PSO experiment does not yet demonstrate an improvement over the baseline, because the recorded PSO cost is higher than the baseline cost.

Therefore, the current implementation should be considered a working optimization prototype that requires further tuning.

Future improvements should focus on:

Better initialization of particles
Improved PSO constraints
More suitable fitness formulation
More iterations
Multiple optimization runs
Comparison against stronger baseline strategies
📉 ML + Demand Analysis

The notebook also compares system scores using baseline allocation and different demand inputs.

One recorded experiment produced:

Original Score: 2838.5
Score with ML Predicted Demand: 30.0

This comparison is based on the simulated demand and the current notebook implementation and should not be interpreted as a real-world transportation improvement.


📊 Exploratory Data Analysis

The project includes several visualizations for understanding the simulated transportation data.

Visualizations include:
Passenger demand distribution
Passenger demand over time
Demand class distribution
Confusion matrix
ROC curve
Before/after cost comparison
Demand-related charts

These visualizations help understand demand patterns and evaluate the machine learning pipeline.


🖥️ Interactive Dashboard

The project includes an interactive Gradio dashboard.

The dashboard is designed to provide:

Transportation data generation
Demand analysis
Demand distribution visualization
Demand trend visualization
Demand class distribution
Classification report
Confusion matrix
ROC curve
Optimization-related visualization
Sample data table
Dashboard Inputs

Users can control:

Time Steps
Maximum Demand
Bus Capacity

The interface also displays:

Total Records
Average Demand
Model Accuracy
Optimization Gain

The dashboard is intended as an interactive prototype for exploring the overall system.

Note: Some dashboard outputs currently use placeholder/dummy calculations and are not connected to the complete trained ML + PSO pipeline. These components are planned for further integration.


🛠️ Technologies Used
Programming Language
Python
Data Analysis
NumPy
Pandas
Machine Learning
Scikit-learn
Random Forest Classifier
StandardScaler
GridSearchCV
Data Visualization
Matplotlib
Seaborn
Plotly
Optimization
Particle Swarm Optimization (PSO)
Interactive Dashboard
Gradio
Streamlit
Development Environment
Jupyter Notebook
VS Code
📁 Project Structure
PSO-for-public-transport-Scheduling-Optimization-in-Simulation-Dataset/
│
├── PSO_Public_Transport_Scheduling.ipynb
├── README.md
├── requirements.txt
├── .gitignore
└── ultimate_transport_dataset.csv

The dataset is generated programmatically by the notebook and does not need to be manually created before running the project.


🚀 How to Run
1. Clone the Repository
git clone https://github.com/adidev282006-sketch/PSO-for-public-transport-Scheduling-Optimization-in-Simulation-Dataset.git
2. Open the Project Folder
cd PSO-for-public-transport-Scheduling-Optimization-in-Simulation-Dataset
3. Install Dependencies
pip install -r requirements.txt
4. Open the Notebook

Open:

PSO_Public_Transport_Scheduling.ipynb

using Jupyter Notebook, JupyterLab, Google Colab, or VS Code.

5. Run the Notebook

Run the cells sequentially to:

Generate the simulated dataset.
Perform data analysis.
Train the Random Forest model.
Perform hyperparameter tuning.
Evaluate the classification model.
Generate predicted demand.
Run PSO-based bus allocation.
View optimization results.
Launch the interactive dashboard.


📦 Requirements

Main Python libraries used in the project include:

numpy
pandas
matplotlib
seaborn
scikit-learn
gradio
streamlit
plotly

Install them using:

pip install -r requirements.txt
🔬 Key Concepts Demonstrated

This project demonstrates practical experience with:

Data generation
Large-scale simulated datasets
Data preprocessing
Exploratory Data Analysis
Feature scaling
Machine learning classification
Random Forest
Hyperparameter tuning
GridSearchCV
Classification metrics
ROC-AUC
Confusion Matrix
Particle Swarm Optimization
Custom fitness functions
Bus allocation
Transportation scheduling
Interactive dashboards
Data visualization


🚧 Future Improvements

The following improvements can make the system more realistic and production-ready:

Machine Learning
Use a larger and more representative test set.
Perform cross-validation with a more realistic evaluation strategy.
Improve demand prediction using real transportation datasets.
Compare Random Forest with other machine learning algorithms.
PSO Optimization
Improve particle initialization.
Add realistic bus capacity constraints.
Add route and timetable constraints.
Add maximum/minimum bus constraints.
Track PSO convergence across iterations.
Run multiple PSO trials for more reliable results.
Compare PSO against stronger baseline algorithms.
Optimize the fitness function.
Dashboard
Connect the dashboard directly to the trained ML model.
Connect the dashboard directly to the PSO optimizer.
Remove placeholder metrics.
Add real-time optimization results.
Add interactive route and bus allocation visualizations.
Deployment
Deploy the Gradio application.
Create a dedicated web application.
Add API support for model predictions.
Deploy the system using a cloud platform.


💡 Project Highlights
Generated a 500,000-record simulated transportation dataset.
Implemented Random Forest classification for passenger demand.
Applied GridSearchCV for hyperparameter tuning.
Implemented a custom Particle Swarm Optimization algorithm.
Designed a fitness function based on unmet demand and unused capacity.
Built an interactive Gradio dashboard.
Integrated machine learning, optimization, and visualization into a single project.


👨‍💻 Author
Aditya Dev

GitHub:
https://github.com/adidev282006-sketch

⭐ Acknowledgement

This project was developed as an educational and experimental implementation of machine learning and optimization techniques for public transportation scheduling.
