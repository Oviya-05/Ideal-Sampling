# Ideal-Sampling
## Aim:

  The aim of this experiment is to understand and demonstrate the concept of ideal sampling in signal processing, highlighting its characteristics and practical applications.

## Tools required:
  
  * Colab (for executing Python code)
  * Libraries: NumPy, Matplotlib

## Program:
~~~
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
  plt.plot(t, signal, label='Continuous Signal', alpha=0.7)
  plt.stem(t_sampled, signal_sampled, linefmt='r-', markerfmt='ro', basefmt='r-', label='Sampled Signal (fs = 100 Hz)')
  plt.title('Sampling of Continuous Signal (fs = 100 Hz)')
  plt.xlabel('Time [s]')
  plt.ylabel('Amplitude')
  plt.grid(True)
  plt.legend()
  plt.show()
  reconstructed_signal = resample(signal_sampled, len(t))
  plt.figure(figsize=(10, 4))
  plt.plot(t, signal, label='Continuous Signal', alpha=0.7)
  plt.plot(t, reconstructed_signal, 'r--', label='Reconstructed Signal (fs = 100 Hz)')
  plt.title('Reconstruction of Sampled Signal (fs = 100 Hz)')
  plt.xlabel('Time [s]')
  plt.ylabel('Amplitude')
  plt.grid(True)
  plt.legend()
  plt.show()
~~~

## Output Waveform:

![image](https://github.com/user-attachments/assets/0674414f-553d-46c4-9ffb-d9d9d79ff29a)

## Results:

  The results of the experiment will include two plots:
  
    * Original Signal Plot:  Displays the continuous sinusoidal waveform.
    
    * Ideal Sampled Signal Plot: Shows discrete points representing the sampled values from the original signal.
    
  These plots will illustrate how ideal sampling captures specific points of the original waveform, effectively demonstrating the concept of ideal sampling in signal processing.
