# Transformer Model Implementation

A comprehensive implementation of a transformer model using PyTorch for language translation tasks. This repository includes scripts for configuration setup, dataset preparation, model architecture, tokenization, and training. I followed and re-implemented the below tutorial, highly recommend to check it out:

https://youtu.be/ISNdQcPhsts?si=SiHKhcwJIsDb8-BR

## Features
- Configurable model parameters and paths.
- Preprocessing of bilingual datasets (between English and Italian following the above tutorial).
- Implementation of transformer model architecture, encoder, and decoder blocks.
- Custom tokenization for source and target languages.
- Training loop with logging and checkpointing.
- Validation with various metrics.
- I also added my notes for more explanatory visual structures how words are converted into tokens and fed through encoder/decoder blocks, how attention score is calculated, etc.

## Requirements
- Python 3.x
- Libraries: `torch`, `transformers`, `datasets`, `tokenizers`, `tensorboard`

You can install these libraries using pip:
```sh
pip install torch transformers datasets tokenizers tensorboard
```

## Setup

### 1. Clone the Repository
```sh
git clone https://github.com/krm-del/Transformer-From-Scratch.git
cd Transformer-From-Scratch
```

### 2. Configuration
Update the `config.py` file with your desired settings. It includes parameters like batch size, number of epochs, learning rate, sequence length, model dimensions, and paths for saving models and tokenizers.

### 3. Dataset Preparation
Prepare your dataset in the required format (e.g., JSON with translations for source and target languages) and specify the path in the configuration. The vocabulary for English and Italian is added as an example.

### 4. Tokenization
Tokenizers for the source and target languages are built if not already available. They convert text to token IDs and vice versa.

## Usage

### Training the Model
Run the training script to start training the transformer model:
```sh
python train.py
```
This will:
- Load the dataset and create data loaders.
- Build the tokenizers if not already available.
- Initialize the transformer model.
- Train the model for the specified number of epochs.
- Save model checkpoints after each epoch.

### Monitoring Training with TensorBoard
Start TensorBoard to monitor the training process:
```sh
tensorboard --logdir=runs/tmodel
```
Open a browser and navigate to `http://localhost:6006` to view the training logs, loss, and other metrics.
