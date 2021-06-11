# secle
## General Description
CycleGAN model has been one of the most widely used ma-chine learning model in the ML/DL field.   However,  it hascertain limitations and would fail some of the cases.  There-fore,  in this paper,  we would like to fix the original limita-tions that CycleGAN has. Thus we propose an upgrade basedon the original CycleGAN model by adding one more seg-mentation layer right before the CycleGAN layer, which wename our method as SecleGAN model. Our model could per-fectly solve the problem that original CycleGAN mistreatedthe part of background as the target as well and transform thebackground into other domains.  In the end,  our SecleGANmodel is able to only transform the real target yet remains thebackground information as much as possible.  Therefore, weconsider our model as an improvement of the original Cycle-GAN
 

## Usage

The project is divided in to three major parts.
1. U-net (Segmentation)
2. Cycle GAN
3. Reconstruction

There are three folders that need to be run sequentially. 

First, the U-net and Cycle GAN model are trained separately. U-net are trained with images and masks of all the classes, which are all the birds class in this case. 

Second, the Cycle GAN model are trained with the two target classes, which are the red and blue birds that we chose.

Lastly, the reconstruction stage takes the two trained model, which need to manually moved to the reconstructed folder, to generate the Secle GAN result. The original image is first run through the Cycle GAN model, which gives out the transformed image. Then the original image is run through U-net, which would return a predicted mask. Then, we use the predicted mask to combine the original image with the transformed images. 

## Customed Usage
 The result can be replicated with customed dataset. In our Secle GANv1 model, the experimental dataset was not birds, but butterflies. To replicate the project, simply replace the birds image and masks with custom images and mask. Then, the models need to be re-trained, but the reconstruction part, which is the core of Secle GAN can be remain unchanged. 


## Referances
1. [Cycle GAN](https://machinelearningmastery.com/cyclegan-tutorial-with-keras/)
2. [U-net](https://github.com/zhixuhao/unet)
