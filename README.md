# Oxford-IIIT-Pet-using-Detectron2
A 37 category pet dataset with roughly 200 images for each class


## Description
The <a href= "https://www.robots.ox.ac.uk/~vgg/data/pets/">Stanford Dogs Dataset</a> We have created a 37 category pet dataset with roughly 200 images for each class. The images have a large variations in scale, pose and lighting. All images have an associated ground truth annotation of breed, head ROI, and pixel level trimap segmentation.

I have used the Dectectron2 , which is pre-trained on the Coco- dataset for classification. Data augementation has been used for making the model generalize better and also to avoid overfitting. The model achieved an accuracy of 90% on validation set, which is decent for this dataset.


### Pre-Requisites
For running the notebook on your local machine, following pre-requisites must be satisfied:
- NumPy
- Pandas
- Scikit-image
- IPython
- Matplotlib
- Tensorflow 2.X
- Keras
- Detectron2
- AZURE Cloud

### Installation
**Dependencies:**
```
# With Tensorflow CPU
git clone <repository name> 
pip install -r requirements.txt
pip install tensorflow-object-detection-api

# With Tensorflow GPU
pip install -r requirements-gpu.txt
```
**Nvidia Driver (For GPU, if you haven't set it up already):**
```
# Ubuntu 20.04
sudo apt-add-repository -r ppa:graphics-drivers/ppa
sudo apt install nvidia-driver-430

# Windows/Other
https://www.nvidia.com/Download/index.aspx
![example images](https://i.imgur.com/Mp2Te2Y.png)

```

## Approach
### Data Augmentation
Data augmentation is done through the following techniques:
- Rescaling (1./255)
- Shear Transformation (0.2)
- Zoom (0.2)
- Horizontal Flipping
- Rotation (20)
- Width Shifting (0.2)
- Height Shifting (0.2)
- 
- ![Capture](https://user-images.githubusercontent.com/61115039/162672456-e9f215e4-4a7e-4bf6-9b07-2c4066427a21.PNG)

### Final Output : Applying different Dectectron2 model for masking the images

#### Using the COCO-Detection - faster_rcnn_R_101_FPN_3x

![final_output_1](https://user-images.githubusercontent.com/61115039/162673147-d288000e-bf52-45e7-a3f5-5442d44ed00f.PNG)

#### Using the COCO-InstanceSegmentation - mask_rcnn_X_101_32x8d_FPN_3x

![panto](https://user-images.githubusercontent.com/61115039/162673227-44b2d313-e759-49e6-a1f2-c0ec46fe5d11.PNG)

#### Using the COCO-PanopticSegmentation - panoptic_fpn_R_101_3x

![coc](https://user-images.githubusercontent.com/61115039/162673328-61b21b21-9dfc-45b5-bc4a-de9f0a5a7c42.PNG)

Final Video :

https://user-images.githubusercontent.com/61115039/162675570-9b675977-49b6-49c0-8dff-9d7875ccbbd3.mp4

