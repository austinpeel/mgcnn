# mgcnn

A Convolutional Neural Network (CNN) architecture for classifying standard and modified gravity (MG) cosmological models based on the weak-lensing convergence maps they generate.

This repository contains the data and code to reproduce the results in [Distinguishing standard and modified gravity cosmologies with machine learning](https://arxiv.org/abs/1810.11030) (Peel et al. 2018).

## Data

In the paper we use weak-lensing data obtained by ray-tracing through the DUSTGRAIN-pathfinder simulation set presented in [Weak lensing light-cones in modified gravity simulations with and without massive neutrinos](https://academic.oup.com/mnras/article-abstract/481/2/2813/5094586) (Giocoli et al. 2018).  These simulations are not yet public, so we are not able to include the original convergence maps derived from the various cosmological runs. We do provide, however, the wavelet PDF datacubes derived for the four models as described in the paper: one standard `LCDM` and three modified gravity `f(R)` models.

## Requirements

* Python3
* Numpy
* Keras with Tensorflow as backend
* scikit-learn

## Usage

```shell
$ python3 train_mgcnn.py -n0
```

The three options for the noise flag `-n` are (0, 1, 2), which correspond to noise standard deviations of sigma = (0, 0.35, 0.70) added to the original convergence maps. Additional options are `-i` and `-e` to specify the number of training iterations and epochs, respectively.

Confusion matrices and evaluation metrics (loss function and validation accuracy) are saved as `numpy` arrays in the generated output/ directory after each iteration.

## Figures

<img src="https://github.com/austinpeel/mgcnn/blob/master/figures/pdf_cm_sigma0.png" alt="noiseless_confusion_matrix" width="400"/>
