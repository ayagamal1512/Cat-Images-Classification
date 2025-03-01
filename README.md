# Cats Image Classification

Our initial model is built from scratch using numpy and the model architecture was made of just 2 hidden layers with input of 209 training examples and the compiled sequence
- Parameters initialization
- Forward propagation
- Cost calculations
- Backward propagation
- Logistic regression model building
- Predictions

and with these 2 hidden layers we managed to achive **80% test accuracy**, which is good but we can do better!
The cahllengs were:
- very small training examples and there is not enough examples for the model to learn
- Building a deeper neural network will cause the problem of over fitting because the data is not large enough
-  Vanshing gradient and the loss function wont converge to the optimal minima due to the increase of number of layers
-  High computational cost due to the increase of the number of learning weights 
- Learning rate optimization

So, we turned to using **Convolution Neural Network** using TensorFlow added 2 conv layer -> 2 MaxPoolin - 2 DropOut-> 2 dense layer and it gave a **better test accuracy 86%**, however we still can do better! 
There are pretrained models such as ResNet50 and Mobile-Net where we can make use of `Transfer Learning` in our case where we have a small number of training examples. 

![ResNet Architecture](https://github.com/ayagamal1512/Cat-Images-Classification/blob/main/ResNet.PNG)

Let's see how Res-Net50 overcome those challenges:
1. very small training examples--> Data Augumentation + using a pretrained model, It has been trained on the ImageNet dataset which contains over **14 million images and 1000 classes**.
2. Over fitting --> Adding regularization term `l2` large enough + adding BatchNormalization to ResNet+ Dropout 60% of the layers
3. Vanshing gradient --> Utilizing the `Residual Network` that skips connection to add the input to the output avoiding information loss due to deep layers
4. High computational cost --> The convolution block in the ResNet resolve this issue using 1x1 convolution which reduce the dimensionality of the input data to match the output and reduce the number of trained parameters 
5. Learning rate optimization --> By using the ADAM Optimization technique to automatically update the learning rate and make it more steady instead of overshooting

In addition, as we can see the ResNet Architecture is composed of 2 blocks (Identity Block and Convolution Block)
- The identity block passes the input through a series of convolutional layers and adds the input back to the output, while the convolutional block uses a 1x1 convolutional layer to reduce the number of filters before the 3x3 convolutional layer and then adds the input back to the output.
- Identity Block --> Helps learning more complex features while mantaining the same spatial dimensions.

