# neural-network-classifier

Here's a step-by-step explanation of my neural network project:

## 1. Dataset Creation
I manually created three binary images (5 rows × 6 columns) to represent the letters A, B, and C using 0s and 1s. These images are flattened into 1D arrays (of length 30) for processing in the neural network.

Each letter is then labeled using one-hot encoding:

A → [1, 0, 0]

B → [0, 1, 0]

C → [0, 0, 1]

This format is used so the model can learn to output a probability distribution over three possible classes.

## 2. Visualization
To confirm the images look correct, you display the data using a heatmap-style image, where 0s appear as black and 1s as white (or vice versa), allowing you to see the shape of the letter.

## 3. Neural Network Design
I implemented a simple feedforward neural network with:

Input layer: 30 neurons (one for each pixel)

Hidden layer: 5 neurons (arbitrary size)

Output layer: 3 neurons (one for each class: A, B, C)

I used the sigmoid activation function in both hidden and output layers to introduce non-linearity.

## 4. Forward Propagation
This is the process of sending input data through the network:

Multiply the input by weights to get a hidden layer signal.

Apply the activation function (sigmoid).

Do the same from hidden to output layer.

The final output is a prediction vector like [0.9, 0.05, 0.02].

## 5. Loss Function
I used mean squared error (MSE) to measure how far the predicted output is from the actual label. This tells the network how "wrong" its prediction is.

## 6. Backpropagation
This is the learning step:

It calculates how to adjust the weights to reduce the loss.

Using the chain rule, it computes gradients (slopes) of the loss with respect to the weights.

Then it updates the weights using a small step in the direction that minimizes the loss (controlled by the learning rate alpha).

## 7. Training Loop
I trained the model for several epochs (training cycles). For each epoch:

The network makes predictions on all training samples.

The loss is computed for each.

The weights are updated via backpropagation.

I store and print the accuracy and average loss.

## 8. Plotting Results
After training:

I plot accuracy vs. epochs to see how well the model improves.

I plot loss vs. epochs to confirm the model is learning (loss should decrease).

## 9. Prediction Function
I wrote a function to test the trained model:

It takes an image input.

It runs forward propagation to get a prediction.

It identifies the class with the highest score and prints whether it’s A, B, or C.

Then it displays the image again.

## 10. Weights Initialization
Before training, I randomly initialized the weights connecting input → hidden and hidden → output layers. This is necessary to break symmetry and allow learning.
