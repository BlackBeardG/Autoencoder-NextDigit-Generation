# Experimental Evaluation of Generative Autoencoder Architectures for Next-Digit Transformation on MNIST

George Ioannidis, undergraduate student, ECE AUTH

## Overview

This project focuses on generative image transformation using Autoencoder Neural Networks. The task is based on the MNIST dataset, where the model receives an image of a handwritten digit **N** as input and is trained to generate an image of the next digit **N+1**.

The goal is to evaluate different Autoencoder architectures and training techniques in order to identify the model that produces the most recognizable generated digits.

## Methods

The project evaluates several MLP Autoencoder architectures with different depths, widths and latent-space configurations.

The experiments include:

* shallow and deep Autoencoder architectures
* different bottleneck and latent-space sizes
* gradual dimensionality reduction
* Binary Cross Entropy and Mean Squared Error loss functions
* thresholding of generated images
* weight decay regularization
* different learning rates
* learning-rate schedulers
* comparison with PCA

A CNN classifier is used as a judge to evaluate whether the generated images can be correctly recognized as digits.

## Results

The best-performing Autoencoder uses an encoder architecture of **784 → 1024 → 512 → 128** with a symmetric decoder. The model applies dropout, weight decay, thresholding and the ReduceLROnPlateau scheduler.

The generated images are evaluated through a CNN classifier trained on MNIST.

The best model achieved **98.01% test accuracy** according to the CNN judge, showing that the generated next-digit images are highly recognizable.

## Files

* `Autoencoders.ipynb`: implementation and experiments
* `Project_Report.pdf`: project report
