# ANN_manualcoding
Artificial neural networks are computing models based on human neural systems. ANN consists of nodes that are connected and form a complete-oriented graph. The graph divides into input, output, and hidden layers and computes the probability based on each connection weight. This project is manually coding an Ann model.

# Table of content
- [Dataset and Normalization](https://github.com/KimiyaVahidMotlagh/ANN_manualcoding/blob/main/README.md#dataset-and-normalization) 
- [Forward Phase](https://github.com/KimiyaVahidMotlagh/ANN_manualcoding/blob/main/README.md#forward-phase)
- [Backward Phase](https://github.com/KimiyaVahidMotlagh/ANN_manualcoding/blob/main/README.md#backward-phase)
- [ANN Model Engineenering](https://github.com/KimiyaVahidMotlagh/ANN_manualcoding/blob/main/README.md#ann-model-engineenering)
- [Train and Evaluation](https://github.com/KimiyaVahidMotlagh/ANN_manualcoding/blob/main/README.md#train--evaluation)

# Dataset and normalization
The Dataset we are training our code for is Mnist. We chose the Mnist Dataset for its simplicity. In Mnist we have 80000 images, each has 28*28 resolution. 
Each test data has a label so we could train the model based on the labels and calculate accuracy. We need a vector[10] of the encoded label for each train data.
<picture>
 <source media="(prefers-color-scheme: dark)" srcset="https://github.com/KimiyaVahidMotlagh/ANN_manualcoding/blob/main/Pictures/example-d2cde38dde1627fc776885213fdb7005.png">
 <img alt="Shows an illustrated sun in light color mode and a moon with stars in dark color mode." src="https://github.com/KimiyaVahidMotlagh/ANN_manualcoding/blob/main/Pictures/example-d2cde38dde1627fc776885213fdb7005.png">
</picture>
Image Source Link: https://cleanlab.ai/blog/label-errors-image-datasets/

# Forward Phase
Every ANN model was a weight matrix and bios matrix for each layer. Our calculation also needs an activation function so that we find Nonlinear functions. The sigmoid function is the activation function we used. Each node calculates $W*X+b$ based on the previous layer's data, weights, and bios. 
<br/> <br/>
- W_init(): returns a matrix with a random number in the range of 0 and 1 for initialization.
- b_init(): returns a vector with all zero data for initialization.
- init_matrix(): sets all initializations for our network based on layers.
- sigmoid(): activation function $1/(1+e^x)$
- next_layer_activation_function(): this function calculates the forward phase based on inputs. 
- forward(): all initialization and calculating activations are in this function. The forward function will call previous functions. 
# Backward Phase
Backpropagation is so that the network trains itself and adjusts the weights and bios. This algorithm compares the last layer predictions to our labels. The difference derivatives show how much the weights and bios will change. In each backpropagation, we move toward the minimal cost. The epochs will determine when the training stops. Epochs are the amount of time we repeat the forward and backward phase. 
<br/> <br/>
- sigmoid_derivate(): calculates the sigmoid derivate needed for the backward phase. 
- calculate_layer_dervatives(): calculates bios, weights, and activations derivatives. 
- backpropagation_dev_calculator(): saves and returns the full network derivatives using the previous function.
- backpropagation_grad_calculator(): returns networks' gradient, which shows how much the weight and bios will change in every epoch.
- cost(): calculates the difference in the prediction and the label. 

# ANN Model Engineenering
In engineering an ANN model, we design and set the appropriate architecture. For training a neural network we need both forward and backward phases. Our algorithm is complete in SGD function. 
<br/> <br/>
- SGD(): full network function with epoch and learning rate added to the parameters. This function will train the model and returns weights, bios, and final training cost.
- cal_accuracy(): calculates accuracy based on how many labels were correctly predicted.
- show_result(): shows the final accuracy and plots the cost throw the epochs. With the plot, we can witness the change in cost and model training.

# Train & Evaluation
Our final model has hidden layers with 64 and 16 nodes and a learning rate of 2. This model has 95 percent accuracy without the library optimizers for our Mnist dataset.
