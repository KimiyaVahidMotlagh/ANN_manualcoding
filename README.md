# ANN_manualcoding
Artificial neural networks are computing models based on human neural systems. ANN consists of nodes that are connected and form a complete-oriented graph. The graph divides into input, output, and hidden layers and computes the probability based on each connection weight. This project was manually coding an Ann model.

# Table of content
- [Dataset and normalization](https://github.com/KimiyaVahidMotlagh/ANN_manualcoding/blob/main/README.md#dataset-and-normalization) 
- Forward Phase
- Backward Phase
- Train and evaluation

# Dataset and normalization
The Dataset we are training our code for is Mnist. We chose the Mnist Dataset for its simplicity. Each test data has a label so we could train the model based on the labels. We need a 10*1 vector of the encoded label for each train data. 

# Forward Phase
Every ANN model was a weight matrix and bios matrix for each layer. Our calculation also needs an activation function so that our results are between 0 and 1. The sigmoid function is the function we used. Each node saves the sum of the previous layers' nodes multiplied by the weights. Then bios get added, and the activation function will calculate the final result. Our last layer has the nodes with the predictions based on input, weights, and bios. For initializing the training we need to set weights and bios. 

# Backward Phase
An ANN model to retrain itself, will compare the last layer predictions to our labels. The difference in derivatives shows how much the weights and bios will change. In each backpropagation, we move toward the minimal cost. The epochs will determine when the training stops. Epochs are the amount of time we repeat the forward and backpropagation. 

# Train & Evaluation
For easy training, we combined both phases in SGD function. This function needs a learning rate so that the changes by the derivatives are under our control and change as necessary. This function will return the cost, weights, and bios. 
Our final model has hidden layers with 64 and 16 nodes and a learning rate of 2. This model has 95 percent accuracy without the library optimizers for our Mnist dataset.
