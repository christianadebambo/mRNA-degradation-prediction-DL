# Covid-19 mRNA Vaccine Degradation Prediction

This project contains code for predicting likely degradation rates at each base of an RNA molecule in Covid-19 mRNA vaccines. The goal is to design a model that can assist in understanding the degradation patterns of mRNA vaccines, which can be useful for vaccine development and optimization.

Dataset taken from [Kaggle](https://www.kaggle.com/competitions/stanford-covid-vaccine)

## Introduction

The code provided in this repository utilizes Python and popular libraries such as pandas, numpy, TensorFlow, and plotly.express to preprocess the input data, build and train a model, make predictions, and perform post-processing.

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

## Code Structure

- `main.py`: The main script that executes the complete workflow, including data preprocessing, model building, training, prediction, and post-processing.
- `model.py`: Contains functions for building the model architecture using the Keras API.
- `data_utils.py`: Contains utility functions for data preprocessing, including token-to-integer mapping, sequence encoding, and array conversion.
- `utils.py`: Contains helper functions used throughout the code, such as the calculation of mean column-wise root mean squared error.

## Results

The results of the model predictions can be found in the generated DataFrame, which contains the predicted degradation rates for each RNA sequence. Additionally, a training history plot is generated to visualize the model's performance during training.
