## EXPT.NO.6 SIMULATION OF AUTOCORRELATION AND PSD USING SCILAB AIM

# AIM 
  To Write a program for Autocorrelation and PSD of signals in SCILAB and verify Wiener-Khinchin relation.

# APPARATUS REQUIRED 
Computer with i3 Processor
wiht SCI LAB

# THEORY
The Wiener-Khinchin theorem states that the power spectral density of a wide sense stationary random process is the Fourier transform of the corresponding autocorrelation function

# ALGORITHM
1.Load or Define the Signal: Input your time-domain signal.

2.Compute Autocorrelation: Calculate the autocorrelation function of the signal.

3.Compute Power Spectral Density (PSD): Estimate the PSD of the signal, either directly using a method like Welch’s periodogram or by using the Fourier transform of the autocorrelation.

4.Plot Results: Visualize the autocorrelation function and PSD.

# PROCEDURE
1.Refer Algorithms and write code for the experiment.

2.Open SCILAB in System

3.Type your code in New Editor

4.Save the file

5.Execute the code

6.If any Error, correct it in code and execute again

7.Verify the generated waveform using Tabulation and Model Waveform

# PROGRAM
```
t=0:0.01:2*3.14;
x=sin(7*t)+cos(8*t);
subplot(3,2,1);
plot(x);
au=xcorr(x);
subplot(3,2,2);
plot(au);
v=fft(au);
subplot(3,2,3);
plot(abs(v));
fw=fft(x);
subplot(3,2,4);
plot(fw);
fw2=(abs(fw))^2;
subplot(3,2,5);
plot(fw2);
```

# OUTPUT

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c2860fe0-6af1-46cf-982f-6e211cb47e82" />

# RESULT 

Thus the Autocorrelation and PSD are executed in Scilab and output is verified.
