# SMILES-to-Spectra and Spectra-to-SMILES Predictions with INNs & MLPs

This repository contains models and evaluation notebooks for learning a bidirectional mapping between SMILES (molecular structures) and molecular spectra using two approaches:

- A **multilayer perceptron** (MLP)
- An **invertible neural network** (INN)

This project uses the `smiles2spec` repository (https://github.com/JeremCab/smiles2spec), which predicts spectra from SMILES using deep learning.

All the files imported in the notebooks can be found in [this shared Google Drive folder]([url](https://drive.google.com/drive/folders/1jfgh5M7cyb9I0chqy6_LN1s1OAEzg9-e?usp=drive_link)) as well.

## Notebooks

- `cddd_INN.ipynb`: Code for the INN model.
- `Neural_Network.ipyn`: Code for the MLP model.
- `Prediction_Stats_INN.ipynb`: Evaluates INN model predictions on a larger test set (15% of the full SMILES dataset).
- `Prediction_Stats_CNN.ipynb`: Evaluates INN model predictions on a larger test set (15% of the full SMILES dataset).

## Datasets

The full dataset contains ~85,000 SMILES–spectra pairs. A 15% holdout test set was used to evaluate model performance.

The SMILES strings were encoded into continuous dense vectors using the [CDDD (Continuous Data-Driven Descriptors)](https://github.com/jrwnter/cddd) model. CDDD is an autoencoder trained on molecular structures that allows conversion between SMILES strings and their latent embeddings. These embeddings were used as inputs for both the forward (SMILES → spectra) and inverse (spectra → SMILES) models in this project.

The decoded SMILES predictions for the test dataset are located here:

- [`predicted_with_spectra_INN.csv`](https://drive.google.com/file/d/1eozwLjU6tF4VK-9Jje7Tp59rlahjR_5L/view?usp=drive_link)
