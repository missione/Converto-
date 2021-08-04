# Converto
## Hand Writing Recognition Using Convolution Neural Network 

This notebook is the implementation of Machine Learning model to classify writers based on their handwritings . Dataset used is IAM top 50 Dataset (where only 50 handwriting styles are considered).Here is the [Link](https://drive.google.com/drive/folders/1L7VNbUVmzFAq2HtNt31RwW_OosYjubHQ?usp=sharing) for the dataset .

I have built this model using Keras and Tensorflow . It is language independent as we are not considering letters in the classification , but patches of image 113X113 pixels are extracted from data and fit into the model for learning .

### About Model :

Optimizer : Adam 

Convolution Layers : 3 

Pooling: Max Pooling 

Activation Functions Used : relu , softmax

_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
zero_padding2d_1 (ZeroPaddin (None, 115, 115, 1)       0         
_________________________________________________________________
lambda_1 (Lambda)            (None, 56, 56, 1)         0         
_________________________________________________________________
conv1 (Conv2D)               (None, 28, 28, 32)        832       
_________________________________________________________________
activation_1 (Activation)    (None, 28, 28, 32)        0         
_________________________________________________________________
pool1 (MaxPooling2D)         (None, 14, 14, 32)        0         
_________________________________________________________________
conv2 (Conv2D)               (None, 14, 14, 64)        18496     
_________________________________________________________________
activation_2 (Activation)    (None, 14, 14, 64)        0         
_________________________________________________________________
pool2 (MaxPooling2D)         (None, 7, 7, 64)          0         
_________________________________________________________________
conv3 (Conv2D)               (None, 7, 7, 128)         73856     
_________________________________________________________________
activation_3 (Activation)    (None, 7, 7, 128)         0         
_________________________________________________________________
pool3 (MaxPooling2D)         (None, 3, 3, 128)         0         
_________________________________________________________________
flatten_1 (Flatten)          (None, 1152)              0         
_________________________________________________________________
dropout_1 (Dropout)          (None, 1152)              0         
_________________________________________________________________
dense1 (Dense)               (None, 512)               590336    
_________________________________________________________________
activation_4 (Activation)    (None, 512)               0         
_________________________________________________________________
dropout_2 (Dropout)          (None, 512)               0         
_________________________________________________________________
dense2 (Dense)               (None, 256)               131328    
_________________________________________________________________
activation_5 (Activation)    (None, 256)               0         
_________________________________________________________________
dropout_3 (Dropout)          (None, 256)               0         
_________________________________________________________________
output (Dense)               (None, 50)                12850     
_________________________________________________________________
activation_6 (Activation)    (None, 50)                0         
=================================================================
Total params: 827,698
Trainable params: 827,698
Non-trainable params: 0


This model gives 81% accuracy on test data for 9 epochs.
