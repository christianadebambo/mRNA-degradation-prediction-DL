# Covid-19 mRNA Vaccine Degradation Prediction

This project contains code for predicting likely degradation rates at each base of an RNA molecule in Covid-19 mRNA vaccines. The goal is to design a model that can assist in understanding the degradation patterns of mRNA vaccines, which can be useful for vaccine development and optimization.

Dataset taken from [Kaggle](https://www.kaggle.com/competitions/stanford-covid-vaccine)

## Introduction

The code provided in this repository utilizes Python and popular libraries such as pandas, numpy, TensorFlow, and plotly.express to preprocess the input data, build and train a model, make predictions, and perform post-processing.

## Code Overview

1. Libraries and Dependencies:
   - The code imports various libraries and dependencies such as json, pandas, numpy, plotly.express, and tensorflow.keras to facilitate data processing, modeling, and visualization.

2. Helper Functions and Useful Variables:
   - The code defines several helper functions and useful variables required for model building and data preprocessing. These functions include MCRMSE for calculating the mean column-wise root mean squared error, gru_layer for creating a bidirectional GRU layer, and build_model for constructing the model architecture.

3. Data Preprocessing:
   - The code reads the training and testing data from JSON files into pandas DataFrames.
   - The training data is filtered based on a condition (signal_to_noise >= 1).
   - A token-to-integer mapping (token2int) is created to convert the input sequences into integer-encoded inputs.
   - The preprocess_inputs function is used to preprocess the training data by mapping the tokens to integers and converting the resulting DataFrame to a NumPy array.

4. Model Training and Evaluation:
   - The training data is split into training and validation sets using the train_test_split function from scikit-learn.
   - The code builds a model using the build_model function and compiles it with the Adam optimizer and the MCRMSE loss function.
   - The model is trained using the fit method, with the training and validation data, batch size, number of epochs, and callbacks for reducing learning rate on plateau and saving the model checkpoint.
   - The training history is evaluated and visualized using the plotly.express library.

5. Model Loading and Prediction:
   - Two separate models (model_public and model_private) are created using the build_model function, with different sequence lengths.
   - The weights of the trained model are loaded into both models.
   - The models make predictions on the public and private test inputs.

6. Post-processing:
   - The predictions are post-processed by iterating over the test data and predictions, creating DataFrames for each prediction, and appending them to a list.
   - The list of DataFrames is concatenated into a single DataFrame (preds_df) containing the predictions for each ID and sequence position.

## Requirements

To run the code in this repository, you will need the following dependencies:

- Python 3.x
- TensorFlow 
- pandas
- numpy 
- plotly

## Getting Started

To get started with this code, follow the steps below:

1. Clone this repository to your local machine.
2. Install the necessary dependencies specified in the Requirements section
3. Prepare the data by downloading the `train.json` and `test.json` files. Make sure they are in the same directory as the code.
4. Run the script `main.py` to preprocess the data, build and train the model, make predictions, and perform post-processing.

## Results

The results of the model predictions can be found in the generated DataFrame, which contains the predicted degradation rates for each RNA sequence. Additionally, a training history plot is generated to visualize the model's performance during training.
