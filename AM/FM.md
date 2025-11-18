# Frequency Modulation Using Python
## AIM
To implement and analyze frequency modulation (FM) using Python's NumPy and Matplotlib libraries.
## APPARATUS REQUIRED
Software: Python with NumPy and Matplotlib libraries
Hardware: Personal Computer
## THEORY
Frequency Modulation (FM) is a method of transmitting information over a carrier wave by varying its frequency in accordance with the amplitude of the input signal (message signal). The frequency of the carrier wave is varied according to the instantaneous amplitude of the message signal. The general form of an FM signal is:
## ALGORITHM
1.Initialize Parameters: Set the values for carrier frequency, message frequency, sampling frequency, and frequency deviation.
2.Generate Time Axis: Create a time vector for the signal duration.
3.Generate Message Signal: Define the message signal as a cosine wave.
4.Compute the Integral of the Message Signal: Calculate the integral of the message signal over time.
5.Generate FM Signal: Apply the FM modulation formula to obtain the modulated signal.
6.Plot the Signals: Use Matplotlib to plot the message signal, carrier signal, and modulated signal.
## PROGRAM
```
import numpy as np
import matplotlib.pyplot as plt

Am=5.1
Ac=10.2
fm=179
fc=1790
fs=17900
t=np.arange(0,3/fm,1/fs)
m=Am*np.cos(2*np.pi*fm*t)
c=Ac*np.cos(2*np.pi*fc*t)
b=4.5
eFM =Ac*np.cos(2 * np.pi * fc * t + b * np.sin(2 * np.pi * fm * t))
plt.subplot(3,1,1)
plt.plot(t,m)
plt.grid()
plt.subplot(3,1,2)
plt.plot(t,c)
plt.grid()
plt.subplot(3,1,3)
plt.plot(t,eFM)
plt.grid()

plt.tight_layout()
plt.show()
```
## OUTPUT WAVEFORM

<img width="766" height="581" alt="image" src="https://github.com/user-attachments/assets/ecc95e09-6d0a-4388-bd26-5b21c78294a5" />

## TABULAR COLOUMN



## CALCULATION



## RESULT
The message signal, carrier signal, and frequency modulated (FM) signal will be displayed in separate plots. The modulated signal will show frequency variations corresponding to the amplitude of the message signal.
