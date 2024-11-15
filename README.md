# Selfie to Anime Style Image Translation with CycleGAN

This project implements an image translation model using CycleGAN to convert selfie images into anime-style representations. The CycleGAN framework is trained to learn mappings between two distinct image domains without requiring paired datasets.

## Project Overview

This project is a part of the CS 315 AI course, where we applied Generative Adversarial Networks (GANs), specifically CycleGAN, for unpaired image-to-image translation tasks. Our model transforms input images of human faces (selfies) into a stylized anime representation by learning from two unpaired datasets: selfie images and anime-style images.

## Model Architecture

The CycleGAN architecture includes:
- **Generator**: The generator learns to translate images from one domain to another. It uses multiple convolutional layers, residual blocks, and up-sampling layers to generate stylized images.
- **Discriminator**: The discriminator assesses whether an input image is real or generated by the model. It includes several convolutional layers with leaky ReLU activations for binary classification.
- **Cycle Consistency Loss**: This loss ensures that an image translated from domain X to Y and back to X is similar to the original image.

## Project Structure

The code includes the following key components:

1. **Discriminator**: Evaluates whether images are real or generated.
2. **Generator**: Transforms images between domains (selfie to anime and vice versa).
3. **ResidualBlock**: Adds skip connections to capture features more effectively.
4. **CycleGAN Class**: Integrates all components, with functions for training the generator and discriminator, computing cycle consistency loss, and managing optimizers.

## Dataset

Two unpaired datasets were used:
- **X_DATASET**: Domain A (Selfie images)
- **Y_DATASET**: Domain B (Anime-style images)


## Training

To train the model, we set up DataLoader objects for both domains, instantiated CycleGAN, and defined optimizers. The training loop alternates between training the generator and discriminator while saving the model with the best generator loss.

### Training Parameters

- **Learning Rate (LR)**: 0.0002
- **Epochs**: 100
- **Batch Size**: 32
- **Betas (β1, β2)**: [0.5, 0.999]
