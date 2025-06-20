# Model Training and Distillation Pipeline

This folder contains three Jupyter notebooks that form the core of a machine learning pipeline involving model training, knowledge distillation, and final evaluation. Below is a brief description of each file:

## 📁 Files Description

### 1. `baselines.ipynb`
This notebook is responsible for training and saving the **teacher models**. These models serve as the high-capacity reference models that will later be used in the distillation process.

### 2. `distillation.ipynb`
This notebook performs **knowledge distillation** using the previously trained teacher models. It generates and saves **student models**, which are lightweight versions of the teacher models optimized for faster inference with minimal performance loss.

### 3. `emotion_baselines.ipynb`
This notebook carries out the **final evaluation** of the models. It tests the performance of both teacher and student models on the target emotion recognition task and provides comparative results.

---

## 🛠 Requirements

Make sure to install all necessary dependencies listed in your project environment (e.g., `requirements.txt` or environment setup guide).

---

## 📌 Notes

- Ensure the teacher models are saved correctly before running the distillation notebook.
- The evaluation assumes that both teacher and student models are already trained and saved.


