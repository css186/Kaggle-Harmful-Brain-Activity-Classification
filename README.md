# Competition Link
https://www.kaggle.com/competitions/hms-harmful-brain-activity-classification

# Timeline
Feb. 2024 – Apr. 2024

# Introduction
* Electroencephalogram (EEG) is a common tool for diagnosing seizures in a clinical setting
* EEG interpretation is a labor-intensive and time-consuming work that currently relies solely on manual analysis of neurologists. 
* Such manual analysis can be prone to fatigue-related errors, and may encounter reliability issues among different EEG reviewers.
* Goal: to build deep learning models for classification of seizure-related activities

# Dataset
* The datasets used in our project were provided by Kaggle: Harvard Medical School - Harmful Brain Activity Classification, as shown in the link below: 
https://www.kaggle.com/competitions/hms-harmful-brain-activity-classification/data

* The datasets consist of 17,300 raw EEG data and 11,138 Spectrogram data


# Methodology
* Data preprocessing of EEG includes **extracting 8 channels** from the given data, **converting raw EEG signals into montaged EEG signals**, standardization, down-sampling, and **applying low-pass filters**

* Data preprocessing of spectrogram data includes extracting the labeled segment of data with offset seconds provided by Kaggle. Both EEG and spectrogram data into a **(24, 128, 256) tensor** were combined, and reshaped into different shapes as inputs.

* Loss function used in this project is **Kullback-Leibler divergence (The closer to 0 the better)**

* Convolutional neural network models, ResNet, LSTM models were used to take in pre-processed EEG data and outputs a prediction probability for each of the six labels, including seizures, LPD, LRDA, GPD, GRDA, and others

* Hyperparameter tuning, utilizing multiple kernels, and combining prediction outputs of multiple models were explored

* The Spectrogram-based models attempted included DenseNet, ResNet, and EfficientNet, and EfficientNet-based model has the best performance

* The EEG-based model that performed best is the combination of 1D CNN and ResNet, trained with 15 epochs without the use of multiple kernels. This model achieved a loss of 0.51

# Result

* A hybrid model consists of 2 different size combination of EfficientNet-based model and EEG-based model **achieved a loss of 0.38**






