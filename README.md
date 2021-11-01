# custom-object-detection
Custom Object Detection model with 2 classes persons and cars.

## About the Model

YOLOv5 is the state-of-the-art object detection model pre-trained on MS COCO. Yolov5 implementation has been done in PyTorch. It is easier to understand, training and deployment using the PyTorch ecosystem. YOLOv5 is faster and accurate. The release of YOLOv5 includes different model sizes YOLOv5s(smallest), YOLOv5m, YOLOv5l, YOLOv5x(largest). 

I have used the YOLOv5m model for the given task

I have followed the [GitHub Repo for the original YOLOv5 model](https://github.com/ultralytics/yolov5) to use YOLOv5 for training and inferencing.

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

The trained model files are uploaded in the [Google Drive](https://drive.google.com/drive/folders/1toON70EAUBLJIhNJE6V361muuxZZ-oL_?usp=sharing)

### Results
Training results on the validation set (30 images)
<br>
Experiment 1:

| Class          | Precision | Recall  | mAP
| ------------- | ------------- |-------|---|
|  all | 0.766| 0.587| 0.635  |
|  person| 0.767| 0.56| 0.608  |
|  car| 0.765| 0.613| 0.663  |

Experiment 2:

| Class          | Precision | Recall  | mAP
| ------------- | ------------- |-------|---|
|  all | 0.7| 0.698| 0.675  |
|  person| 0.461| 0.472| 0.393  |
|  car| 0.939| 0.923| 0.958 |

### Inference
Tested the models on new images collected from web. The test results are in results/ directory.

## Conclusions and recommendations
The given dataset is having more instances in one class than the other class. There are several ways we can improve the class imbalance.
* I have done augmentation of lower class data instead of soing Downsampling the higher class. With down sampling we will loose the important imformation and size of the dataset will be reduced. We can apply some other techniques like using focal loss for training etc.
* Note: As I am having limited GPU resources, I have done with 2 experiments only. 


