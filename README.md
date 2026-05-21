# EXP 1 A : COMPUTATION OF DFT USING DIRECT AND FFT

## AIM: 
 To Obtain DFT and FFT of a given sequence in SCILAB. 

## APPARATUS REQUIRED: 
PC installed with SCILAB. 

## PROGRAM: 
### DFT-direct method:
```
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
### OUTPUT: 

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/949e6e52-2f99-43be-a61e-221656a97a88" />



<img width="500" height="500" alt="Screenshot 2026-05-21 152049" src="https://github.com/user-attachments/assets/a1e70bed-7f32-4a0b-afbc-e6d7dea9cf00" />

### DFT-FFT method:

```
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

### Output:
<img width="482" height="206" alt="image" src="https://github.com/user-attachments/assets/60da464f-14d9-4977-a1e9-97f23d68a973" />



<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/25a658a3-c949-4cdf-9452-0873118e690a" />

# RESULT: 
Thus, the Discrete Fourier Transform using Direct and Fast Fourier Transform of the given sequence were obtained and its magnitude and phase spectrum were plotted.
