# -Frequency-Modulation-and-Demodulation-using-NumPy-and-Matplotlib-

## Aim:

To implement and analyze frequency modulation (FM) using Python's NumPy and Matplotlib libraries.

## Apparatus Required:

1. Software: Python with NumPy and Matplotlib libraries
   
2. Hardware: Personal Computer

 
## Theory:

Frequency Modulation (FM) is a method of transmitting information over a carrier wave by varying its 
frequency in accordance with the amplitude of the input signal (message signal). The frequency of the carrier 
wave is varied according to the instantaneous amplitude of the message signal.

## Algorithm:

1. Initialize Parameters: Set the values for carrier frequency, message frequency, sampling frequency, and 
   frequency deviation.
   
2. Generate Time Axis: Create a time vector for the signal duration.
    
3. Generate Message Signal: Define the message signal as a cosine wave.
    
4. Compute the Integral of the Message Signal: Calculate the integral of the message signal over time.
    
5. Generate FM Signal: Apply the FM modulation formula to obtain the modulated signal.
 
6. Plot the Signals: Use Matplotlib to plot the message signal, carrier signal, and modulated signal.

## Program:
```
import numpy as np
import matplotlib.pyplot as plt

Am = 11.5       
fm = 540     
Ac = 23       
fc = 5400     
fs = 54000     
t = np.arange(0, 3/fm, 1/fs)
m = Am * np.cos(2 * 3.14 * fm * t)
plt.subplot(3,1,1)
plt.plot(t, m)
plt.title("Message Signal")
plt.xlabel("Time")
plt.ylabel("Amplitude")
c = Ac * np.cos(2 * 3.14 * fc * t)
plt.subplot(3,1,2)
plt.plot(t, c)
plt.title("Carrier Signal")
plt.xlabel("Time")
plt.ylabel("Amplitude")
df = 2000       
beta = df / fm
print("Modulation Index (β) =", beta)
s = Ac * np.cos(2 * 3.14 * fc * t + beta * np.sin(2 * 3.14 * fm * t))
plt.subplot(3,1,3)
plt.plot(t, s)
plt.title("Frequency Modulated Signal")
plt.xlabel("Time")
plt.ylabel("Amplitude")
plt.tight_layout()
plt.show()
```
## Output:
<img width="630" height="469" alt="image" src="https://github.com/user-attachments/assets/619e1929-815d-4b24-b32d-76850473a57f" />

## Tabulation:
![WhatsApp Image 2025-11-23 at 15 55 41_6c648a1b](https://github.com/user-attachments/assets/2d0ee236-c113-4ce8-b4f3-f87719bbdb0b)

## Result:
The FM experiment shows that the frequency of the carrier varies according to the message signal while the amplitude remains constant. The waveform clearly displays frequency deviations based on the input message. The spectrum shows multiple sidebands, confirming successful FM. This experiment helps understand noise-resistant modulation techniques.
