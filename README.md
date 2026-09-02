# Fashion MNIST ANN — V1

A simple Artificial Neural Network built with **PyTorch** to classify Fashion-MNIST images.

## Results

- Training samples: **60,000**
- Test samples: **10,000**
- Test Accuracy: **88.49%**
- Test Accuracy: **98%**
- Epochs: **200**

> The reported accuracy is based on the exact 60,000/10,000 train-test split used in this project. Using a different dataset version, split, preprocessing, or labels may produce different results.

## Dataset

The dataset used for this project can be found here:

**Dataset:** https://www.kaggle.com/datasets/zalando-research/fashionmnist

The dataset contains:

- `fashion_train.csv` — 60,000 training samples
- `fashion_test.csv` — 10,000 test samples
- `label` — target class
- 784 pixel features per image

The CSV files are **not included in this repository**.

## Model

- ReLU activation
- Cross Entropy Loss
- SGD optimizer
- Learning rate: `0.01`
- Batch size: `32`
- Epochs: `200`

## Reproducibility

- Random seed: `100`
- Training samples: `60,000`
- Test samples: `10,000`
- Input features: `784`
- Pixel scaling: `/255.0`

Results may vary if the dataset, preprocessing, or training configuration is changed.

## Tech Stack

- Python
- PyTorch
- Pandas
- Matplotlib
