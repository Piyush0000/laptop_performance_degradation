🚀 Laptop Performance Degradation Predictor
A machine learning project that predicts how much a laptop's performance will degrade over time based on its specifications and usage patterns.

https://img.shields.io/badge/Python-3.7%252B-blue
https://img.shields.io/badge/Scikit--learn-1.0%252B-orange
https://img.shields.io/badge/License-MIT-green

📖 Overview
This project uses various machine learning algorithms to predict laptop performance degradation percentage based on hardware specifications and usage habits. Perfect for understanding how different factors affect laptop longevity!

🎯 What Problem Does This Solve?
🔍 Predict how much a laptop will slow down over time

💡 Understand which factors most impact performance degradation

📊 Compare different machine learning algorithms

🎓 Learn practical data science and ML implementation

📊 Dataset Features
Feature	Description	Type
RAM_GB	Amount of RAM in gigabytes	Numerical
Storage_SSD	Whether storage is SSD (1) or HDD (0)	Binary
CPU_GHz	Processor speed in gigahertz	Numerical
Daily_Usage_hr	Average daily usage in hours	Numerical
Background_Apps	Number of background applications	Numerical
Degradation_Percent	Performance degradation percentage	Target
🛠️ Installation & Setup
Prerequisites
Python 3.7+

pip (Python package manager)

Quick Start
bash
# Clone the repository
git clone https://github.com/yourusername/laptop-performance-predictor.git
cd laptop-performance-predictor

# Install required packages
pip install -r requirements.txt

# Run the Jupyter notebook
jupyter notebook laptop_performance_analysis.ipynb
Requirements
Create a requirements.txt file with:

text
pandas>=1.3.0
numpy>=1.21.0
scikit-learn>=1.0.0
matplotlib>=3.5.0
seaborn>=0.11.0
jupyter>=1.0.0
joblib>=1.1.0
🚀 Quick Usage
Basic Prediction
python
from sklearn.ensemble import RandomForestRegressor
import joblib

# Load the trained model
model = joblib.load('best_laptop_predictor.pkl')

# Predict degradation for a new laptop
laptop_specs = [[16, 1, 2.5, 8, 10]]  # [RAM, SSD, CPU, Usage, Background Apps]
prediction = model.predict(laptop_specs)[0]
print(f"Predicted degradation: {prediction:.1f}%")
Example Predictions
Laptop Profile	Specs	Predicted Degradation
Gaming Laptop	16GB RAM, SSD, 3.5GHz, 4hrs/day, 5 apps	~25%
Work Laptop	8GB RAM, SSD, 2.5GHz, 8hrs/day, 15 apps	~35%
Budget Laptop	4GB RAM, HDD, 1.8GHz, 10hrs/day, 20 apps	~40%
📈 Model Performance
We compared multiple algorithms:

Model	Mean Absolute Error	R² Score
Random Forest 🏆	2.15	0.89
Gradient Boosting	2.23	0.87
Linear Regression	3.45	0.76
Decision Tree	2.98	0.81
K-Neighbors	3.12	0.79
🔍 Key Insights
Most Important Features
Daily Usage Hours ⏰ - Biggest impact on degradation

Background Applications 📱 - Significant performance drain

RAM Size 💾 - More RAM = slower degradation

Storage Type 💽 - SSD laptops degrade slower

CPU Speed ⚡ - Moderate impact

Interesting Findings
📊 SSD vs HDD: SSD laptops show 15-20% less degradation

⏳ Usage patterns: 8+ hours daily usage accelerates degradation

🎮 Background apps: Each additional app increases degradation by ~0.5%
