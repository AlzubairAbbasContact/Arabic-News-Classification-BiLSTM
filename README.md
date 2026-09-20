# Arabic News Classification using BiLSTM

## Project Overview

This project implements a Deep Learning model for classifying Arabic news articles using a Bidirectional Long Short-Term Memory (BiLSTM) neural network.

The main objective of this project is to build an Arabic text classification system that can automatically identify the category of a news article.

The model classifies news articles into seven categories:

- Culture
- Finance
- Medical
- Politics
- Religion
- Sports
- Tech


## Dataset

This project uses the Akhbarona Arabic News Dataset.

The dataset contains Arabic news articles collected from different categories.

After preprocessing and removing empty texts, the final dataset contains:

- Total articles: 78,351
- Number of classes: 7


## Data Preprocessing

The preprocessing pipeline includes:

- Removing empty texts
- Removing URLs
- Removing email addresses
- Removing Arabic diacritics
- Normalizing Arabic characters
- Keeping Arabic letters, English words, and numbers
- Tokenization
- Sequence padding


## Dataset Split

The dataset was divided using stratified splitting to maintain class distribution:

- Training set: 70%
- Validation set: 15%
- Testing set: 15%


Number of samples:

- Training samples: 54,845
- Validation samples: 11,753
- Testing samples: 11,753


## Model Architecture

The proposed model is based on a Bidirectional LSTM architecture.

Model layers:

- Embedding Layer
- SpatialDropout1D Layer
- Bidirectional LSTM Layer
- Dropout Layer
- Dense Layer with ReLU activation
- Softmax Output Layer


Model configuration:

- Vocabulary size: 50,000
- Embedding dimension: 128
- LSTM units: 128
- Maximum sequence length: 800


## Training

The model was trained using:

- Optimizer: Adam
- Loss function: Sparse Categorical Crossentropy
- Evaluation metric: Accuracy


Training techniques:

- ModelCheckpoint for saving the best performing model
- ReduceLROnPlateau for adjusting the learning rate


## Evaluation Results

The final evaluation was performed on an unseen test dataset.

### Test Performance

Test Accuracy:


90.31%


Test Loss:


0.3478



The model was also evaluated using:

- Precision
- Recall
- F1-score
- Confusion Matrix


The model achieved strong performance on categories with clear linguistic patterns such as:

- Sports
- Medical
- Religion


Some categories showed more confusion due to semantic similarity between news topics, such as:

- Culture
- Finance


## Project Structure


Arabic-News-Classification-BiLSTM/

│
├── notebooks/
│ ├── Arabic_News_Training.ipynb
│ └── Arabic_News_Final_Demo.ipynb
│
├── models/
│ ├── best_model.keras
│ ├── tokenizer.pkl
│ └── label_encoder.pkl
│
├── README.md
├── requirements.txt
└── .gitignore



## How to Run

### 1. Install Dependencies

Install the required Python libraries:

```bash
pip install -r requirements.txt
2. Run the Demo

Open:

notebooks/Arabic_News_Final_Demo.ipynb

The notebook loads the trained model and performs classification on new Arabic news texts.

Technologies Used
Python
TensorFlow
Keras
Scikit-learn
NumPy
Pandas
Matplotlib
Saved Model Files

The project includes:

Trained BiLSTM model (best_model.keras)
Tokenizer (tokenizer.pkl)
Label Encoder (label_encoder.pkl)
Author

Alzubair Abbas
