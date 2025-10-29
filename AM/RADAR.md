# EVALUATION OF RADAR RANGE USING SCILAB

## AIM
To calculate the maximum range of a radar system using the Radar Range Equation and verify the results through scilab

## THEORY
The Radar Range Equation is a fundamental formula used in radar system design to determine the maximum range at which a radar can detect a target. It is given by:

<img width="457" height="528" alt="image" src="https://github.com/user-attachments/assets/85da0f10-05b8-496a-aaf5-a6969692f9de" />

## PROCEDURE
Open Scilab.
Create a new script file (.sce) and enter the given program code.
Define all constants — speed of light, wavelength, radar cross-section, and system loss.
Define the range vector R from 1 km to 100 km.
Assign transmitted power Pt and antenna gain G as nonlinear (quadratic) functions of R.
Compute received power Pr using the Radar Range Equation.
Convert Pr to dBm for better visualization.
Plot:
Pt vs R (curved increasing relation)
G vs R (curved increasing relation)
Pr vs R (curved decreasing relation)
Execute the program to display the three subplots.

