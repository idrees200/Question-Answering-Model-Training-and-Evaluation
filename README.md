# Question Answering Model Training and Evaluation

## Overview
This repository contains Python scripts for training and evaluating Question Answering (QA) models using the SimpleTransformers library. QA models are essential for automatically answering questions posed in natural language, making them valuable for various applications such as customer support automation, information retrieval systems, and more.

The training and evaluation process involves using a dataset (`train.csv`) containing questions paired with their corresponding answers. After training, the models are evaluated on another dataset (`eval.csv`) to assess their performance metrics such as accuracy, precision, recall, and F1-score. All training and evaluation metrics are logged using Weights and Biases (WandB), facilitating easy tracking and visualization of model performance over time.

## Requirements
- Python 3.x
- `simpletransformers` library for easy implementation of Transformer-based models
- `pandas` for data manipulation and preprocessing
- `scikit-learn` for evaluating model performance metrics
- `wandb` for logging and visualizing training and evaluation metrics

Install the required libraries using the following command:

pip install -qqq simpletransformers pandas scikit-learn wandb
# Dataset
Ensure you have a CSV file named `train.csv` that contains at least two columns: `Question` and `Answer`. This file serves as the training data for the QA models. Each row represents a question-answer pair used to train the models.

# Configuration
The repository includes configurations for different model types and hyperparameters. Each model configuration specifies:

## BERT
- **Model name**: `bert-base-uncased`
- **Training batch size**: 16
- **Evaluation batch size**: 16
- **Number of training epochs**: 3
- **Learning rate**: 5e-5
- **WandB project**: `MedQuad_QA_BERT`

## MobileBERT
- **Model name**: `google/mobilebert-uncased`
- **Training batch size**: 16
- **Evaluation batch size**: 16
- **Number of training epochs**: 3
- **Learning rate**: 5e-5
- **WandB project**: `MedQuad_QA_MobileBERT`

## RoBERTa
- **Model name**: `roberta-base`
- **Training batch size**: 16
- **Evaluation batch size**: 16
- **Number of training epochs**: 3
- **Learning rate**: 5e-5
- **WandB project**: `MedQuad_QA_RoBERTa`

# Usage
1. **Prepare the Dataset**: Ensure `train.csv` is correctly formatted with questions and their corresponding answers. This dataset will be used to train the QA models.

2. **Run the Script**: Execute the script (`train_and_eval.py`) to start training and evaluating the models. The script iterates over different model configurations and hyperparameters, training each model and evaluating its performance on the validation dataset (`eval.csv`).

3. **Logging with WandB**: Metrics such as accuracy, precision, recall, and F1-score are logged to WandB during both training and evaluation phases. Ensure you have an account on WandB and set up your API key for logging.

4. **Evaluate Models**: After training, the models are automatically evaluated using the `eval.csv` dataset. Evaluation results, along with training metrics, are logged to WandB for analysis.

