# TTS model for Technical English Vocabulary
# Text-to-Speech Model Training

## Note: Due to limited GPU runtime on Colab, the model cannot be trained in a singel instance. Therefore, gradient checkpoint has been enabled to ensure gradual retrining on a daily basis.


## Overview
This repository contains the code and resources for training a text-to-speech (TTS) model. The goal is to fine-tune a pre-trained TTS model to improve speech quality and adapt to specific speaker characteristics.

## Table of Contents
- [Introduction](#introduction)
- [Dataset Description](#dataset-description)
- [Model Architecture](#model-architecture)
- [Training Setup](#training-setup)
- [Approach](#approach)
- [Performance Evaluation](#performance-evaluation)
- [Audio Samples](#audio-samples)
- [Installation](#installation)
- [Contributing](#contributing)
- [License](#license)

## Introduction
This is a Microsoft SpeechT5 model fine-tuned for Technical English Vocabulary. 

## Dataset Description
- **Source**: https://www.kaggle.com/datasets/shigrafs/english-technical-interview & https://www.kaggle.com/datasets/shigrafs/english-wav
- **Content**: 
  - No of Audio files: 16512
  - Number of speakers: 1
  - Types of speech: Scripted
- **Preprocessing Steps**:
  - Normalization of audio levels
  - Segmentation into shorter clips
  - Tokenization of text data

## Model Architecture
This project utilizes the Microsoft Text-To-Speech architecture, which is based on Google T5 model. 

### Key Features
- [List any specific features or modifications made to the model]

## Approach 
The dataset stored on Kaggle contains the wav files and the labels. They are loaded onto a dataset dictionary along with it's array representation and sampling rate. All the characters are extracted and the new characters found in the data is added to the tokenizer. Speechbrain model is used to generate the speaker embeddings to help the model adjust it's output. The dataset is prepared and longer files are trimmed off so as per the model requirement. SpeechT5 takes 600 token length of input. The dataset is split into train and test. A data collator is implemented to handle the padding. Training arguments is set up along with a remote repository. The model is set to be trained for 7 epochs. The training is done in steps to handle limited colab GPU access. The model is pushed to HuggingFace repository.


## Training Setup
- **Environment**: 
  - Python version: 3.10.12 (main, Sep 11 2024, 15:47:36) [GCC 11.4.0]
  - Libraries: 
    - PyTorch: 2.5.0+cu121
    - NumPy: 1.26.4
    - Pandas: 2.2.2
    - Matplotlib: 3.7.1
- **Hyperparameters**:
  - Learning rate: [Value]
  - Batch size: [Value]
  - Number of epochs: 20

### Training Logs
![Loss Curve](path/to/loss_curve.png)  
*Description of the loss curve and what it indicates about training.*

## Performance Evaluation
- **Metrics**:
  - Mean Opinion Score (MOS): [Score]
  - Character Error Rate (CER): [Score]
- **Results**:
  - Pre-trained model: [Metrics]
  - Fine-tuned model: [Metrics]
  
*Analysis of performance improvements observed during fine-tuning.*

## Audio Samples
Listen to samples generated by both the pre-trained and fine-tuned models:
- **Pre-trained Model**: [Link or description of the audio sample]
- **Fine-tuned Model**: [Link or description of the audio sample]

## Installation
To set up the environment, run the following commands:

```bash
git clone https://github.com/ShigrafS/TechEngTTS.git
cd your-repo
pip install -r requirements.txt
```

## Contributing 

Contributions are welcome! Please open an issue or submit a pull request for any changes or improvements.

## License


