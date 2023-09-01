# Face-Generator using VAE with Simpsons' Faces

## Variational Autoencoder (VAE)

VAE is a method that combines the advantages of Bayes Method and Deep Learning. VAEs are appealing because they are built on top of standard function approximators (neural networks), and can be trained with stochastic gradient descent. VAEs have already shown promise in generating many kinds of complicated data, including handwritten digits, faces, house numbers, CIFAR images, physical models of scenes, segmentation, and predicting the future from static images. [1]

In this project, VAE is used to generate Simpsons' faces. Similar to Autoencoder, VAE only show the difference in the latent process. Precisely, VAE will add some noise to the latent, so that the output will be slightly different from the input. However, if the VAE is not well-trained, the images will be blury. This is a drawback of using too much deconvolution that causes the reduction of sharpness.

## Reference
[1] [Tutorial on Variational Autoencoders](https://doi.org/10.48550/arXiv.1606.05908)
