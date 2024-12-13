# MNIST Classification Model Evolution

This repository contains a series of PyTorch implementations showing the evolution of a CNN model for MNIST digit classification.

## Model Progression

### Model  1 
#### Target:
- Create a Basic skeleton of the model
- Set Basic Working Code
- Simple architecture with Conv2d layers followed by MaxPooling
- Set Basic Training  & Test Loop
- Set parameters to be less than 8000
- Set Epochs to 15
#### Result:
- Parameters: 7,704
- Best Train Accuracy: 98.72
- Best Test Accuracy: 98.40
#### Analysis:
- The model is working with some over-fitting.

### Model  2 
#### Target:
- Added BatchNormalization after each convolution layer to increase model efficiency
#### Result:
- Parameters: 7,848
- Best Train Accuracy: 99.62
- Best Test Accuracy: 99.10
#### Analysis:
- We have started to see over-fitting a bit more now. 
- Even if the model is pushed further, it won't be able to get to 99.4% Test Accuracy.

### Model 3 
#### Target:
- Introduced Dropout (0.08) for regularization
#### Result:
- Parameters: 7,848
- Best Train Accuracy: 99.03
- Best Test Accuracy: 99.12
#### Analysis:
- The model is not over-fitting at all now.

### Model 4 
#### Target:
- Changed architecture to use Global Average Pooling (GAP) and removed the BIG kernel at the end.
#### Result:
- Parameters: 3,964
- Best Train Accuracy: 97.99
- Best Test Accuracy: 98.70
#### Analysis:
- Reduced model parameters.
- The model is under-fitting which is a good thing.
- Since we have reduced model capacity, a reduction in performance is expected. 

### Model 5 
#### Target:
- Increased Paramter count and added more layers
#### Result:
- Parameters: 6,264
- Best Train Accuracy: 98.86
- Best Test Accuracy: 99.37 (15th Epoch)
#### Analysis:
- The model is still under-fitting which is a good thing.
- Best Test Accuracy reached but still short by 0.03% from desired result.

### Model 6 - Final Version
#### Target:
- Added image augmentation (Random Rotation -5° to +5°)
#### Result:
- Parameters: 6,264
- Best Train Accuracy: 98.84
- Best Test Accuracy: 99.18
#### Analysis:
- The model is under-fitting.
- Test Accuracy is reduced a bit from last model.

## Architecture Details
- Input: 28x28 MNIST images
- Output: 10 classes (digits 0-9)
- Loss Function: Negative Log Likelihood (NLL)
- Optimizer: SGD with momentum (0.9)
- Learning Rate: 0.015
- Batch Size: 128

## Training
- Epochs: 15
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
