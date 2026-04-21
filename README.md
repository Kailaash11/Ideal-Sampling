# Ideal, Natural, & Flat-top -Sampling
# Aim
  To write a simple Python program for the construction and reconstruction of ideal, natural, and flattop sampling.
# Tools required
  PC with i3 processor
  
  Google colab
  
# Program
```
import numpy as np
import matplotlib.pyplot as plt
fm = 5                   
fs = 50                    
t = np.linspace(0, 1, 1000)   # Continuous time axis
ts = np.arange(0, 1, 1/fs)    # Sampled time axis
x = np.sin(2 * np.pi * fm * t)
xs = np.sin(2 * np.pi * fm * ts)
pulse_width = 0.01
natural = np.zeros_like(t)

for i in range(len(ts)):
    idx = np.where((t >= ts[i]) & (t < ts[i] + pulse_width))
    natural[idx] = x[idx]
flat_top = np.zeros_like(t)

for i in range(len(ts)-1):
    idx = np.where((t >= ts[i]) & (t < ts[i+1]))
    flat_top[idx] = xs[i]
plt.figure(figsize=(12, 8))
plt.subplot(4,1,1)
plt.plot(t, x)
plt.title("Original Analog Signal")
plt.xlabel("Time (s)")
plt.ylabel("Amplitude")
plt.grid()
plt.subplot(4,1,2)
plt.stem(ts, xs, basefmt=" ")
plt.title("Ideal Sampling")
plt.xlabel("Time (s)")
plt.ylabel("Amplitude")
plt.grid()
plt.subplot(4,1,3)
plt.plot(t, natural)
plt.title("Natural Sampling")
plt.xlabel("Time (s)")
plt.ylabel("Amplitude")
plt.grid()
plt.subplot(4,1,4)
plt.plot(t, flat_top)
plt.title("Flat-top Sampling")
plt.xlabel("Time (s)")
plt.ylabel("Amplitude")
plt.grid()
plt.tight_layout()
plt.show()

```
# Output Waveform
<img width="1020" height="672" alt="WhatsApp Image 2026-04-21 at 9 06 18 AM" src="https://github.com/user-attachments/assets/fb52b894-0ce7-4de3-9991-85c94f66f6e1" />

# Results
 A simple Python program for the construction and reconstruction of ideal, natural, and flattop sampling issuccessfully generated 
