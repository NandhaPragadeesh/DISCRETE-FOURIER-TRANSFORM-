# EXP 1 A : COMPUTATION OF DFT USING DIRECT AND FFT

# AIM: 

# To Obtain DFT and FFT of a given sequence in SCILAB. 

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc;
clear;

x = input("Enter discrete signal as [x1 x2 ...]: ");
N = length(x);

X_dft = zeros(1, N);
for k = 0:N-1
    for n = 0:N-1
        X_dft(k+1) = X_dft(k+1) + x(n+1) * exp(-%i * 2 * %pi * k * n / N);
    end
end

f = (0:N-1) / N;

scf(0); 
subplot(2,1,1);
plot2d3(f, abs(X_dft));
xtitle("Magnitude Spectrum using Direct DFT");

subplot(2,1,2);
plot2d3(f, atan(imag(X_dft), real(X_dft))); 
xtitle("Phase Spectrum using Direct DFT");

X_fft = fft(x, -1);   

subplot(2,1,1);
plot2d3(f, abs(X_fft));
xtitle("Magnitude Spectrum using FFT");

subplot(2,1,2);
plot2d3(f, atan(imag(X_fft), real(X_fft))); 
xtitle("Phase Spectrum using FFT");
```

# OUTPUT: 

<img width="755" height="708" alt="Screenshot 2026-01-30 223025" src="https://github.com/user-attachments/assets/e99002b3-4dcf-46a1-b81c-bd50fa2f26a8" />

<img width="746" height="717" alt="Screenshot 2026-01-30 223034" src="https://github.com/user-attachments/assets/7849ac5c-1c9a-4bcb-a226-22834182ccba" />



# RESULT: 
Thus,The DFT and FFT of the given sequence is obtained using SCILAB.
