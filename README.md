# custom-object-detection
localize and classifies persons and cars in the given image

## About the Model

YOLOv5 is the state-of-the-art object detection model pre-trained on MS COCO. Yolov5 implementation has been done in PyTorch. It is easier to understand, training and deployment using the PyTorch ecosystem. YOLOv5 is faster and accurate. The release of YOLOv5 includes different model sizes YOLOv5s(smallest), YOLOv5m, YOLOv5l, YOLOv5x(largest). 
* I have used the YOLOv5(m) model for the given task

## Primary Analysis(Dataset):

Total number of Images: 2239

The dataset contains imbalanced occurrences of object types, the person class have more instances than the car. It leads to poor model performance (less Average Precisions).

Number of instances for each category
<br>person -  12348
<br>car    -   4424

<p align="center">
  <img src="https://github.com/saikumarmalla/custom-object-detection/blob/main/screenshots/data.png" width="300" title="classwise instances">
</p>

## Training:
Converted the given annotation COCO JSON file into YOLOv5 PyTorch TXT format. I have done two experiments of training.

Experiment 1:
Trained the YOLOv5m model with original (Unbalanced) dataset provided. <br>
Dataset link: [Dataset 1](https://drive.google.com/drive/folders/1h3Sp2UufIY_bDePTHPNjSWav8t2wMdH-?usp=sharing)

Experiment 2:
Adjusted class representations in the training set. Augmented entries from the minority class (i.e, car) to match the majority class (person). Applied 2 augmentation techniques lightening the image and adding Gaussian noise. <br>
Dataset link: [Dataset 2](https://drive.google.com/drive/folders/1CKkfcVkkF5T-M3GqyADCpjHRoMbWETag?usp=sharing)

### Results


### Inference


## Conclusions and recommendations



