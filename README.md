# Traffic Congestion Prediction Using Bayesian Network - Exact Inference
This project provides a Bayesian Network model implemented in Python to predict traffic congestion based on factors like weather, time of day, traffic light state, and accident occurrence. Using the pgmpy library, this notebook demonstrates constructing the network, defining conditional probability distributions (CPDs), and performing exact inference to predict traffic conditions.
Model Description
The Bayesian Network model in this project is designed to predict the likelihood of traffic congestion. The network considers the following nodes:

Weather: Indicates if the weather is clear or rainy.
TimeOfDay: Differentiates between off-peak and peak hours.
Accident: Represents the occurrence of an accident.
TrafficLightState: Influenced by time of day, indicating the traffic light conditions.
TrafficCongestion: The primary variable of interest, representing the traffic congestion status.
Model Structure
The network relationships:

Weather, TimeOfDay, Accident, and TrafficLightState all influence TrafficCongestion.
TrafficLightState is influenced by TimeOfDay.
CPDs (Conditional Probability Distributions)
Each variable has a CPD defining its probabilities:

Weather: Probability of clear or rainy.
TimeOfDay: Probability of off-peak or peak.
Accident: Probability of accident or no accident.
TrafficLightState: Based on TimeOfDay.
TrafficCongestion: Based on Weather, TimeOfDay, Accident, and TrafficLightState.
Running the Notebook
Download or clone the repository.
Open the exact__inference.ipynb notebook in Jupyter Notebook or JupyterLab.
Run each cell in sequence to define the model, set up CPDs, and perform inference.
Example Usage
Here’s an example of performing inference to determine traffic congestion:

python
Copy code
# Evidence: Weather is rainy, TimeOfDay is peak, Accident has occurred
result = inference.query(variables=['TrafficCongestion'], evidence={'Weather': 1, 'TimeOfDay': 1, 'Accident': 1})
print(result)
The output may look like this:

plaintext
Copy code
+----------------------+----------------+
| TrafficCongestion    |   phi(TrafficCongestion) |
+======================+================+
| TrafficCongestion(0) |        0.35    |
+----------------------+----------------+
| TrafficCongestion(1) |        0.65    |
+----------------------+----------------+
This result indicates a 65% chance of traffic congestion under rainy weather, peak hours, and accident conditions.

Dependencies
pgmpy: For constructing and running inference on the Bayesian Network.
Install via:

bash
Copy code
pip install pgmpy
