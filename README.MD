# MaskRCNN on Nucleus dataset.

MaskRcnn, is a segmentation algorithm(object detection).It performs better than FastRCNN and FasterRCNN and can be called a extension of these with extra branch.

## Description

LIBRARY USED:		https://github.com/matterport/Mask_RCNN		
Provides Configuration class which can be easily extended to make separate
classes for training mode and inference mode.
Easy mapper for dataset and operability with functions like prepare.

PAPER REFERED TO:	https://arxiv.org/pdf/1703.06870.pdf

BACKBONE USED:		Resnet101
As mentioned in the original paper Resnet101 leads to better mAP values 
55.2 for resnet50-FPN and 57.3 for Resnet-101-FPN.
Mask R-CNN using ResNet-101-FPN outperforms the base variants of all 
previous state-of-the-art  models,  including  the  single-model  variant  
of  G-RMI, the winner of the COCO 2016 Detection Challenge.

COCO weights are used as initialization. COCO contains lesser classes than IMAGENET,
nucleus data is relatively simple and targets only two classes.

Backbone is frozen and top(head) is trained, fine tuning is prefered but not implemented
or required in a simple use case as input distribution is mostly round nucleuses on a background. On the other hand.

After 1/1 epoch with 200 steps model showed decent results.

What more could be done?
As mentioned in the paper using Imagenet will have better results, especially on complicated dataset with more classes.
Region Proposal Network can be tweaked.
Fine tuning could be applied and 
epochs can be increased to perform better on training data and remove bias.

All this might increase computation cost.

## Getting Started


maskRCNN_nucleus.ipynb  :	Self sufficent ipynb made in Google COLAB. 
				It downloads and installs MRCNN library	and guides through training and detection.
				It also plots the mAP Precision and recall curve.
				Dataset is downoaded in colab via drive link, provide your own(zip).Follow the same structure
				as the nuclei_dataset folder. You can zip nuclei_datasets folder and upload to drive.


