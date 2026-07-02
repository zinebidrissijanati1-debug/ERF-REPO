# Evolutionary Random Forest for Breast Cancer Diagnosis

Source code for the paper:

**"Breast Cancer Diagnosis using a new Evolutionary Forest Approach"**
Z. Idrissi Janati, N. El-Amarty, H. El Fadili. *Scientific Reports* (2026).

This repository contains the implementation of the Evolutionary Random Forest (ERF) framework — a genetic algorithm for feature selection wrapped around a Random Forest classifier — together with all experiment notebooks used to produce the results reported in the paper.

## Method summary

Each individual is a 30-bit binary chromosome (one bit per WBCD feature). Fitness is the mean 5-fold cross-validated accuracy of a Random Forest trained on the decoded feature subset. The population evolves via tournament selection (K = 2), one-point crossover, and bit-flip mutation over 20 generations. Final configuration: population size 100, mutation rate 0.1, 50 trees, unlimited depth, Gini criterion.

## Requirements
scikit-learn=1.6.1
numpy=2.0.2
matplotlib=3.10.0

## Note on reproducibility of the genetic algorithm

The evolutionary algorithm in the original experiments used NumPy's default (unseeded) random state. The notebook `ERF_final.ipynb` preserves the exact outputs reported in the paper: selected subset `[1 7 13 15 21 23 24 26]`, accuracy 0.9859, AUC 0.9968, confusion matrix `[[205, 7], [1, 356]]`. This corresponds to the best-performing run (Run 10 in Table 5).

## License

Released under the MIT License. 
## Citation

If you use this code, please cite: https://doi.org/10.5281/zenodo.21133795
