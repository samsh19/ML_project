# ML Project: image segmentation with style transfer

This is the project for NYU intro to ML. The goal of this project is to combine the image segmentation and style transfer techniques to create a partial style transfer image to an specific objective.

Note that the for the segmentation, we only specify one object here. 


All the technique code is based on the pytorch official tutorial document.
>https://pytorch.org/tutorials/intermediate/torchvision_tutorial.html<br>
>https://pytorch.org/tutorials/advanced/neural_style_tutorial.html<br>

This repository didn't change much on the original code but provide the new displayment of the image outcome.

### Image segmentation (Instant segmentation):
For the image segmentation, the Mask RCNN is been adapted here. The Mask RCNN is envolve from the Faster RCNN (RCNN -> Fast RCNN -> Faster RCNN -> Mask RCNN). Due to the one object detection scenario, I fine tune the orginal model with 2 classes (object and background). Although the original model code is powerful, one thing that needed to modify but I didn't done is encountering the multiple target in one image. In this case, the model will only segment one of the objective in multiple targets. For example, for the family photo, the segmentation will only separate the "Mom" object and regard all the other as background.

### Style transfer:
For the style transfer, the orginal version of style transfer has been used in here (provided by Leon A. Gatys, Alexander S. Ecker and Matthias Bethge). Instead of the style transfer, I personally think that it is more closely to the image synthesis. The model tunning the VGG16 and adding 2 different kind of loss function, content loss function and style loss function, then processed the optimization (gradient) with the content image and the style image. Note that the technique has the improved version from Perceptual Losses for Real-Time Style Transfer and Super-Resolution (https://arxiv.org/pdf/1603.08155.pdf).

### Result:
<p align = 'center'>
<img src = 'compare_images/polor_bear_japan_paint_wave_compare.png'>
</p>
<p align = 'center'>
From the left to right, the content image, style image, style transferred image, segmentation of the content image, and the outcome
</p>

<!-- ### Experinment: -->
