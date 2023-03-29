# Vanilla_GAN - PyTorch Implementation
<img src="https://user-images.githubusercontent.com/50144683/228511407-72eafe5e-106d-4be5-8c45-9054a285c5d8.gif" width=45% height=35%></br>
**Picture:** _These numbers were produced by our generator that allows control over different aspects of the image._

This repository contains the Pytorch implementation of the following paper:
>**Generative Adversarial Networks**</br>
>Ian J. Goodfellow, Jean Pouget-Abadie, Mehdi Mirza, Bing Xu, David Warde-Farley, Sherjil Ozair, Aaron Courville, Yoshua Bengio
>https://arxiv.org/abs/1406.2661
>
>**Abstract:** _We propose a new framework for estimating generative models via an adversarial process, in which we simultaneously train two models: a generative model G
that captures the data distribution, and a discriminative model D that estimates the probability that a sample came from the training data rather than G. The training procedure for G is to maximize the probability of D making a mistake. This framework corresponds to a minimax two-player game. In the space of arbitrary functions G and D, a unique solution exists, with G recovering the training data distribution and D equal to 1/2 everywhere. In the case where G and D are defined by multilayer perceptrons, the entire system can be trained with backpropagation. There is no need for any Markov chains or unrolled approximate inference networks during either training or generation of samples. Experiments demonstrate the potential of the framework through qualitative and quantitative evaluation of the generated samples._

## GAN Loss and Training
The training of the Generator(G) and Discriminator(D) networks is based on the following MiniMax game played between the two.</br>
<img src="https://user-images.githubusercontent.com/50144683/228524056-daa3a7f8-ebcf-46e6-a562-2c33627669d6.png" width=65%>

The training algorithm is described in the paper as below :</br>
<img src="https://user-images.githubusercontent.com/50144683/228524568-12035248-41fd-491d-bc7c-d51d5573cf00.png" width=65%>

Binary Cross Entropy loss was used to train both generator and discriminator. Generator was trained my maximising discriminators probability of being real on fake data instead of other way round, because as mentioned in the paper, it provides stronger gradients early.</br>
<img src="https://user-images.githubusercontent.com/50144683/228525406-e0faaa16-3aa7-405c-82e3-0285044a4137.png" width=45%>
