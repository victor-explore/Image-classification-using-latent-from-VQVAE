# Image Classification using VQVAE Latent Space

This repository demonstrates an innovative approach to image classification by leveraging the latent space representations learned through a Vector Quantized Variational Autoencoder (VQ-VAE).

## Overview

The project consists of two main components:
1. A VQ-VAE model that learns compressed latent representations of images
2. A classifier that operates on these latent representations instead of raw images

## Key Features

- **Latent Space Classification**: Instead of classifying raw images directly, we first encode them into a compressed latent space using VQ-VAE and perform classification on these latent representations
- **Dimensionality Reduction**: The VQ-VAE significantly reduces the dimensionality of the input while preserving important features
- **Improved Efficiency**: Classification in the compressed latent space requires fewer computational resources
- **Robust Feature Learning**: The VQ-VAE learns meaningful discrete representations that can improve classification accuracy

## Classification Architecture

The classification pipeline follows these steps:

1. Images are first passed through the trained VQ-VAE encoder
2. The encoder produces discrete latent codes
3. These latent codes are used as input to a neural network classifier
4. The classifier outputs class predictions

## Training Process

The training process shows consistent improvement in classification accuracy across epochs, with the loss decreasing from ~0.5 to ~0.37 over 25+ epochs. Key metrics from training:

- Starting loss: ~0.50
- Final loss: ~0.37
- Batch size: Configured for 146 batches per epoch
- Regular reconstruction image checkpoints saved for monitoring

## Results

The model demonstrates strong classification performance while benefiting from:
- Reduced input dimensionality
- Discrete latent representations
- Efficient processing of compressed data

## Usage

To use this model:

1. Train the VQ-VAE on your image dataset
2. Extract latent representations using the trained encoder
3. Train the classifier on these latent representations
4. Use the pipeline for inference on new images

## Requirements

- PyTorch
- Python 3.x
- Standard deep learning libraries (exact requirements in requirements.txt)

## Future Improvements

- Experiment with different VQ-VAE architectures
- Try various classifier architectures
- Optimize the codebook size
- Implement data augmentation in latent space
