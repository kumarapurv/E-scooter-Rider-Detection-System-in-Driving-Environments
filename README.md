# Overview
Object detection system to differentiate e-scooter riders and other humans in natural driving environments.

# Abstract
E-scooters have become ubiquitous vehicles in major cities around the world. The numbers of e-scooters keep escalating, increasing their interactions with other cars on the road. An e-scooter rider’s normal behavior varies enormously to other vulnerable road users. This situation creates new challenges for vehicle active safety systems and automated driving functionalities, which require the detection of e-scooter riders as the first step. To our best knowledge, there is no existing computer vision model to detect these e-scooter riders. This paper presents a novel vision-based system to differentiate between e-scooter riders and regular pedestrians and a benchmark data set for e-scooter riders in natural scenes. We propose an efficient pipeline built over two existing state-of-the-art convolutional neural networks (CNN), `You Only Look Once (YOLOv3)` and `MobileNetV2`. We fine-tune MobileNetV2 over our dataset and train the model to classify e-scooter riders and pedestrians. We obtain a recall of around 0.75 on our raw test sample to classify e-scooter riders with the whole pipeline. Moreover, the classification accuracy of trained MobileNetV2 on top of YOLOv3 is over 91%, with precision and recall over 0.9.

# Detection Pipeline
The system pipeline consists of three stages:
- Candidate Region Selection
- Extended Region Extraction
- Binary Image Classification

![](https://github.com/kumarapurv/E-scooter-Rider-Detection-System-in-Driving-Environments/blob/main/images/model_architecture.png)

# Dataset
The data was collected in Indianapolis. Using the vehicle shown in the figure below, the entire interaction of e-scooter riders were captured around the car.

<img src="https://github.com/kumarapurv/E-scooter-Rider-Detection-System-in-Driving-Environments/blob/main/images/WNP_0918-1.jpg" width=60% height=60%>

The data will be made available to the public soon.

# Training
In the candidate region selection step, the base model `YOLOv3`, trained on COCO dataset, is used to detect humans first. The trained weights used in this module can be found [here](https://github.com/kumarapurv/E-scooter-Rider-Detection-System-in-Driving-Environments/tree/main/model%20weights/YOLO).

`MobileNetV2` was trained for the binary classification task. The model was trained by us on our dataset, and the weights can be found [here](https://github.com/kumarapurv/E-scooter-Rider-Detection-System-in-Driving-Environments/tree/main/model%20weights/e-scooter%20detector%20model).

# Results
![demo-output](https://github.com/kumarapurv/E-scooter-Rider-Detection-System-in-Driving-Environments/blob/main/results/demo_output.gif)

The e-scooter riders are colored in green and others are colored in yellow.

# Cite as:
```
arXiv:2111.14060
```
or
```
@article{apurv2021detection,
  title={Detection of E-scooter Riders in Naturalistic Scenes},
  author={Apurv, Kumar and Tian, Renran and Sherony, Rini},
  journal={arXiv preprint arXiv:2111.14060},
  year={2021}
}
```
