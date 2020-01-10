# CSE 676: Deep Learning

## Project 1 Description for Fall 2019

### Intoduction

This project is about learning a generative model from which samples can be generated. In this project you will implement two types of Generative Adversarial Networks (GANs): One known as the Deep Convolution GAN (**DCGAN**); the other known as Self-Attention GAN (**SA-GAN**) using **CIFAR-10 dataset**. Basic DCGAN consists of two neural networks: a discriminator (D) and a generator (G) which compete with each other making each other stronger at the same time. One of the simple variants of GAN in Deep Convolutional GANs (DCGANs) in which G and D are both based on deep convolution neural network. 

DCGANs exhibit limitations while modelling long term dependencies for image generation tasks. For example, dogs are often drawn with realistic fur texture but without clearly defined separate feet. The problem with DCGANs exists because model relies heavily on convolution to model the dependencies across different image regions. Since convolution operator has a local receptive field, long ranged dependencies can only be processed after passing through several convolutional layers. This could prevent learning about long-term dependencies for a variety of reasons: 

1. A small model may not be able to represent them 
2. Increasing the size of the convolution kernels can increase the representational capacity of the network but doing so also loses the computational and statistical efficiency obtained by using local convolutional structure 
3. Mode collapse 

To mitigate first two issues self-attention module is introduced in DCGANs. SA, exhibits a better balance between the ability to model long-range dependencies and the computational and statistical efficiency. 

To alleviate the third issue, GANs are trained with Wasserstein Loss. The Wasserstein distance is the minimum cost of transporting mass in converting the data distribution q to the data distribu- tion p. Even when two distributions are located in lower dimensional manifolds without overlaps, Wasserstein distance can still provide a meaningful and smooth representation of the distance in- between. The Equation for Wasserstein distance is given as follows: 

L(pr,pg) = W(pr,pg) = maxEx∼pr[fw(x)]−Ez∼pr(z)[fw(gθ(z))] (1) w∈W 

In this project, students will use Wasserstein Loss while implementing a Self-Attention Gener- ative Adversarial Network (SAGAN). 



### Project Requirements
 GAN Model, Attention Implementation, Evaluation Metrics 

ImplementamodelcombiningaconditionalGenerator(G)andDiscriminator(D)usingyour own code. 

Apply Spectral Normalization (SN) on G and D. Existing implementations for SN can be used. 

Implement self-attention (SA) module using your own code. 

Implement Wasserstein Loss function for the training using your own code. 

Apply FID as an evaluation metric. Existing implementations for FID can be used. 

It is expected that students validate the training epochs using Fre ́chet Inception Distance (FID) with a validation set. Existing implementations can be used 

Compute the FID score during training at least at every 1000 iterations and plot it
 A jupyter notebook containing the complete code.
 The jupyter notebook should have an ultimate cell which when run executes and generates form the best generator model obtained while training. 

(a) 8 by 8 image grid
(b) FID score. CIFAR10 test data should be used wile calculating FID 

Optional Step: It is recommended to use the two-timescale learning rates update rule (TTUR) implemented in the SA-GANs paper in order for the GAN to converge to a local Nash equilibrium. Guidelines for Using 3rd Party Code: In general third party code can only be used when imported from the deep learning API of the student’s choice. Any other outside code used must only be “snippets” and must be cited. Students cannot share code between groups under any circumstances. 

