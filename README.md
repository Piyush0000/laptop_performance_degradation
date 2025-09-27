# Laptop Performance Degradation Predictor

A machine learning project that predicts how much a laptop's performance will degrade over time based on its specifications and usage patterns.

## Overview

This project uses various machine learning algorithms to predict laptop performance degradation percentage based on hardware specifications and usage habits.

### What it does:
- Predicts how much a laptop will slow down over time
- Identifies which factors most impact performance degradation
- Compares different machine learning algorithms

## Dataset Features

- **RAM_GB**: Amount of RAM in gigabytes
- **Storage_SSD**: Whether storage is SSD (1) or HDD (0)
- **CPU_GHz**: Processor speed in gigahertz
- **Daily_Usage_hr**: Average daily usage in hours
- **Background_Apps**: Number of background applications
- **Degradation_Percent**: Performance degradation percentage (target)

## Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/laptop-performance-predictor.git
cd laptop-performance-predictor
```

2. Install dependencies:
```bash
pip install pandas numpy scikit-learn matplotlib seaborn jupyter joblib
```

3. Run the notebook:
```bash
jupyter notebook laptop_performance_analysis.ipynb
```

## Usage

```python
from sklearn.ensemble import RandomForestRegressor
import joblib

# Load the trained model
model = joblib.load('best_laptop_predictor.pkl')

# Predict degradation for a new laptop
laptop_specs = [[16, 1, 2.5, 8, 10]]  # [RAM, SSD, CPU, Usage, Background Apps]
prediction = model.predict(laptop_specs)[0]
print(f"Predicted degradation: {prediction:.1f}%")
```

## Model Performance

| Model | Mean Absolute Error | R² Score |
|-------|-------------------|----------|
| Random Forest | 2.15 | 0.89 |
| Gradient Boosting | 2.23 | 0.87 |
| Linear Regression | 3.45 | 0.76 |
| Decision Tree | 2.98 | 0.81 |

## Key Findings

**Most Important Features:**
1. Daily Usage Hours - Biggest impact on degradation
2. Background Applications - Significant performance drain
3. RAM Size - More RAM = slower degradation
4. Storage Type - SSD laptops degrade slower
5. CPU Speed - Moderate impact

**Insights:**
- SSD laptops show 15-20% less degradation than HDD
- 8+ hours daily usage accelerates degradation
- Each additional background app increases degradation by ~0.5%

## Example Predictions

- **Gaming Laptop** (16GB RAM, SSD, 3.5GHz, 4hrs/day, 5 apps): ~25% degradation
- **Work Laptop** (8GB RAM, SSD, 2.5GHz, 8hrs/day, 15 apps): ~35% degradation
- **Budget Laptop** (4GB RAM, HDD, 1.8GHz, 10hrs/day, 20 apps): ~40% degradation

## License

MIT License
