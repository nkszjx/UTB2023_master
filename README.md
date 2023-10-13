# The Urban Tree Canopy Cover in Brazil


To better service Brazil’s urban ecosystem, we developed a semi-supervised deep learning method, which is able to learn semantic segmentation knowledge from both labeled and unlabeled images, to segment urban trees from high spatial resolution remote sensing images. The approach attains significant improvement over existing methods, especially when trained with limited labeled samples. Using this approach, we created 0.5 m fine-scale tree canopy products for 472 cities in Brazil and made them freely available to the community ([UTB dataset1](https://nkszjx.github.io/projects/UTB.html)). 
![](/figure/TreeSeg_Network.png)

In this study, we used the same semi-supervised learning framework (a) to train two CNN models for urban tree and mask segmentation, respectively. 
We use [Deeplabv3+](https://github.com/VainF/DeepLabV3Plus-Pytorch) (Chen et al., 2018) as our segmentation network (b). 
A standard binary classification network was designed as the discriminator (c) in this semi-supervised adversarial learning framework.

## Results
### Tree segmentation results
![](/figure/tree.png)

### Urban tree canopy cover in Brazil
![](/figure/Graphical.png)

## Package pre-requisites
The code runs on Python 3 and Pytorch 0.4 The following packages are required. 

```
pip install scipy tqdm matplotlib numpy opencv-python
```

## Training preparation

Download ImageNet pretrained Resnet-101([Link](https://download.pytorch.org/models/resnet101-5d3b4d8f.pth)) and place it ```./pretrained_models/```

### Training semi-supervised Learing Framework(SSL)
```
python train.py   
```
or
```
nohup python -u train.py > ./log/out_list.log 2>&1 &
``` 
### Validation 
```
python evaluate.py
```

## Acknowledgement

Parts of the code have been adapted from: 
[DeepLab-Resnet-Pytorch](https://github.com/speedinghzl/Pytorch-Deeplab), [AdvSemiSeg](https://github.com/hfslyc/AdvSemiSeg), [PyTorch-Encoding](https://github.com/zhanghang1989/PyTorch-Encoding)


```

