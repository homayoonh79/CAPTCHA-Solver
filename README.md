# CAPTCHA-Solver
Train a model for recognizing the characters in CAPTCHA images.

# How to use
Run the Captcha_Solver.ipynb file in google colab. Then upload the train.zip data file to colab.
Run the codes and enjoy the built model. You can modify it according to your needs.

# Description
The provided code is designed to train a model for recognizing the characters in CAPTCHA images. The model uses a Convolutional Neural Network (CNN) and Recurrent Neural Network (RNN) with Connectionist Temporal Classification (CTC) loss.
Here is a step-by-step explanation of the code:
1.	Import dependencies: The script begins by importing necessary libraries and modules such as os, numpy, matplotlib, pathlib, tensorflow, and keras.
2.	Data preparation: The script reads the CAPTCHA images from a directory, extracts the labels (the actual CAPTCHA text) from the image filenames, and finds the unique characters present in the labels.
3.	Preprocessing: The characters are then encoded into numeric format using StringLookup. Two mappings are created: one for converting characters to numbers (char_to_num), and another for converting numbers back to characters (num_to_char).
4.	Data splitting: The script divides the dataset into training and validation sets using a custom split_data function.
5.	Image encoding: The encode_single_sample function is defined to convert each image and its corresponding label into a format suitable for training the model. This includes reading the image file, converting it to grayscale, normalizing it, resizing it, transposing it, and converting the label to numeric format.
6.	Dataset creation: TensorFlow Dataset objects for the training and validation datasets are created, with each dataset item being a tuple of an image and its corresponding label.
7.	Model creation: The model is built using the build_model function. This function defines a model architecture that consists of several layers including Conv2D, MaxPooling2D, Reshape, Dense, Bidirectional LSTM, and a custom CTCLayer. The CTCLayer uses the CTC loss function, which is suitable for sequence prediction problems where the timing is variable, such as recognizing characters in a CAPTCHA.
8.	Training: The model is trained for a specified number of epochs with early stopping to prevent overfitting.
9.	Inference: A prediction model is created by extracting layers up to the output layer of the trained model. This prediction model is used to decode the predictions from the validation dataset and visualize them.
10.	Saving the model: Finally, the prediction model is saved as an h5 file for later use.
This script is an example of how to train a model for CAPTCHA recognition. You can modify it according to your needs, such as changing the model architecture, adjusting the preprocessing steps, or using a different dataset.

