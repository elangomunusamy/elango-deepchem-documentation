# Learning Journey: DeepChem, PyTorch, TensorFlow for Chemistry & Biology  
*Author: Elango*  
*Started: December 2025*  

---

## 📌 Purpose of This Document
This file tracks my entire learning journey as I explore deep learning tools for chemistry, biology, and computational science.   
When I started from installation of Deepchem, I followed the instructions given in the "The DeepChem Book-Democratizing Deep Learning for Sciences". 
I kindly acknowledge the author, Bharath Ramsundar and the DeepChem team.

It includes:
- Installation steps  
- Errors I encountered  
- How I fixed them  
- Notes on DeepChem, PyTorch, TensorFlow  
- Mini‑projects and experiments  
- Lessons learned  

---

## 🧪 1. Environment Setup

### ✔️ Installing Python
- I installed ubuntu 24.04 (WSL) in my windows laptop. The command `lsb_release -a` can be used to know your version.
- The default python version is 3.13.9 and is the latest version. The command `python --version` will tell your python version.
- In addition to latest python version, I also have other previous versions of python installed.

### ✔️ Creating Environments using Conda
- To create a new environment in python, miniconda3 could be installed in python.  I have installed conda 25.11.1 in ubuntu WSL.
- A new environment is created with the command `conda create -n deepchem-27 python=3.10`.
- The deepchem book was written few years ago where older versions of scientific tools were used. So to learn from the book, it is advisable to use older versions of all the tools.
- After the environment is created, activate it using the command `conda activate deepchem-27` and deactivate it using the command `conda deactivate`.
- Inside the deepchem-27 environment, we should install the versions of deepchem, pytorch, tensorflow, rdkit, etc that are compatible with each other.
- Given below are the tools/versions installed with python version 3.10
  - `pip install torch torchvision torchaudio` version 2.9
  - `pip install numpy==1.24`
  - `pip install rdkit-pypi matplotlib scikit-learn`
  - `pip install deepchem==2.7.1`
  - `pip install tensorflow==2.12.0`
  
### ✔️ Installing DeepChem
- Attempted installation with Python 3.13 → **failed** due to version incompatibility.
- Error: `AttributeError: 'str' object has no attribute 'as_numpy_dtype'`
- Diagnosis: DeepChem 2.5.0 is incompatible with TensorFlow 2.20 and Python 3.13.
- Fix: Created a new environment with Python 3.10 and installed DeepChem 2.7.1.
- Error: `AttributeError: module 'scipy.stats' has no attribute 'gilbrat'. Did you mean: 'gibrat'?`
- Diagnosis: Deepchem 2.7 requires scipy older version. Installed scipy 1.10.1
- Error: `ModuleNotFoundError: No module named 'numpy._core'`
- Diagnosis: Installed the numpy==1.26.4 version
- 
### ✔️ Installing TensorFlow
- TensorFlow 2.12 not available for Python 3.13.
- Solution: Installed TensorFlow 2.12 inside Python 3.10 environment.

### ✔️ Installing PyTorch
- Error: `ModuleNotFoundError: No module named 'torch'`
- Fix: Installed PyTorch using pip inside the same environment.

---

## 🧩 2. Errors & Fixes

### 🔧 Error: Sequential model has no defined inputs
- Cause: Missing `input_shape` in first Keras layer.
- Fix:
  ```python
  tf.keras.layers.Dense(1000, activation='relu', input_shape=(1024,))
