# Investigating Spectral Bias in CNNs

This project investigates how different image frequency components affect the performance, robustness, and inference efficiency of a small Convolutional Neural Network (CNN). The experiments use CIFAR-10 and compare original, low-frequency, high-frequency, and noisy image versions.

## Project Description

The main goal is to test whether changing the frequency content of input images changes how well a CNN learns and generalizes.

The notebook includes:

- Loading CIFAR-10
- Creating transformed datasets
- Training a vanilla CNN
- Comparing accuracy and loss across conditions
- Testing robustness on frequency-shifted inputs
- Generating error-analysis examples and result figures

## Dataset Conditions

| Condition | Description |
|---|---|
| Original | Unmodified CIFAR-10 images |
| Low-frequency | Gaussian-blurred images |
| High-frequency | Original images minus blurred images, emphasizing edges/details |
| Noisy | Images with added Gaussian noise |

## Repository Structure

```text
spectral-bias-cnn/
├── README.md
├── requirements.txt
├── CS271Project.ipynb
├── results/
│   └── .csv result files
├── figures/
│   └── generated plots and misclassified examples
└── .gitignore


## Requirements

Install dependencies with:

```bash
pip install -r requirements.txt
```

Suggested `requirements.txt`:

```txt
torch
torchvision
numpy
pandas
matplotlib
pillow
jupyter
```

## How to Run

Clone the repository:

```bash
git clone <your-repo-url>
cd spectral-bias-cnn
```

Install requirements:

```bash
pip install -r requirements.txt
```

Open the notebook:

```bash
jupyter notebook CS271Project.ipynb
```

Then run the notebook cells in order.

The notebook will automatically download CIFAR-10 using `torchvision`.
## Outputs

The notebook produces:

- CSV result files in `results/`
- Accuracy and loss curves
- Robustness bar chart
- Misclassified example images
- Inference efficiency results

## Summary

The original and high-frequency image conditions performed best, while low-frequency blurred images and noisy images reduced performance. The results suggest that edge and boundary information remained important for CIFAR-10 classification, and that spectral bias was not clearly observed as stronger performance on low-frequency inputs in this small CNN setting.
