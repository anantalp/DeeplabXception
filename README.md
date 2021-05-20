## *Encoder-Decoder with Atrous Separable Convolution for Semantic Image Segmentation*

### Introduction: 
This is a re-implementation of [DeepLab-V3-Plus](https://arxiv.org/pdf/1802.02611). It can use Modified Aligned Xception and ResNet as backbone. Currently, we utilizeDeepLab V3 Plus using Pascal VOC 2012, SBD and Cityscapes datasets.

### Abstract:
Spatial pyramid pooling module or encoder-decoder structure are used in deep neural networks for semantic segmentation task. The former networks are able to encode
multi-scale contextual information by probing the incoming features with filters or pooling operations at multiple rates and multiple effective fields-of-view, while the latter networks
can capture sharper object boundaries by gradually recovering the spatial information. In this paper, the authors propose to combine the advantages of both methods. Specifically,
the proposed model, DeepLabv3+, extends DeepLabv3 by adding a simple yet effective decoder module to refine the segmentation results, especially along object boundaries.
they further explore the Xception model and apply the depthwise separable convolutionto both Atrous Spatial Pyramid Pooling and decoder modules, resulting in a faster and
stronger encoder-decoder network.

### Illustration:
1. Network Overview for Deeplabv3+:
<img src="https://github.com/anantalp/DeeplabXception/blob/main/figures/fig1.PNG">

2. Encoder-Decoder with Atrous Separable Convolution for Deeplabv3+:
<img src="https://github.com/anantalp/DeeplabXception/blob/main/figures/fig2.PNG">

### Visualization:
<img src="https://github.com/anantalp/DeeplabXception/blob/main/figures/fig3.PNG">

### Results
| Backbone  | train/eval os  |mIoU in val |
| :-------- | :------------: |:---------: |
| ResNet    | 16/16          | 78.43%     | 
| MobileNet | 16/16          | 70.81%     | 
| DRN       | 16/16          | 78.87%     | 

### Training
Follow steps below to train your model:

1. Configure your dataset path in [mypath.py](https://github.com/anantalp/DeeplabXception/blob/main/mypath.py).

2. Input argument:
    ```Shell
    train.py (see full input arguments via python train.py --help)
    ```

3. To train deeplabv3+ using Pascal VOC dataset and ResNet as backbone:
    ```Shell
    bash train_voc.sh
    ```
4. To train deeplabv3+ using COCO dataset and ResNet as backbone:
    ```Shell
    bash train_coco.sh
    ```    


