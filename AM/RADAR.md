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

## ALGORITHM
1.Initialize constants: λ (wavelength) = 0.03 m σ (radar cross section) = 1 m²
2.Vary each parameter while keeping the others constant: Pt: 0.1 → 10 Gt: 1 → 50 Pm: 1e⁻¹⁵ → 1e⁻¹⁰
3.Compute maximum range using: R_max = ((Pt * Gt² * λ² * σ) / ((4π)³ * Pm))¼
4.Plot the following: Pt vs Rmax Gt vs Rmax Pm vs Rmax

## PROGRAM
```
G=40;
eta=0.5;
Ae=1;
Smin=1e-10;
Ppeak=5000:50:9000;
Rmax_values = zeros(1, length(Ppeak));
for i = 1:length(Ppeak)
    Rmax_values(i) = ((Ppeak(i) * G * eta * Ae) / (16 * %pi^2 * Smin))^(1/4);
end
clf;
subplot(3,1,1);
plot(Ppeak, Rmax_values, 'b');
xlabel('P_{peak}');
ylabel('R_{max}');
clear "G" "Rmax_values" "Ppeak";
Ppeak = 5000;
G = 50:2:100;
Rmax_values = zeros(1, length(G));
for i = 1:length(G)
    Rmax_values(i) = ((Ppeak * G(i) * eta * Ae) / (16 * %pi^2 * Smin))^(1/4);
end
subplot(3,1,2);
plot(G, Rmax_values, 'r');
xlabel("G");
ylabel("R_{max}");
clear "G" "Rmax_values" "Smin";
G = 40;
Smin_values = logspace(-12,-9,50);
Rmax_values = zeros(1, length(Smin_values));
for i = 1:length(Smin_values)
    Rmax_values(i) = ((Ppeak * G * eta * Ae) / (16 * %pi^2 * Smin_values(i)))^(1/4);
end
subplot(3,1,3);
plot(Smin_values, Rmax_values, 'g');
xlabel("S_{min}");
ylabel("R_{max}");
```
## OUTPUT WAVEFORM

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/f3435f99-a4af-472b-947d-f6bac357a051" />

## CALCULATION

![IMG-20251126-WA0026 1](https://github.com/user-attachments/assets/8068b06f-c183-48c9-9b31-7f1053da24f0)

## RESULT
Thus, the maximum range of a radar system using the Radar Range Equation is verified
