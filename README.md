# Knowledge Distillation for Opportune Moment Detection and Emotion Classification

This repository presents a two-stage pipeline for emotion recognition enhanced by knowledge distillation. A teacher-student architecture is used to identify opportune moments in physiological signals, followed by emotion classification using valence-arousal labels collected at those moments. Baseline models are also included for comparison.

## Files

### 1. `mycode.ipynb`
- **Purpose**: Train a **teacher model** for detecting opportune moments from physiological signals, and distill its knowledge into a **lighter student model**.
- **Process**:
  - The teacher model is trained using multiple physiological inputs and RuLSIF-based labels.
  - A student model is trained to mimic the teacher’s predictions on opportune moments.
- **Output**: A compact, generalized student model capable of identifying opportune moments efficiently.

### 2. `emotion.ipynb`
- **Purpose**: Use the **student model** from `mycode.ipynb` to detect opportune moments across the dataset, and collect **valence-arousal labels** at those moments for emotion classification.
- **Process**:
  - Segments predicted as opportune are selected.
  - Emotion labels (valence-arousal) are extracted at those moments.
  - A separate classifier is trained using these labeled samples and a set of physiological features.
- **Goal**: Demonstrate that training on emotionally salient (opportune) moments improves classification accuracy.

### 3. `baselines.ipynb`
- **Purpose**: Implement various **baseline models** for opportune moment detection.
- **Baselines Include**:
  - Fixed time-based selection
  - Random selection
  - Classical ML models (e.g., Random Forest, SVM)
  - Personalized, aggregate, and demographic-specific models (e.g., age-based, gender-based)

## Pipeline Summary

1. **Knowledge Distillation** (`mycode.ipynb`)
   - Train teacher → Distill to student
2. **Opportune-Based Emotion Classification** (`emotion.ipynb`)
   - Use student model for moment selection → Train emotion classifier on selected data
3. **Baseline Comparisons** (`baselines.ipynb`)
   - Evaluate effectiveness of student model against conventional and personalized baselines

## Notes

- The student model serves as a lightweight, deployable alternative to the complex teacher model.
- Only signals that are easily extractable using hand-wearable devices (e.g., GSR, BVP, skin temperature) are used as inputs to the student model, making it practical for real-world deployment.
- Emotion labels collected at opportune moments are assumed to be more expressive and reliable.
- This approach leverages signal change dynamics (via RuLSIF) for both training and evaluation.
