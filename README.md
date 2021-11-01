# custom-object-detection
localize and classifies persons and cars in the given image

## About the Model

YOLOv5 is the state-of-the-art object detection model pre-trained on MS COCO. Yolov5 implementation has been done in PyTorch. It is easier to understand, training and deployment using the PyTorch ecosystem. YOLOv5 is faster and accurate. The release of YOLOv5 includes different model sizes YOLOv5s(smallest), YOLOv5m, YOLOv5l, YOLOv5x(largest). 
* I have used the YOLOv5(m) model for the given task

## Primary Analysis:

Total number of Images: 2239

The dataset contains imbalanced occurrences of object types, the person class have more instances than the car. It leads to poor model performance (less Average Precisions).

Number of instances for each category
<br>person -  12348
<br>car    -   4424

<p align="center">
  <img src="https://github.com/saikumarmalla/custom-object-detection/blob/main/screenshots/data.png" width="200" title="plot">

</p>


![alt text](https://github.com/saikumarmalla/custom-object-detection/blob/main/screenshots/data.png)
