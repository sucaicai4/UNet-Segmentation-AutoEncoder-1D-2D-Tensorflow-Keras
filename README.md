# UNet-Segmentation-Model-Builder-Tensorflow-Keras
This repository contains 1D and 2D Signal Segmentation Model Builder for UNet and several of its variants developed in KERAS-Tensorflow. The code supports Deep Supervision, Autoencoder mode and other options explained in the DEMO. The segmentation models can be used for binary or multiclass segmentation, or for regression tasks.  

## Models supported
1. **UNet** [1]
2. **UNet Ensembled (UNetE)** [2]
3. **UNet+ (UNetP)** [2]
3. **UNet++ (UNetPP)** [3]
5. **MultiResUNet** [4]

## UNet to UNet++
![UNet Architectures](https://github.com/Sakib1263/UNet2D-Segmentation-Model-Builder-KERAS/blob/main/Documents/Images/UNet.jpg "UNet Models")   

## MultiResUNet
Yet another variant is the MultiResUNet architecture as shown above. It has an interesting Residual path for the skip connection and uses MultiRes Blocks instead of normal UNet blocks for deep learning. MultiResUNet model also uses Transposed Convolutions in the encoder by default instead of UpSampling.  
![MultiResUNet Architecture](https://github.com/Sakib1263/UNet-2D-Segmentation-AutoEncoder-Model-Builder-KERAS/blob/main/Documents/Images/MultiResUNet.png "MultiResUNet Model")  
Internal structure for the MultiResUNet block is shown below [4]. As it can be seen, the MultiRes Block goes through convolutions of different Kernel sizes, then concatenates in the end (somewhat similar to Inception_v1 Block idea).  
![MultiResUNet Block](https://github.com/Sakib1263/UNet-Segmentation-AutoEncoder-1D-2D-Tensorflow-Keras/blob/main/Documents/Images/MultiRes%20Block.jpg "MultiResUNet Block")  
Structure for the Residual Path (or ResPath) is shown below [4]. The Residual Path has multiple covolutions and additions to skip conncetions in place of UNet's direct skip connection.  
![Residual Path](https://github.com/Sakib1263/UNet-Segmentation-AutoEncoder-1D-2D-Tensorflow-Keras/blob/main/Documents/Images/Residual_Path.jpg "Residual Path")  

## Supported Features
The speciality about this model is its flexibility, such as:
1. The user can choose any of the 5 available UNet variants for either 1D or 2D Segmentation tasks.
2. The models can be used for Binary or Multi-Class Classification, or Regression type Segmentation tasks.
3. The models allow Deep Supervision [5] with flexibility during Segmentation.
4. The segmentation models can also be used as Autoencoders [6] for Feature Extraction.
5. The depth of all the models can be varied to form very shallow to very deep networks.
6. Number of input kernel/filter, commonly known as Width of the model can be varied.
7. Number of classes for Classification tasks and number of extracted features for Regression tasks can be varied.
8. Number of Channels in the Input Dataset can be varied.  
9. In case of only MultiResUNet, its 'alpha' parameter can be varied (default set to 1.0) [4].  

Version 2 of all the networks (e.g., UNet_v2) uses Transposed Convolution [7] instead of UpSampling in the Decoder section.  
![Transposed Convolutions](https://github.com/Sakib1263/UNet-Segmentation-AutoEncoder-1D-2D-Tensorflow-Keras/blob/main/Documents/Images/Transposed_Convolution.png "Transposed Convolutions") 

Details of the process are available in the DEMO provided in the codes section. The datasets used in the DEMO as also available in the 'Documents' folder. **[The DEMO will be added soon for 1D and 2D]**

## References  
**[1]** Ronneberger, O., Fischer, P., & Brox, T. (2021). U-Net: Convolutional Networks for Biomedical Image Segmentation. arXiv.org. Retrieved 30 August 2021, from https://arxiv.org/abs/1505.04597.  
**[2]** Zhou, Z., Siddiquee, M., Tajbakhsh, N., & Liang, J. (2021). UNet++: Redesigning Skip Connections to Exploit Multiscale Features in Image Segmentation. Arxiv-vanity.com. Retrieved 30 August 2021, from https://www.arxiv-vanity.com/papers/1912.05074/.  
**[3]**  Zhou, Z., Siddiquee, M., Tajbakhsh, N., & Liang, J. (2021). UNet++: A Nested U-Net Architecture for Medical Image Segmentation. arXiv.org. Retrieved 30 August 2021, from https://arxiv.org/abs/1807.10165.  
**[4]** Ibtehaz, Nabil, and M. Sohel Rahman. “Multiresunet : Rethinking the u-Net Architecture for Multimodal Biomedical Image Segmentation.” ArXiv.org, 11 Feb. 2019, arxiv.org/abs/1902.04049v1.  
**[5]** Wang, L., Lee, C., Tu, Z., & Lazebnik, S. (2021). Training Deeper Convolutional Networks with Deep Supervision. arXiv.org. Retrieved 30 August 2021, from https://arxiv.org/abs/1505.02496.  
**[6]** Chang, H. (2021). A Method of Brain Image Optimization based on an Autoencoder Unet. Journal Of Physics: Conference Series, 1952(2), 022064. https://doi.org/10.1088/1742-6596/1952/2/022064  
**[7]** Transposed Convolution Demystified. Medium. (2021). Retrieved 1 September 2021, from https://towardsdatascience.com/transposed-convolution-demystified-84ca81b4baba.  
