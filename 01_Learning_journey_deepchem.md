# Learning Journey: DeepChem, PyTorch, TensorFlow for Chemistry & Biology  
*Author: Elango*  
*Started: December 2025*  

---

## 📌 Purpose of This Document
This file tracks my entire learning journey as I explore deep learning tools for chemistry, biology, and computational science.  
When I started from installation of Deepchem, I followed the instructions given in the "The DeepChem Book-Democratizing Deep Learning for Sciences"
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

### ✔️ Installing DeepChem
- Attempted installation with Python 3.13 → **failed** due to version incompatibility.
- Error: `AttributeError: 'str' object has no attribute 'as_numpy_dtype'`
- Diagnosis: DeepChem 2.5.0 is incompatible with TensorFlow 2.20 and Python 3.13.
- Fix: Created a new environment with Python 3.10 and installed DeepChem 2.7.1.

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
