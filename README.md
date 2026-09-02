# Fashion-MNIST ANN — V1 & V2

A Fashion-MNIST image classification project built with **PyTorch**, developed in two versions to improve an Artificial Neural Network (ANN) through regularization and hyperparameter optimization.

> **Note:** This project uses an ANN for image classification. A CNN can generally make better use of spatial features in images and may achieve better results on Fashion-MNIST.

## Results

| | V1 | V2 |
|---|---:|---:|
| Model | Basic ANN | Optimized ANN |
| Hidden Layers | — | 2 |
| Neurons/Layer | — | 88 |
| Optimizer | SGD | Adam |
| Learning Rate | 0.01 | 0.00059448 |
| Batch Size | 32 | 256 |
| Epochs | 200 | 50 |
| Batch Normalization | ❌ | ✅ |
| Dropout | ❌ | 0.4 |
| Weight Decay | ❌ | 0.000030786 |
| Optuna | ❌ | ✅ |
| Test Accuracy | **88.49%** | **89.45%** |

V2 improved the test accuracy by **0.96 percentage points** compared with V1 while using fewer epochs.

## Dataset

**Fashion-MNIST:** https://www.kaggle.com/datasets/zalando-research/fashionmnist

- Training samples: **60,000**
- Test samples: **10,000**
- Image size: **28 × 28**
- Input features: **784**
- Classes: **10**
- Pixel values normalized using `/255.0`

The CSV files are not included in this repository.

## V1 — Basic ANN

V1 uses a simple fully connected neural network with:

- Linear layers
- ReLU activation
- Cross Entropy Loss
- SGD optimizer
- Learning rate: `0.01`
- Batch size: `32`
- Epochs: `200`

V1 showed signs of **overfitting**, motivating the improvements introduced in V2.

## V2 — Hyperparameter-Optimized ANN

V2 adds:

- Batch Normalization
- Dropout
- Weight decay
- Adam, SGD and RMSprop
- Learning-rate search
- Batch-size search
- Epoch search
- Hidden-layer search
- Neuron search
- **Optuna hyperparameter optimization**

### Best V2 Configuration

```text
Hidden Layers:     2
Neurons/Layer:     88
Epochs:            50
Learning Rate:     0.00059448
Dropout:           0.4
Batch Size:        256
Optimizer:         Adam
Weight Decay:      0.000030786
Test Accuracy:     89.45%
