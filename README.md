# IS_Lab3_Fuzzy-Logic-Control
# Fuzzy Pet Feeder Control System

## Overview

This repository contains the implementation of a Fuzzy Logic-based control system for a pet feeder. The system takes into account the pet's hunger level, the amount of food consumed beforehand, and the food dispenser motor speed to determine the optimal motor speed for the food dispenser.

## Fuzzy Logic Variables

### Pet's Hunger Level (H)
- Linguistic Variables: Starving, Hungry, Satiated, Overfed
- Universe of Discourse: 0 - 100
- Membership Functions: Starving, Hungry, Satiated, Overfed

### Amount of Food Consumed (F)
- Linguistic Variables: Low, Medium, High
- Universe of Discourse: 0 - 500
- Membership Functions: Low, Medium, High

### Food Dispenser Motor Speed (MS)
- Linguistic Variables: Slow, Moderate, Fast
- Universe of Discourse: 0 - 300
- Membership Functions: Slow, Moderate, Fast

## Rule Base

The rule base defines the relationships between the input variables and the output motor speed.

| Rule | Pet's Hunger Level | Amount of Food Consumed | Food Dispenser Motor Speed |
|------|--------------------|-------------------------|----------------------------|
| 1    | Starving            | Low                     | Fast                       |
| 2    | Starving            | Medium                  | Fast                       |
| 3    | Starving            | High                    | Fast                       |
| 4    | Hungry              | Low                     | Moderate                   |
| 5    | Hungry              | Medium                  | Moderate                   |
| 6    | Hungry              | High                    | Slow                       |
| 7    | Satiated            | Low                     | Moderate                   |
| 8    | Satiated            | Medium                  | Slow                       |
| 9    | Satiated            | High                    | Slow                       |
| 10   | Overfed             | Low                     | Slow                       |
| 11   | Overfed             | Medium                  | Slow                       |
| 12   | Overfed             | High                    | Slow                       |

## Rule Evaluation

The rules are applied to the input values (Pet's Hunger Level, Amount of Food Consumed) to determine the Food Dispenser Motor Speed. The center of gravity (COG) is calculated as the weighted average of the motor speeds.

## Example Usage

To use the Fuzzy Pet Feeder Control System, provide the values for the pet's hunger level and the amount of food consumed beforehand in the `values` dictionary. The system will output the recommended Food Dispenser Motor Speed.

```python
# Example Usage
values = { H: 10, F: 400 }
output = fuzzy_control_system(values)
print(f"Recommended Food Dispenser Motor Speed: {output}")
```

Feel free to experiment with different input values to observe how the system adjusts the motor speed recommendation.
