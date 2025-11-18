# DSBSC USING PYTHON 
## AIM
To implement and analyze Double Sideband Suppressed Carrier (DSB-SC) modulation using Python’s NumPy and Matplotlib libraries.
## APPARATUS REQUIRED
Software: Python with NumPy and Matplotlib libraries Hardware: Personal Computer
## THEORY
Double Sideband Suppressed Carrier (DSB-SC) is a type of amplitude modulation where the carrier signal is suppressed, and only the sidebands (which contain the information) are transmitted.

<img width="1031" height="643" alt="image" src="https://github.com/user-attachments/assets/4624395d-7cb3-4bbb-9040-16c901af2437" />

## ALGORITHM

<img width="1005" height="524" alt="image" src="https://github.com/user-attachments/assets/c1983e35-9327-4e6a-be0f-f65dd95ba704" />

PROGRAM
```
import numpy as np
import matplotlib.pyplot as plt
Am = 5.3
Ac = 10.6
fm = 199
fc = 1990
fs = 19900
t = np.arange(0, 2/fm, 1/fs)
m = Am * np.cos(2 * np.pi * fm * t)
c = Ac * np.cos(2 * np.pi * fc * t)
s1 = (Ac + m) * np.cos(2 * np.pi * fc * t)
s2 = (Ac - m) * np.cos(2 * np.pi * fc * t)
s = s1 - s2
plt.figure(figsize=(10, 6))
plt.subplot(3,1,1)
plt.plot(t, m)
plt.xlabel("Time")
plt.ylabel("Amplitude")
plt.grid()
plt.subplot(3,1,2)
plt.plot(t, c)
plt.xlabel("Time")
plt.ylabel("Amplitude")
plt.grid()
plt.subplot(3,1,3)
plt.plot(t, s)
plt.xlabel("Time")
plt.ylabel("Amplitude")
plt.grid()
plt.tight_layout()
plt.show()
```
## OUTPUT WAVEFORM

<img width="989" height="590" alt="image" src="https://github.com/user-attachments/assets/52af412a-6515-4a80-b5b5-2e4d646575c9" />

## TABULATION

![IMG-20251118-WA0006 1](https://github.com/user-attachments/assets/7a0e5ec7-6af8-4651-bde6-44d17fe9c28d)

## RESULT
Thus, Double Sideband Suppressed Carrier (DSB-SC) modulation was successfully implemented using Python’s NumPy and Matplotlib libraries, and the message, carrier, and modulated waveforms were plotted and analyzed.
