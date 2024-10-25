# Traffic Congestion Prediction Using Bayesian Network - Exact Inference
This project demonstrates the use of Bayesian Networks to predict traffic congestion based on multiple factors such as weather conditions, time of day, traffic light state, and the occurrence of accidents. The model leverages the pgmpy library to construct the network, define conditional probability distributions (CPDs), and perform exact inference to deduce the likelihood of traffic congestion.

# Introduction
Traffic congestion prediction is a critical component of modern traffic management systems, enabling cities to optimize traffic flow and improve road safety. This Bayesian Network model provides a probabilistic approach to predict traffic congestion by analyzing various factors and their interdependencies.

The notebook exact__inference.ipynb contains the complete code for building the model and performing exact inference on traffic congestion.

# Installation
## Prerequisites
Python 3.7 or higher
Jupyter Notebook or JupyterLab

# Install Dependencies
To set up the required Python packages, run:
```bash
pip install pgmpy
```

# Project Overview
This project defines a Bayesian Network with nodes representing different factors influencing traffic congestion and uses exact inference to analyze these influences. This can be useful in real-time traffic management scenarios or as a part of a larger traffic analysis system.

# Model Details
The Bayesian Network model consists of the following variables:

1.Weather: Indicates if the weather is clear or rainy.  

2.TimeOfDay: Differentiates between off-peak and peak hours.  

3.Accident: Represents the occurrence of an accident.  

4.TrafficLightState: Indicates traffic light state, influenced by the time of day.  

5.TrafficCongestion: The target variable, representing the traffic congestion status.

## Model Structure
The network’s relationships:

Weather, TimeOfDay, Accident, and TrafficLightState influence TrafficCongestion.  

TrafficLightState is influenced by TimeOfDay.

## CPDs (Conditional Probability Distributions)
Each variable is assigned a probability distribution:

Weather: Probability of clear or rainy weather.  

TimeOfDay: Probability of off-peak or peak time.  

Accident: Probability of accident occurrence.  

TrafficLightState: Probability of traffic light state depending on TimeOfDay.  

TrafficCongestion: Probability of traffic congestion based on Weather, TimeOfDay, Accident, and TrafficLightState.

The network allows for exact inference on TrafficCongestion given certain evidence, enabling us to estimate traffic congestion probability under specific conditions.

# Dependencies
This project requires the pgmpy library. Install it via:
```python
pip install pgmpy
```
