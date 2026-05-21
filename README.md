## EXP 1  : COMPUTATION OF DFT USING DIRECT AND FFT ALGORITHM

### AIM: 

 To Obtain DFT using Direct and FFT of a given sequence in SCILAB. 

### APPARATUS REQUIRED: 
PC installed with SCILAB. 

### PROGRAM: 
 ##### DISCRETE FOURIER TRANSFORM USING DIRECT METHOD
 ```python
clc;
clear;

N = input("Length of the sequence N: ");
x = input("Input sequence x(n): ");

if length(x) <> N then
    error("Length of x(n) must be equal to N");
end

X_direct = zeros(1, N);

for k = 0:N-1
    sum_val = 0;
    for n = 0:N-1
        sum_val = sum_val + x(n+1)*exp(-%i*2*%pi*k*n/N);
    end
    X_direct(k+1) = sum_val;
end

X_direct = clean(X_direct);

disp("DFT using Direct Method:");
disp(X_direct);

mag = abs(X_direct);
phase = atan(imag(X_direct), real(X_direct));

disp("Magnitude Spectrum:");
disp(mag);

disp("Phase Spectrum (radians):");
disp(phase);

k = 0:N-1;
clf;

subplot(2,1,1);
plot2d3(k, mag);
title("Magnitude Spectrum of DFT");
xlabel("k");
ylabel("|X(k)|");

subplot(2,1,2);
plot2d3(k, phase);
title("Phase Spectrum of DFT");
xlabel("k");
ylabel("∠X(k) (rad)");
```
##### DISCRETE FOURIER TRANSFORM USING FFT ALGORITHM

```python
clc;
clear;

N = input("Length of the sequence N: ");
x = input("Enter input sequence x(n): ");
if length(x) <> N then
    error("Length of x(n) must be equal to N");
end

X_fft = fft(x);

disp("DFT using FFT:");
disp(X_fft);

mag = abs(X_fft);
phase = atan(imag(X_fft), real(X_fft));

disp("Magnitude Spectrum:");
disp(mag);

disp("Phase Spectrum (radians):");
disp(phase);

k = 0:N-1;
clf;

subplot(3,1,1);
plot2d3(0:N-1, x);
title("Input Sequence x(n)");
xlabel("n");
ylabel("Amplitude");

subplot(3,1,2);
plot2d3(k, mag);
title("Magnitude Spectrum");
xlabel("k");
ylabel("|X(k)|");

subplot(3,1,3);
plot2d3(k, phase);
title("Phase Spectrum");
xlabel("k");
ylabel("∠X(k) (rad)");
```

### OUTPUT: 
 ##### DISCRETE FOURIER TRANSFORM USING DIRECT METHOD
 <img width="2880" height="1696" alt="DFT1" src="https://github.com/user-attachments/assets/89e58196-4988-447a-8c16-3e0a6a2e85fc" />
 <img width="914" height="502" alt="DFT2" src="https://github.com/user-attachments/assets/6b7d465c-e0a2-4291-8beb-0b2e2d264e43" />


##### DISCRETE FOURIER TRANSFORM USING FFT ALGORITHM
<img width="2865" height="1458" alt="DFT FFT1" src="https://github.com/user-attachments/assets/e792c0ad-13ef-42ce-b82c-479dbdb99827" />
<img width="1063" height="461" alt="DFT FFT2" src="https://github.com/user-attachments/assets/28d78879-45d6-4ca6-b252-a8cd94674771" />


### RESULT: 
Thus, the Discrete Fourier Transform using Direct and Fast Fourier Transform of the given sequence were obtained and its magnitude and phase spectrum were plotted.
