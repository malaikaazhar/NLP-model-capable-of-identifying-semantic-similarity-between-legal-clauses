
# Clause Similarity Classification

This repository contains code for building a clause similarity classification model using TensorFlow/Keras. The workflow includes:

## 📁 Dataset Loading
- Downloads dataset from Kaggle using `kagglehub`.
- Reads multiple CSV files containing legal/contractual clauses.
- Combines them into a unified DataFrame.

## 🧹 Preprocessing
- Cleans text using custom preprocessing:
  - Lowercasing
  - Removing special characters
  - Normalizing whitespace
- Generates positive and negative clause pairs for training:
  - Positive pairs: clauses with the same label.
  - Negative pairs: clauses with different labels.

## 🧪 Feature Engineering
- Vectorizes text using `TextVectorization`.
- Converts clause pairs into numerical sequences.
- Prepares inputs: `A` (clause1), `B` (clause2), and labels `y`.

## 🧠 Model Architecture
- Twin-tower (Siamese) LSTM-like design using:
  - Embedding layers
  - Bidirectional LSTMs
  - Dense layers
- Combines encoded clause vectors using absolute difference.
- Final output: binary similarity (0 = not similar, 1 = similar).

## 🔧 Training
- Uses binary cross-entropy loss.
- Includes callbacks:
  - EarlyStopping
- Evaluates model using accuracy and loss.

## 📊 Outputs
- Prints dataset shapes.
- Displays sample clause pairs.
- Shows training logs and results.

## ▶️ How to Run
1. Install dependencies:
   ```bash
   pip install tensorflow numpy pandas kagglehub scikit-learn
   ```
2. Place the notebook in your working environment.
3. Run all cells sequentially.
