# Colorization with CIFAR 10 

This task is based on Autoencoder model. Which is consisted of an encoder and a decoder. The dataloader is self-defined in order to load the grayscale images and their original images. Each record is made up of a grayscale image and original image pair. The neural network takes in a grayscale image as input and then output a colorized one. 

The input grayscale image also has 3 channels but with exactly the same value for each pixel. Actually, this is not so meaningful afterwards, it can still be modified to be a one-dimensional input.

## U-Net

The network is based on the frame of U-Net. It is connected on the convolutional layers and deconvolutional layers. This ensures that the information will not miss too much after down-sampling and up-sampling. 
