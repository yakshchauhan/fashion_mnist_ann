# Fashion-MNIST ANN — V1 & V2

This is a Fashion-MNIST image classification project I made using PyTorch. I built the model in two versions. V1 is a basic ANN, and in V2 I tried to improve it using regularization and hyperparameter tuning.

> I used an ANN for this project. A CNN would probably perform better on Fashion-MNIST because it can use the spatial information in images.

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
| Batch Normalization | No | Yes |
| Dropout | No | 0.4 |
| Weight Decay | No | 0.000030786 |
| Optuna | No | Yes |
| Test Accuracy | 88.49% | 89.45% |

V2 improved the accuracy from 88.49% to 89.45%, which is about a 0.96 percentage point improvement.

## Dataset

I used the Fashion-MNIST dataset.

- Training samples: 60,000
- Test samples: 10,000
- Image size: 28 × 28
- Input features: 784
- Number of classes: 10
- Pixel values were normalized by dividing them by `255.0`

Dataset: https://www.kaggle.com/datasets/zalando-research/fashionmnist

The CSV files are not included in this repository.

## V1 — Basic ANN

For the first version, I started with a simple fully connected neural network.

It uses:

- Linear layers
- ReLU activation
- Cross Entropy Loss
- SGD optimizer
- Learning rate: `0.01`
- Batch size: `32`
- 200 epochs

The model reached 88.49% test accuracy.

While training the model, I noticed that it was starting to overfit, so I used the second version to experiment with some regularization techniques.

## V2 — Improving the Model

For V2, I added:

- Batch Normalization
- Dropout
- Weight Decay
- Adam, SGD and RMSprop optimizers
- Different learning rates
- Different batch sizes
- Different numbers of hidden layers
- Different numbers of neurons

I used Optuna to try different combinations of these hyperparameters and find a better configuration.

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

## Overfitting

The main reason I made V2 was to try to reduce the overfitting I saw in V1.

I used Dropout, Batch Normalization and Weight Decay for this.

I also compared training and test/validation performance to see how well the model was generalizing.

## Training Process

```
Fashion-MNIST
      ↓
Normalize Images
      ↓
PyTorch Dataset
      ↓
DataLoader
      ↓
ANN
      ↓
Forward Pass
      ↓
Cross Entropy Loss
      ↓
Backpropagation
      ↓
Optimizer
      ↓
Evaluation
```

For V2, Optuna was added to the process to search for better hyperparameters.

## What I Learned

Through this project I got more familiar with:

- Building neural networks using PyTorch
- Creating custom Dataset and DataLoader
- Training models on a GPU
- Forward and backward propagation
- Batch Normalization
- Dropout
- Weight Decay
- Different optimizers
- Hyperparameter tuning with Optuna
- Evaluating model performance
- Understanding overfitting

## Reproducibility

- Random seed: `100`
- Input features: `784`
- Pixel scaling: `/255.0`
- Training samples: `60,000`
- Test samples: `10,000`

The exact results can vary depending on the random seed, PyTorch version, hardware and training setup.

## Tech Used

- Python
- PyTorch
- Optuna
- Pandas
- NumPy
- Matplotlib

## Future Work

Some things I want to try next:

- Build a CNN and compare it with this ANN
- Use a separate validation set for Optuna instead of the test set
- Plot training and validation accuracy/loss
- Add a confusion matrix
- Check accuracy for each class
- Try learning-rate schedulers
- Compare the ANN and CNN results
