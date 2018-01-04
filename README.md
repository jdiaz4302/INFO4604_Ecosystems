# Flood style transfer

#### A project by Jeremy Diaz (https://github.com/jdiaz4302) and Kristin Robinson (https://github.com/CUKrob)
##### Final project for INFO 4604/5604 - Applied Machine Learning

## Background

Artistic style transfer is a recent method for applying artistic styles to everyday pictures, such as making a photograph look like it was painted by Vincent van Gogh (**Figure 1**). A foundational paper in this field and the approach which this project is based off is ["A Neural Algorithm of Artistic Style"](https://arxiv.org/abs/1508.06576) by Leon A. Gatys, Alexander S. Ecker, and Matthias Bethge. <br>

## Our goal

The goal of this project is to see if natural disasters (such as fires and floods) can be effectively used as artistic styles. That is, can we **visually predict what a natural disaster may look like**?<br>

## Methods

We gathered before and after images for 28 flooded locations. One image was used as a "style" image (representing a typical flood) (**Figure 2**) to apply to other location's before images. We generated output images which serve as compromises between before-image content and style-image style, and then compared these output images (via the same unweighted loss functions) to the true after images.<br>

Artistic style transfer utilizes a pretrained convolutional neural network, therefore there is no "training"; parameters are not tuned, only hyperparameters (such as loss function tradeoff and neural style depth) are. We found the hyperparameter combinations which minimize the loss/error between output images and 20 post-fire images, then used this combination to evaluate performance on 7 test set images. The outputs of which are below.
