# YOLO-MCHKD: A Lightweight Crack Detection Model with Cross-head Knowledge Distillation

This repository contains the source code for the paper. The complete implementation will be made publicly available upon acceptance.

## Overview

## Abstract
Detecting surface cracks plays a vital role in the health monitoring of infrastructure. Ideally, inspection systems are deployed on edge devices for on-site analysis. However, such deployment is hindered due to the complexity of many deep learning–based models. To address this challenge, this article proposed a lightweight crack detection model based on YOLOv8n, termed YOLO Cross-Head Knowledge Distillation (YOLO-CHKD). First, we replace the original YOLO backbone with MobileNetV3 and design a lightweight neck. Second, we swapped the CIoU loss with the EIoU loss to improve detection performance. Eventually, we introduce a soft-teacher mechanism in the cross-head knowledge distillation to recover performance and ensure both high accuracy and real-time inference capability. This approach transfers rich feature representations and decision information from the large-scale teacher model to the small-scale student model. The proposed model was successfully deployed on a Jetson Nano at 10.01 FPS, demonstrating its suitability for industrial inspection applications, and also highlighting the impact of layer number on inference time. The computational efficiency is validated on the Crack-BPHDR dataset, where YOLO-CHKD reduces the parameter number and GFLOPs by 60\% while experiencing a slight reduction in accuracy, compared to the baseline model, YOLOv8n. The generalizability is evaluated on the GC10-DET dataset, where YOLO-CHKD improved mAP0.5 by 3.87\%.

<img width="784" alt="YOLO-CHKD" src="https://github.com/Hiepresearchgroup/CHKD-YOLO/blob/main/img/Overview_YOLO-CHKD.png">

## Datasets

The details are shown in our paper.

Crack dataset is available at https://docs.ultralytics.com/datasets/segment/crack-seg/

GC10-DET dataset is available at https://github.com/lvxiaoming2019/GC10-DET-Metallic-Surface-Defect-Datasets

## Training
Most of training configurations can change in the "Train settings" section of ultralytics/cfg/default.yaml. 
The key factors are model, data, img, epoches, batch, device and training hyperparameters.
For example, you can use "model: hyper-yolon.yaml" to train an object detection model.
```bash
python ultralytics/models/yolo/detect/train.py 
```

## Evaluation
Most of evaluation configurations can change in the "Val/Test settings" section of ultralytics/cfg/default.yaml. 
The key factors are model(weight), data, img, batch, conf, iou, half.
```bash
python ultralytics/models/yolo/detect/val.py
```

## Acknowledgement
Our code is built based on the [YOLOv8](https://github.com/ultralytics/ultralytics).
Thanks for their great work!





