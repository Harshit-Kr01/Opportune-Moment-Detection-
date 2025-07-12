# Opportune Moment Detection & Emotion Classification using CNN-based Model

This repository contains two notebooks that together form a two-stage pipeline for detecting opportune moments in physiological signal data and using them to improve emotion classification.

## Files

### 1. `nn_based.ipynb`
- **Purpose**: Train a **CNN model with late fusion** to detect **opportune moments** using multimodal physiological signals such as GSR, BVP, and skin temperature.
- **Model**: Convolutional layers are applied to each signal stream independently (early layers), followed by concatenation and fully connected layers (late fusion).
- **Output**: Binary classification of each segment as either an **opportune moment** (`1`) or **inopportune** (`0`), used to guide emotion labeling in the next stage.

### 2. `emotion_nn_opportune.ipynb`
- **Purpose**: Perform **emotion classification** using data collected specifically at **opportune moments** identified by the model trained in `nn_based.ipynb`.
- **Input**: Only those segments predicted as opportune are used as training samples.
- **Model**: A separate classifier is trained to predict emotional states using a different subset of physiological signals (e.g., ECG, EMG, Respiration).

## Pipeline Overview

1. **Opportune Moment Detection** (`nn_based.ipynb`)
   - Input: Raw physiological signals
   - Output: Binary labels per segment (opportune/inopportune)

2. **Emotion Classification** (`emotion_nn_opportune.ipynb`)
   - Input: Segments predicted as opportune moments
   - Output: Emotion labels (multi-class classification)

