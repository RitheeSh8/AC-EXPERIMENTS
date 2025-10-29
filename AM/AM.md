#     Amplitude Modulation Using Python

## Aim:
  To implement and analyze amplitude modulation (AM) using Python's NumPy and Matplotlib libraries. 

## Apparatus Required
   Software: Python with NumPy and Matplotlib libraries
   Hardware: Personal Computer
## Theory
Amplitude Modulation (AM) is a technique used in electronic communication, primarily for transmitting information via a radio carrier wave. In AM, the amplitude of the carrier wave is varied in proportion to that of the message signal. The general form of an AM signal is:

<img width="460" height="332" alt="image" src="https://github.com/user-attachments/assets/6c8b9105-d2d3-4b99-999c-82e9f7808a7b" />

## Algorithm
1.	Initialize Parameters: Set the values for carrier frequency, message frequency, and sampling frequency.
2.	Generate Time Axis: Create a time vector for the signal duration.
3.	Generate Message Signal: Define the message signal as a cosine wave.
4.	Generate Carrier Signal: Define the carrier signal as a cosine wave.
5.	Modulate Signal: Apply the AM formula to obtain the modulated signal.
6.	Plot the Signals: Use Matplotlib to plot the message signal, carrier signal, and modulated signal.
## Program
```
import numpy as np
import matplotlib.pyplot as plt
Am = 3.1
Ac = 6.2
fm = 614
fc = 6140
fs = 61400
t = np.arange(0, 3/fm, 1/fs)
m = Am * np.cos(2 * np.pi * fm * t)
c = Ac * np.cos(2 * np.pi * fc * t)
s = (Ac + m) * np.cos(2 * np.pi * fc * t)
plt.figure(figsize=(10, 6))
plt.subplot(3,1,1)
plt.plot(t, m)
plt.grid()
plt.subplot(3,1,2)
plt.plot(t, c)
plt.grid()
plt.subplot(3,1,3)
plt.plot(t, s)
plt.grid()
plt.tight_layout()
plt.show()
```
## Output

<img width="986" height="590" alt="image" src="https://github.com/user-attachments/assets/ad25b174-b70c-4250-835c-cb4d2b4ab62e" />

## Tabulation



## Result
The message signal, carrier signal, and amplitude modulated (AM) signal will be displayed in separate plots. Thus AM is implemented using numPy and Matplotlib.
