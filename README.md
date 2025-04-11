# erc_convener_q2
Contains solution to q2 of the convener assignment.

The goal of this study was to recover and clean an amplitude modulation (AM)-transmitted noisy audio signal. Reading the modulated audio file and transforming the signal data into a floating-point format for precise processing was the first step. In order to visualise the signal across time, I subsequently created a time vector based on the sample rate.

I used the Fast Fourier Transform (FFT) on the signal to get the carrier frequency, which is the frequency that was utilised to modulate the original audio. I was able to determine which frequencies were there and how powerful they were by converting the signal from the time domain into the frequency domain using this mathematical method.

I was able to determine the carrier frequency with a high degree of precision by identifying the peak in the magnitude spectrum (concentrating solely on the positive half because the FFT is symmetric).

After estimating the carrier frequency, I isolated the frequency range containing the valuable modulated information and reduced wideband noise by using a bandpass filter centred on this frequency. I used the Hilbert Transform after filtering to get the signal's analytic form. I was able to recover the original message signal that had been embedded by extracting the envelope, which is a representation of the amplitude variations in the carrier wave.

Since there was still some noise in the envelope, I created and used a second bandpass filter that was especially tuned to the 950–1200 Hz frequency region that was thought to contain the original audio information. This made the restored signal considerably clearer by suppressing any undesirable frequencies that could still be there.

I exported the cleaned audio as a new file called clean_audio.wav after normalising it to the proper range for WAV format storage. Additionally, I created a number of charts, including one that contrasted the filtered and noisy versions of the recovered audio, another that visualised the demodulated signal over time, and one that displayed the frequency spectrum that was used to identify the carrier. These illustrations showed the efficiency of the filtering and demodulation process and assisted in validating each stage.

Attained plots are given below:


![Filtered_vs_Noisy](https://github.com/user-attachments/assets/61890441-974a-47e0-b360-ed5cb9682b1a)



![FFT_spectrum](https://github.com/user-attachments/assets/b6d2ddc3-1b2a-4c4e-98f7-81c2daaf8611)



![Demodulated_signal](https://github.com/user-attachments/assets/e481e4cd-34cc-4922-8abb-597703f99ee2)
