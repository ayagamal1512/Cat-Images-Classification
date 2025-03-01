# Cats Image Classification

Our initial model is build from scrach using numpy and the model architecture was made of just 2 hidden layers with input of 209 training examples and the compiled sequence
- Parameters initialization
- Forward propagation
- Cost calculations
- Backward propagation
- Logistic regression model building
- Predictions
and with these 2 hidden layers I managed to achive **80% test accuracy**, which is good but we can do better!
The cahllengs were:
- very small training examples and there is not enough examples for the model to learn
- Building a deeper neural network will cause the problem of over fitting because the data is not large enough
-  Vanshing gradient and the loss function wont converge to the optimal minima due to the increase of number of layers
-  High computational cost due to the increase of the number of learning weights 
- Learning rate optimization

So, we turned to using **Convolution Neural Network** using TensorFlow added 2 conv layer -> 2 MaxPoolin - 2 DropOut-> 2 dense layer and it gave a **better test accuracy 86%**, however we still can do better! 
There are pretrained models such as ResNet50 and Mobile-Net where we can make use of `Transfer Learning` in our case where we have a small number of training examples. 

![ResNet Architecture](https://github.com/ayagamal1512/Cat-Images-Classification/blob/main/ResNet.PNG)
