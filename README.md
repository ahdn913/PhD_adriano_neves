# Complex Networks & Spatial Epidemic Dynamics
> Deterministic and stochastic simulations of epidemic, ecological, and magnetic models on regular, irregular, and complex networks.

![Language](https://img.shields.io/badge/language-C%20%7C%20Python-blue)
![HPC](https://img.shields.io/badge/HPC-OpenMP%20%7C%20CUDA-orange)
![License](https://img.shields.io/badge/license-MIT-green)

## Description

This repository contains the simulation code developed during my Ph.D. in Computational Physics. The research investigates **phase transitions and critical phenomena** in:

- **Epidemic models** (SIR, SIV) on complex networks (Barabási-Albert, Watts-Strogatz, Erdős-Rényi, random geometric, random spherical).
- **Ecological models** (Lotka-Volterra, May-Leonard) in deterministic and stochastic regimes.
- **Magnetic models** (2D Ising) for benchmarking phase transitions.
- **Percolation theory** applied to epidemic spreading.
- **Opinion dynamics** with political bubbles and echo chambers.

The central goal is to understand how network topology and spatial structure affect the emergence of **aggregated states**, **critical exponents**, and **phase transitions** in interacting many-body systems.

## Repository Structure

```
.
├── real/                     # Exploratory SIR and eco chamber simulations in real space
│   ├── epidem/               # Randomly formed connections
│   ├── bolhas/               # echo chamber for synthetic political groups
│   └── polarizacao/          # another eco chamber for synthetic political groups, focusing on the accretion part
│
├── redes/                    # Network-based simulations
    ├── det/                  # Deterministic models
    │   ├── epidem/           # SIR, SIV, SIV diffusive model
    │   ├── rps/              # Predator-prey and rock-paper-scissors ecology
    │   └── pi/               # Monte Carlo methods for approximating the value of pi
    │
    └── est/                  # Stochastic models
        ├── ising/            # 2D Ising model
        ├── lv/               # Stochastic Lotka-Volterra
        ├── ml/               # Stochastic May-Leonard
        ├── off_ml/           # May-Leonard in real space
        ├── perco_siv/        # Percolation + SIV
        ├── percolacao/       # Pure percolation (conductor and insulating spheres in a capacitor)
        ├── rpsir/            # SIR + May-Leonard hybrid
        ├── sir/              # SIR on von Neumann lattice
        └── siv/              # SIV on von Neumann lattice

## Requirements

- **C compiler**: `gcc` (≥ 9.0)
- **OpenMP** (parallel CPU)
- **CUDA** (GPU, optional)
- **Python**: ≥ 3.8
- **Libraries**: `numpy`, `scipy`, `pandas`, `matplotlib`, `seaborn`, `h5py`, `stdio.h`, `stdlib.h`, `math.h`, `time.h`, `gsl/gsl_rng.h`
- **HDF5** (for large data storage)
- **OS**: Linux (Ubuntu) or WSL2

Install Python dependencies:
```bash
pip install numpy scipy pandas matplotlib seaborn h5py
```

Install HDF5 development libraries:
```bash
sudo apt install libhdf5-dev
```

## Compilation and Execution

Each `.c` file includes its own compilation/execution instructions as header comments. General pattern:

```bash
# Serial
gcc -O2 -o program program.c -lm

# OpenMP (parallel)
gcc -O2 -fopenmp -o program program.c -lm

# CUDA (GPU)
nvcc -O2 -o program program.cu
```

Run:
```bash
./program
```

## Modules Overview

### `real/` — Real-space SIR
Exploratory simulations of SIR dynamics with different connection rules (random, radius-based, fixed-N). Includes models for **political bubbles and echo chambers** with aggregation tendencies.

> ⚠️ This folder is a **testbed** for exploratory ideas. It is not production-quality code.

### `redes/det/` — Deterministic Network Models
- **epidem**: SIR, SEIR, SIV solved with RK2/RK4.
- **bolhas**: eco chambers for synthetic political groups without the accretion of individuals.
- **polarizacao**: eco chambers for synthetic political groups with the accretion of individuals.

### `redes/est/` — Stochastic Network Models
- **`ising/`**: 2D Ising model with Metropolis algorithm.
- **`lv/`**: Stochastic Lotka-Volterra.
- **`ml/`**: Stochastic May-Leonard.
- **`off_ml/`**: May-Leonard in real space (off-lattice).
- **`perco_siv/`** & **`percolacao/`**: Percolation theory applied to SIV and pure percolation.
- **`rpsir/`**: Hybrid SIR + May-Leonard in real space.
- **`sir/`** & **`siv/`**: Epidemiological models on von Neumann lattices.

## Results

- **Critical exponents** determined for percolation on complex networks.
- **Phase transitions** identified in SIR/SIV dynamics on regular and irregular lattices.
- **Turing patterns** and **aggregated states** reproduced in opinion dynamics models.

## References

- Barabási, A.-L. *Network Science*. Cambridge.
- Newman, M. E. J. *Networks: An Introduction*. Oxford.
- Marro, J., & Dickman, R. *Nonequilibrium Phase Transitions in Lattice Models*. Cambridge.
- Murray, J. D. *Mathematical Biology*. Springer.

## License

MIT License — see `LICENSE` file for details.

## Contact

**Adriano Neves**
[GitHub](https://github.com/ahdn913) · [LinkedIn](https://www.linkedin.com/in/adriano-henrique-neves/) · [ORCID](https://orcid.org/0000-0002-8734-4660)
