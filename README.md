# Ideal, Natural, & Flat-top -Sampling
# Aim
Write a simple Python program for the construction and reconstruction of ideal, natural, and flattop sampling.
# Tools required
colab python
# Program
# IDEAL SAMPLING #
import numpy as np
import matplotlib.pyplot as plt
from scipy.signal import resample
fs = 100
t = np.arange(0, 1, 1/fs) 
f = 5
signal = np.sin(2 * np.pi * f * t)
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal')
plt.title('Continuous Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()
t_sampled = np.arange(0, 1, 1/fs)
signal_sampled = np.sin(2 * np.pi * f * t_sampled)
plt.figure(figsize=(10, 4))
#plt.plot(t, signal, label='Continuous Signal', alpha=0.7)
plt.stem(t_sampled, signal_sampled, linefmt='r-', markerfmt='ro', basefmt='r-', label='Sampled Signal (fs = 100 Hz)')
plt.title('Sampling of Continuous Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()
reconstructed_signal = resample(signal_sampled, len(t))
plt.figure(figsize=(10, 4))
#plt.plot(t, signal, label='Continuous Signal', alpha=0.7)
plt.plot(t, reconstructed_signal, 'r--', label='Reconstructed Signal (fs = 100 Hz)')
plt.title('Reconstruction of Sampled Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()
# Output Waveform
IDEAL SAMPLING
<img width="866" height="393" alt="image" src="https://github.com/user-attachments/assets/f6794cf9-93c7-45e9-ac78-e8dafb885d87" />
<img width="866" height="393" alt="image" src="https://github.com/user-attachments/assets/d372749c-4ef1-42d6-9426-9899a240746d" />
<img width="866" height="393" alt="image" src="https://github.com/user-attachments/assets/4935090f-bf92-4963-82d5-9cb381749e18" />

NATURAL SAMPLING
<img width="1390" height="989" alt="image" src="https://github.com/user-attachments/assets/81334784-f750-4725-919b-e0cf198a3da5" />

FLAT-TOP SAMPLING
<img width="1398" height="990" alt="image" src="https://github.com/user-attachments/assets/d2849b7b-2831-4e84-8964-6348975d6c8c" />

# Results
Thus the construction and reconstruction of Ideal, Natural and Flat-top sampling were successfully implemented using Python and the corresponding waveforms were obtained.
