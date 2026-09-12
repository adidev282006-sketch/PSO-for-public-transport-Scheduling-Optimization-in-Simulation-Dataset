# 🚍 PSO-Based Public Transport Scheduling Optimization

An intelligent public transport scheduling system that combines **Machine Learning** and **Particle Swarm Optimization (PSO)** to analyze passenger demand and explore optimized bus allocation strategies using simulated transportation data.

---

## 📌 Project Overview

This project demonstrates a data-driven approach to public transport scheduling.

A simulated transportation dataset is generated using Python and analyzed using machine learning techniques. A **Random Forest Classifier** is trained to classify passenger demand into different demand levels. The predicted demand is then used as an input to a **Particle Swarm Optimization (PSO)** algorithm for bus allocation.

The project also includes an interactive **Gradio dashboard** for exploring transportation data, model metrics, visualizations, and optimization-related outputs.

---

## 🎯 Objectives

- Generate and analyze simulated public transport data.
- Classify passenger demand into different demand levels.
- Apply machine learning for demand prediction.
- Use Particle Swarm Optimization for bus allocation.
- Analyze transportation scheduling costs.
- Visualize passenger demand and model performance.
- Provide an interactive dashboard for system exploration.

---

## 🧠 Methodology

The project follows the following workflow:

```text
Simulated Transport Data
          ↓
Data Preprocessing
          ↓
Exploratory Data Analysis
          ↓
Demand Classification
          ↓
Random Forest Model
          ↓
GridSearchCV Hyperparameter Tuning
          ↓
Predicted Passenger Demand
          ↓
Particle Swarm Optimization
          ↓
Bus Allocation Analysis
          ↓
Interactive Dashboard
