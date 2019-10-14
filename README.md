# Voice Activity Detection in Noisy Environments
Voice Activity Detection (VAD) using deep learning. Supervised by Retune DSP.

### Abstract
Automatic speech recognition (ASR) systems often require an always-on low-complexity Voice Activity Detection (VAD) module to identify voice before forwarding it for further processing in order to reduce power consumption. In most real-life scenarios recorded audio is noisy and deepneural networks have proven more robust to noise than the traditionally used statistical methods.

This study investigates the performance of three distinct low-complexity architectures – namely Long Short-Term Memory (LSTM) Recurrent Neural Networks (RNN), Gated Recurrent Unit (GRU) RNNs and an implementation of DenseNet. Furthermore, the impact of Focal Loss (FL) over the Cross-Entropy (CE) criterion during training is explored and findings are compared to recent VAD research.

Using a 72-hour dataset built from open sources with varied noise levels, 12 Mel-frequency Cepstral Coefficients (MFCC) as well as their derivatives in a temporal context of 900 ms, a GRU-RNN with 30.000 parameters achieves an Area Under Curve (AUC) of .991 and a False Acceptance Rate (FAR) of 3.61% given a False Rejection Rate (FRR) fixed at 1%. Focal Loss is found to improve performance slightly when using focusing parameter γ=2 and performance improvements are observed for all three architectures when their number of parameters is increased, which suggests that network size and performance can be viewed as a trade-off.

It is observed that in a high-noise environment, Convolutional Neural Networks (CNN) struggle  compared to pure RNNs where a 10.000 parameter LSTM-RNN achieves a FAR of 48.13% for fixed FRR at 1% compared to 58.14% for a DenseNet of comparable size.


### Results

All results shown here are for samples generated with a SNR (signal-to-noise ratio) of -3 dB, which -- for the unfamiliar reader -- is a substantial amount of noise.

ROC Curve

![ROC](https://i.imgur.com/Oukcxkw.png)

Example of a label

![Sample](https://i.imgur.com/6U51S2a.png)

Associated NN prediction

![Prediction](https://i.imgur.com/Jckot75.png)

### How to run?

You will need to download the two datasets used for our study as well as the notebook itself. Instructions on the datasets are given in the following section. The notebook will automatically install any missing dependencies using pip. You may need to alter the global parameters slightly before running -- see notebook for more details.


### Datasets

Our provided notebook can be run in two different modes: either you download and pre-process all data from scratch (takes roughly 16 hours on a personal computer) or you download and execute with already processed data (27 GB).

In any case, you will want to create a local directory that contain all necessary data and outputs. If you want to start from scratch, these are the two datasets that you need to collect: *LibriSpeech ASR corpus* and *QUT-NOISE*.
