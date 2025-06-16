# ΛCDM Parameter Estimation using PyPolyChord

This repository demonstrates how to constrain the standard ΛCDM cosmological model using the [PyPolyChord](https://github.com/PolyChord/PolyChordLite) nested sampling framework.

We combine three state-of-the-art datasets to constrain cosmological parameters:

1. Cosmic Chronometers incorporating the full covariance matrix from "Moresco et al. https://gitlab.com/mmoresco/CCcovariance"
2. Pantheon+ Compilation
3. Baryon Acoustic Oscillation (BAO) data from the latest Data Release 2

You can set up this environment using conda and build PyPolyChord from source.

```bash
# Create environment
conda create -n polychord_env python=3.10 -y
conda activate polychord_env

# Install basic tools and compilers
conda install -c conda-forge numpy cython make cmake git -y
conda install -c conda-forge fortran-compiler compilers -y

# (Optional) For MPI parallelism
conda install -c conda-forge openmpi mpi4py -y

# Clone and build PolyChordLite
git clone https://github.com/PolyChord/PolyChordLite.git
cd PolyChordLite
make

# Install the Python wrapper
pip install .
