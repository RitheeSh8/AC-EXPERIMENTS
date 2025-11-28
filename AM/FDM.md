# SIMULATION OF FREQUENCY DIVISION MULTIPLEXING (FDM) AND DEMULTIPLEXING USING SCILAB

## AIM
To write a Scilab program to simulate frequency division multiplexing and demultiplexing for six different frequencies, and verify the demultiplexed outputs correspond to the original signals

## ALGORITHM
1.Define six different frequencies to generate six sine wave signals.
2.Generate the time vector to represent time samples.
3.Compute six sine signals for each frequency over the time vector.
4.Frequency Division Multiplexing: sum all six sine signals to make one multiplexed signal.
5.Frequency Division Demultiplexing: for each frequency, multiply the multiplexed signal by a sine wave of that frequency (mixing), then apply a lowpass filter to extract the baseband (original) signal.
6.Plot original signals, multiplexed signal, and demultiplexed signals for verification.

## PROGRAM
```
fs = 80000;
t = 0:1/fs:0.035;

m1 = 2.6*sin(2*%pi*564*t);
m2 = 2.7*sin(2*%pi*574*t);
m3 = 2.8*sin(2*%pi*584*t);
m4 = 2.9*sin(2*%pi*594*t);
m5 = 3.0*sin(2*%pi*604*t);
m6 = 3.1*sin(2*%pi*614*t);

fc = [6000 7500 9000 10500 12000 13500];

c1 = cos(2*%pi*fc(1)*t);
c2 = cos(2*%pi*fc(2)*t);
c3 = cos(2*%pi*fc(3)*t);
c4 = cos(2*%pi*fc(4)*t);
c5 = cos(2*%pi*fc(5)*t);
c6 = cos(2*%pi*fc(6)*t);

s1 = m1 .* c1;
s2 = m2 .* c2;
s3 = m3 .* c3;
s4 = m4 .* c4;
s5 = m5 .* c5;
s6 = m6 .* c6;

s = s1 + s2 + s3 + s4 + s5 + s6;

d1 = 2 * s .* c1;
d2 = 2 * s .* c2;
d3 = 2 * s .* c3;
d4 = 2 * s .* c4;
d5 = 2 * s .* c5;
d6 = 2 * s .* c6;

cutoff = 800;

function y = fft_lowpass(x, cutoff, fs)
    N = length(x);
    X = fft(x);
    f = (0:N-1)*(fs/N);
    mask = (f <= cutoff) | (f >= fs - cutoff);
    Y = X .* mask;
    y = real(ifft(Y));
endfunction

r1 = fft_lowpass(d1, cutoff, fs);
r2 = fft_lowpass(d2, cutoff, fs);
r3 = fft_lowpass(d3, cutoff, fs);
r4 = fft_lowpass(d4, cutoff, fs);
r5 = fft_lowpass(d5, cutoff, fs);
r6 = fft_lowpass(d6, cutoff, fs);

scf(1);
clf;

subplot(6,3,1);  plot(t, m1);
subplot(6,3,4);  plot(t, m2);
subplot(6,3,7);  plot(t, m3);
subplot(6,3,10); plot(t, m4);
subplot(6,3,13); plot(t, m5);
subplot(6,3,16); plot(t, m6);

subplot(6,3,8);  plot(t, s);

subplot(6,3,3);  plot(t, r1);
subplot(6,3,6);  plot(t, r2);
subplot(6,3,9);  plot(t, r3);
subplot(6,3,12); plot(t, r4);
subplot(6,3,15); plot(t, r5);
subplot(6,3,18); plot(t, r6);

```
## OUTPUT

<img width="2560" height="1368" alt="image" src="https://github.com/user-attachments/assets/404518be-390a-4c74-9d57-e5bdec84d31f" />

## TABULATION
![IMG-20251128-WA0011 1](https://github.com/user-attachments/assets/1f298da1-aac7-4c47-92e2-5a046a3f9c33)

![IMG-20251128-WA0012 1](https://github.com/user-attachments/assets/7134a8d5-3d96-4d64-85db-8161fe6b37f2)

## RESULTS
The program successfully simulates FDM and demultiplexing for multiple frequency signals with filtering to recover original signals accurately in Scilab.
