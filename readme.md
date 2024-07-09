# Parkinsonian Cortical Basal Ganglia Network during Deep Brain Stimulation Model Code

## General Information

This repository contains python code for simulating a Hodgkin-Huxley based neural network model of the cortico-basal ganglia network with closed-loop deep brain stimulation to test closed-loop DBS control strategies.

<br/>

<br/>

![alt text](https://www.frontiersin.org/files/Articles/520710/fnins-14-00166-HTML/image_m/fnins-14-00166-g001.jpg)

<sup><sub>Fleming, J.E., Dunn, E. and Lowery, M.M., 2020. Simulation of closed-loop deep brain stimulation control schemes for suppression of pathological beta oscillations in Parkinson’s disease. Frontiers in neuroscience, 14, p.166. </sup></sub>

<br/>

## Citations
Fleming, J.E., Dunn, E. and Lowery, M.M., 2020. Simulation of closed-loop deep brain stimulation control schemes for suppression of pathological beta oscillations in Parkinson’s disease. Frontiers in neuroscience, 14, p.166.

The code contained in this repository for simulation of the motor network model and multivariable control DBS approaches is companion to the paper:  
> "Simulation of closed-loop deep brain stimulation control schemes for suppression of pathological beta oscillations in Parkinson’s disease"  
>   John E. Fleming, Eleanor Dunn, Madeleine M. Lowery
>    March 5, 2020 : 166  
>    DOI: 10.3389/fnins.2020.00166

which should be cited for academic use of this code.  
<br/>

## Model Requirements
The model is simulated using PyNN with NEURON as it's backend simulator, thus follow their installation instructions at: 

1) Neuron - https://www.neuron.yale.edu/neuron/download
   
2) PyNN - https://pypi.org/project/PyNN/ - http://neuralensemble.org/docs/PyNN/

<br/>

## Model Setup: 
1) Copy the included PyNN files from the downloaded model folder to their corresponding location on your computer (i.e. the directory of your PyNN instatllation - Updated PyNN files are needed for correct simulation of the multicompartmental cortical neurons and for loading model simulations from a presimulated steady state.

2) Compile the NEURON model mod files using either mknrndll or nrnivmodl, for windows or Linux, respectively.

3) Run run_CBG_MU_Pool_Model_to_SS.py

	Example:
	
 	1) From the command line/terminal navigate to the folder containing the model.
	
 	2) Execute "python run_CBG_Model_to_SS.py neuron"

    Explanation: There is an initial transient period in the model (~8 seconds). This model simulation runs the model for 
    the transienThere is an initial transient period in the model (~6 seconds). This model simulation runs the model for the transient
    period and creates a binary file (steady_state.bin) at the end of the simulation. This binary file captures the state of the model at
    the end of this transient simulation (i.e. after the model has reached the steady state)

Running the Model: - Once the steady state of the model has been saved you can run the model by navigating to the model directory in the command line and typing:

"python run_CBG_Model_Amplitude_Modulation_Controller.py neuron"

Output files of the simulation are then written to a "Simulation_Output_Results" folder when the simulation is finished.  Model outputs are structured using the neo file format as detailed in https://neo.readthedocs.io/en/stable/.
