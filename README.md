# Flood style transfer

#### A project by Jeremy Diaz (https://github.com/jdiaz4302) and Kristin Robinson (https://github.com/CUKrob)
##### Final project for INFO 4604/5604 - Applied Machine Learning

## Background

Artistic style transfer is a recent method for applying artistic styles to everyday pictures, such as making a photograph look like it was painted by Vincent van Gogh (**Figure 1C**). A foundational paper in this field and the approach which this project is based off is ["A Neural Algorithm of Artistic Style"](https://arxiv.org/abs/1508.06576) by Leon A. Gatys, Alexander S. Ecker, and Matthias Bethge. <br>

![Example of artistic style transfer](https://raw.githubusercontent.com/jdiaz4302/flood_style_transfer/master/README_images/example_picture.png)

## Our goal

The goal of this project is to see if natural disasters (such as fires and floods) can be effectively used as artistic styles. That is, can we **visually predict what a natural disaster may look like**?<br>

## Methods

We gathered before and after images for 28 flooded locations. One image was used as a "style" image (representing a typical flood) (**Figure 2**) to apply to other location's before images. We generated output images which serve as compromises between before-image content and style-image style, and then compared these output images (via the same unweighted loss functions) to the true after images.<br>

![Flood style image](https://raw.githubusercontent.com/jdiaz4302/flood_style_transfer/master/README_images/flood_style.jpg)

Artistic style transfer utilizes a pretrained convolutional neural network, therefore there is no "training"; parameters are not tuned, only hyperparameters (such as loss function tradeoff and neural style depth) are. We found the hyperparameter combinations which minimize the loss/error between output images and 20 post-fire images, then used this combination to evaluate performance on 7 test set images. The model-generated outputs of which are below.


<img src="https://raw.githubusercontent.com/jdiaz4302/flood_style_transfer/master/README_images/21_content.jpg" height="250" width="250"><img src="https://raw.githubusercontent.com/jdiaz4302/flood_style_transfer/master/README_images/21_style.jpg" height="250" width="250"><img src="https://raw.githubusercontent.com/jdiaz4302/flood_style_transfer/master/README_images/output21.png" height="250" width="250">

<img src="https://raw.githubusercontent.com/jdiaz4302/flood_style_transfer/master/README_images/22_content.jpg" height="250" width="250"><img src="https://raw.githubusercontent.com/jdiaz4302/flood_style_transfer/master/README_images/22_style.jpg" height="250" width="250"><img src="https://raw.githubusercontent.com/jdiaz4302/flood_style_transfer/master/README_images/output22.png" height="250" width="250">

<img src="https://raw.githubusercontent.com/jdiaz4302/flood_style_transfer/master/README_images/23_content.jpg" height="250" width="250"><img src="https://raw.githubusercontent.com/jdiaz4302/flood_style_transfer/master/README_images/23_style.jpg" height="250" width="250"><img src="https://raw.githubusercontent.com/jdiaz4302/flood_style_transfer/master/README_images/output23.png" height="250" width="250">

<img src="https://raw.githubusercontent.com/jdiaz4302/flood_style_transfer/master/README_images/24_content.jpg" height="250" width="250"><img src="https://raw.githubusercontent.com/jdiaz4302/flood_style_transfer/master/README_images/24_style.jpg" height="250" width="250"><img src="https://raw.githubusercontent.com/jdiaz4302/flood_style_transfer/master/README_images/output24.png" height="250" width="250">

<img src="https://raw.githubusercontent.com/jdiaz4302/flood_style_transfer/master/README_images/25_content.jpg" height="250" width="250"><img src="https://raw.githubusercontent.com/jdiaz4302/flood_style_transfer/master/README_images/25_style.jpg" height="250" width="250"><img src="https://raw.githubusercontent.com/jdiaz4302/flood_style_transfer/master/README_images/output25.png" height="250" width="250">

<img src="https://raw.githubusercontent.com/jdiaz4302/flood_style_transfer/master/README_images/26_content.jpg" height="250" width="250"><img src="https://raw.githubusercontent.com/jdiaz4302/flood_style_transfer/master/README_images/26_style.jpg" height="250" width="250"><img src="https://raw.githubusercontent.com/jdiaz4302/flood_style_transfer/master/README_images/output26.png" height="250" width="250">

<img src="https://raw.githubusercontent.com/jdiaz4302/flood_style_transfer/master/README_images/27_content.jpg" height="250" width="250"><img src="https://raw.githubusercontent.com/jdiaz4302/flood_style_transfer/master/README_images/27_style.jpg" height="250" width="250">
<img src="https://raw.githubusercontent.com/jdiaz4302/flood_style_transfer/master/README_images/output27.png" height="250" width="250">
## Evaluation

Overall the results are pretty impressive! Notably, however, the model will not "add water". Our model primarily gives the scenes a muddy and eroded appearance, suggesting that we are more reasonably predicting the aftermath (rather than the presence) of a flood. Due to this, the predictions are less impression on locations which lack abundant plant life.<br><br>

## Acknowledgements

This project was competed using the PyTorch (http://pytorch.org/) deep learning framework and was inspired by the above-mentioned arxiv paper. Our neural style tranfer code was immensely helped by the following documentation: http://pytorch.org/tutorials/advanced/neural_style_tutorial.html
