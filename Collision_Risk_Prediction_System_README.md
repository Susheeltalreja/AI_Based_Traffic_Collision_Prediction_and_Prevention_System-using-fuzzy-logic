# Collision Risk Prediction System

## Overview
This project implements a fuzzy logic-based system to evaluate collision risk based on various factors such as traffic density, weather conditions, road conditions, road types, and accident history. The system uses fuzzy membership functions to calculate degrees of risk and suggests control actions accordingly.

## Features
- **Traffic Density Analysis**: Classifies traffic density into Low, Medium, and High categories.
- **Weather Condition Evaluation**: Categorizes weather into Good, Fair, and Bad conditions.
- **Road Conditions**: Evaluates the condition of roads (Wet, Dry, Icy) and their associated risk.
- **Road Types**: Assesses risk based on road type (Highway, City Street, Residential).
- **Accident History**: Incorporates past accident data to influence risk assessment.
- **Fuzzy Logic**: Utilizes membership functions and rules to determine risk levels.
- **Control Actions**: Provides actionable recommendations based on calculated collision risk.

## Membership Functions
### Traffic Density
- **Low Traffic**: Membership peaks at 0 and diminishes to 0 by density 5.
- **Medium Traffic**: Membership peaks at density 5 and tapers off between densities 3 and 7.
- **High Traffic**: Membership increases from density 5 to 10 and remains high beyond.

### Weather Conditions
- **Good Weather**: Peaks at 35°C, suitable range between 28°C and 35°C.
- **Fair Weather**: Suitable between 26°C and 35°C.
- **Bad Weather**: Peaks at extreme temperatures (≤10°C or ≥35°C).

### Road Conditions and Types
- Wet, Dry, and Icy roads are evaluated with varying risk levels.
- Road types include Highway, City Street, and Residential, each with specific risk profiles.

## How It Works
1. **Input Parameters**:
   - Traffic Density
   - Weather Condition
   - Road Condition (Wet, Dry, Icy)
   - Road Type (Highway, City Street, Residential)
   - Accident History (Low, Medium, High)

2. **Fuzzy Inference**:
   - Membership functions calculate degrees of relevance for each parameter.
   - Rules combine the degrees to determine overall collision risk.

3. **Output**:
   - Provides collision risk level: Low, Moderate, or High.
   - Suggests control actions such as "Safe to proceed," "Maintain speed," or "Increase caution."

## Visualization
The system includes visualizations for:
- Traffic density membership functions.
- Weather condition membership functions.

To visualize, call `plot_membership_functions()` in the script.

## Example Usage
```python
traffic_conditions = [
    (10, 45, 3, 3, 1),  # (density, weather, road_condition, road_type, accident_history)
    (7, 25, 2, 2, 2),
    (3, 30, 2, 1, 3)
]

actions = []
for density, weather, road_condition, road_type, accident_history in traffic_conditions:
    action = control_action(density, weather, road_condition, road_type, accident_history)
    actions.append((density, weather, road_condition, road_type, accident_history, action))
    print(action)
```

## Installation
1. Clone the repository.
```bash
git clone <repository_url>
```
2. Install required libraries.
```bash
pip install numpy matplotlib
```

## License
This project is licensed under the MIT License.

---
For further information, feel free to contribute or raise issues!
