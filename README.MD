# MNIST Classification Model Evolution

This repository contains a series of PyTorch implementations showing the evolution of a CNN model for MNIST digit classification.

## Model Progression

### Version 1 (F1)
- Basic CNN architecture
- No regularization
- Simple architecture with Conv2d layers followed by MaxPooling
- Final layer using 7x7 kernel to get to 1x1x10 output

### Version 2 (F2)
- Added BatchNormalization after each convolution layer
- Improved model stability and training speed
- Same basic architecture as F1

### Version 3 (F3)
- Introduced Dropout (0.1) for regularization
- BatchNorm + Dropout combination
- Better generalization compared to F2

### Version 4 (F4)
- Changed architecture to use Global Average Pooling (GAP)
- Reduced model parameters
- More modern architectural choice compared to large kernel at end

### Version 5 (F5)
- Modified channel sizes
- Optimized architecture with 16->8 channel transition
- Better parameter efficiency

### Version 6 (F6) - Final Version
- Added image augmentation (Random Rotation -7° to +7°)
- Best performing model with regularization and augmentation
- Most robust against overfitting

## Architecture Details
- Input: 28x28 MNIST images
- Output: 10 classes (digits 0-9)
- Loss Function: Negative Log Likelihood (NLL)
- Optimizer: SGD with momentum (0.9)
- Learning Rate: 0.01
- Batch Size: 128

## Training
- Epochs: 14
- Train/Test Split: Standard MNIST split
- GPU Support: Yes (CUDA compatible)

## Requirements
- python
- torch
- torchvision
- numpy
- matplotlib
- tqdm

## Usage

## Usage
Each version can be run independently. For local execution:
1. Install dependencies
2. Adjust batch size and workers if needed
3. Run the desired version

## Results
Each version shows progressive improvement in:
- Model stability
- Training speed
- Test accuracy
- Generalization

## Hardware Requirements
- CPU: Any modern CPU (i5 or better recommended)
- GPU: CUDA compatible (tested on GTX 1660Ti)
- RAM: 8GB minimum
- VRAM: 4GB minimum