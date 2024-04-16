# A machine learning based controller to set and regulate non-visual lighting metrics of a tunable lighting system using visual light parameters
A regression based controller to set and regulate non-visual lighting metrics of a tunable lighting system using visual light parameters. This project aims to develop a regression model to establish a relationship between selected visual metrics and the MDER and MEDI, simultaneously of a Phillips Hue Lighting system. This relationship will then be used to achieve MDER and MEDI values by altering the color temperature and brightness settings of the Philips Hue lighting system.

## lighting_control_model.ipynb
### Defining The Model
A simple regression model constructed using the Pytorch framework
- Input: The model takes in two features: color temperature and brightness.
- Hidden Layers: It has two layers, each with 400 neurons. These layers help the model learn complex patterns using a function called ReLU, making the model more effective. The 400 neurons in each layer allow the model to learn detailed relationships effectively without being too complex. This setup helps the model capture important patterns while keeping it manageable. This function helps the model learn faster and more efficiently by solving some common problems in training neural networks.
- Output: It outputs two values, one for MDER and one for MEDI.

## metrics.csv
The dataset provided consists of measurements recorded from a Philips Hue Lighting system. It contains 9,587 entries and captures various lighting metrics along with color temperature settings and their resulting visual impacts taken at different times of dat in a simulated living room. 

Dataset Structure:
The dataset consists of the following columns:
- date: The date on which the measurement was taken (format: DD/MM/YYYY).
- time: The time at which the measurement was recorded (format: HH:MM:SS).
- bri: Brightness setting of the Philips Hue light (integer).
- ct: Color temperature setting on the Philips Hue scale (integer).
- cct_in: Input correlated color temperature (integer, in Kelvin).
- cct: Calculated correlated color temperature (float, in Kelvin).
- lcone_lux: Lux level perceived by the L-cones in the human eye (float).
- mcone_lux: Lux level perceived by the M-cones in the human eye (float).
- mlux: Melanopic lux level (float).
- plux: Photopic lux level (float).
- scone_lux: Lux level perceived by the S-cones in the human eye (float).

## model.pt
The trained weights of the previous model
