# PA-ISTA: Physics-Aware Iterative Shrinkage-Thresholding Algorithm

This repository contains the implementation of the Physics-Aware Iterative Shrinkage-Thresholding Algorithm (PA-ISTA) for sparse signal recovery in PDE-governed measurement systems.

## Paper

**"Physics-Aware Sparse Signal Recovery Through PDE-Governed Measurement Systems"**

*Authors: Tadashi Wadayama, Koji Igarashi, Takumi Takahashi*

## Overview

PA-ISTA combines the computational efficiency of the Iterative Shrinkage-Thresholding Algorithm (ISTA) with accurate physical modeling using numerical PDE solvers and automatic differentiation. The algorithm incorporates the underlying physics through the nonlinear Schrödinger equation (NLSE) for optical fiber channels.

### Key Features

- **Physics-aware signal recovery**: Incorporates PDEs directly into the recovery process
- **Automatic differentiation**: Uses Wirtinger derivatives for complex-valued optimization
- **Deep unfolding**: Optimizes algorithm parameters using a store-and-replay method
- **SSFM integration**: Employs Split-Step Fourier Method for NLSE solving

## Requirements

- Julia 1.9
- Required packages:
  - LinearAlgebra
  - Plots
  - Flux
  - FFTW
  - Random
  - Zygote

## Usage

The main implementation is contained in `exp3-MSE.ipynb`. The notebook demonstrates:

1. **Parameter Settings**: Configure NLSE parameters (β₂, γ, T₀)
2. **Signal Generation**: Create sparse test signals
3. **PA-ISTA Algorithm**: Physics-aware recovery with deep unfolding
4. **Performance Evaluation**: MSE comparison with baseline methods

### Running the Code

```julia
# Install required packages
using Pkg
Pkg.add(["LinearAlgebra", "Plots", "Flux", "FFTW", "Random", "Zygote"])

# Run the notebook
# Open exp3-MSE.ipynb in Jupyter or VS Code
```

## Algorithm Parameters

- **Dispersion coefficient**: β₂ = -10 (ps²/km)
- **Nonlinearity coefficient**: γ = 2.0
- **Pulse half-width**: T₀ = 1 (ps)
- **Signal sparsity**: k = 3 non-zero elements out of n = 30
- **SNR**: 15 dB (configurable)

## Results

The algorithm demonstrates significant improvements over conventional methods:
- Superior MSE performance compared to Digital Back Propagation (DBP)
- Effective parameter optimization through deep unfolding
- Robust recovery in the presence of observation noise

## Citation

If you use this code in your research, please cite our paper:

```bibtex
@inproceedings{wadayama2025physics,
  title={Physics-Aware Sparse Signal Recovery Through PDE-Governed Measurement Systems},
  author={Wadayama, Tadashi and Igarashi, Koji and Takahashi, Takumi},
  booktitle={IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP)},
  year={2025}
}
```

## License

This project is licensed under the MIT License.

## Contact

- Tadashi Wadayama: wadayama@nitech.ac.jp
- Nagoya Institute of Technology