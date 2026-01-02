# Learning Journey: Neural Network for Chemistry & Biology  
*Author: Elango*  
*Started: January 2026*  

---

## 📌 Purpose of This Document
This file tracks my entire learning journey as I explore neural network basics and tools for chemistry, biology, and computational science.   
It contains informations that I collected for my learning from various free sources. I am deeply thankful to all those contributions and the people behind it.

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

  
## 🧩 2. Errors & Fixes

### 🔧 Error: Sequential model has no defined inputs
- Cause: Missing `input_shape` in first Keras layer.
- Fix:
  ```python
  tf.keras.layers.Dense(1000, activation='relu', input_shape=(1024,))
