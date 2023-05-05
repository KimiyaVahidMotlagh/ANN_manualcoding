# ANN_manualcoding
Artificial neural networks are computing models based on human neural systems. ANN consists of nodes that are connected and form a complete-oriented graph. The graph divides into input, output, and hidden layers and computes the probability based on each connection weight. This project is manually coding an Ann model.

# Table of content
- [Dataset and Normalization](https://github.com/KimiyaVahidMotlagh/ANN_manualcoding/blob/main/README.md#dataset-and-normalization) 
- [Forward Phase](https://github.com/KimiyaVahidMotlagh/ANN_manualcoding/blob/main/README.md#forward-phase)
- [Backward Phase](https://github.com/KimiyaVahidMotlagh/ANN_manualcoding/blob/main/README.md#backward-phase)
- [ANN Model Engneering]()
- [Train and Evaluation](https://github.com/KimiyaVahidMotlagh/ANN_manualcoding/blob/main/README.md#train--evaluation)

# Dataset and normalization
The Dataset we are training our code for is Mnist. We chose the Mnist Dataset for its simplicity. In Mnist we have 80000 images, each has 28*28 resolution. 
Each test data has a label so we could train the model based on the labels. We need a vector[10] of the encoded label for each train data. 

# Forward Phase
Every ANN model was a weight matrix and bios matrix for each layer. Our calculation also needs an activation function so that we find Nonlinear functions. The sigmoid function is the activation function we used. Each node calculates $W*X+b$ based on the previous layer's data, weights, and bios. 
<br/> <br/>
- W_init(): Matrix with a random number in the range of 0 and 1 for initialization.
- b_init(): Vector with all zero data for initialization.
- init_matrix(): 
# Backward Phase
An ANN model to retrain itself, will compare the last layer predictions to our labels. The difference in derivatives shows how much the weights and bios will change. In each backpropagation, we move toward the minimal cost. The epochs will determine when the training stops. Epochs are the amount of time we repeat the forward and backward phase. 

# ANN Model Engeenering


# Train & Evaluation
For easy training, we combined both phases in SGD function. This function needs a learning rate so that the changes by the derivatives are under our control and change as necessary. This function will return the cost, weights, and bios. 
Our final model has hidden layers with 64 and 16 nodes and a learning rate of 2. This model has 95 percent accuracy without the library optimizers for our Mnist dataset.
