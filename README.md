# Fashion-MNIST ANN — V1

A simple Artificial Neural Network built with **PyTorch** to classify Fashion-MNIST images.

## Results

- Training samples: **60,000**
- Test samples: **10,000**
- Test Accuracy: **88.49%**
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

## Preprocessing

Pixel values ranging from `0–255` were scaled to `0–1`:

```python
X_train = X_train / 255.0
X_test = X_test / 255.0
