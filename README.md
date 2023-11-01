# Brain Tumor Segmentation

Implementation of UNet architecture to segment brain tumor masks


I picked up this fun project on Kaggle
Dataset: https://www.kaggle.com/datasets/mateuszbuda/lgg-mri-segmentation
UNet is based on the paper: https://arxiv.org/abs/1505.04597 

# U Net 
![Illustration-of-the-U-net-architecture-The-figure-illustrates-the-U-net-architecture 1](https://github.com/hjoshi95/Brain-tumor-Segmentation-UNET/assets/144065828/31f0936b-b9eb-4452-9894-b3883e622592)

# Idea

The network architecture is a U-shaped encoder-decoder architecture. The encoder basically extracts high level features but loses spatial information and the decoder 
basically gains spatial information but takes a hit on the feature activations. The skip connections between the corresponding encoded and decoded layers make sure to counteract the
limitations of the lost spatial information as well as the lost feature activations hence using best of both worlds for its learning.

One could even make UNets more robust by adding Attention Gates to decoders and skip connections


# Architecture

1. Encoder Path:
Encoder captures the context of the input image through a series of Conv-ReLu-Pool operations.

2. Bottleneck:
The bottleneck bridge comprises of high level features with an increased receptive field thus allowing for discriminative features incorporating image context. All image info is
compressed in a low dimensional space. This aids the network in being parameter efficient. Its an essential middleman to preserve spatial information and context

4. Decoder:
Aims to localize and segment the regions of interest. It uses upsampled convolutions to increase the spatial resolution.
Skip connections from the encoder path are concatenated to preserve high-resolution features.








