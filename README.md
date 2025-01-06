# 🎓 Object Detection Model Compression

Welcome to my Final Year Project (FYP) repository! This project focuses on compressing a pre-trained object detection and depth estimation model to run them on mobile devices. Currently, this repository contains the detection model that is trained on the COCO dataset, and the compression process is underway.

> **Note**: This repository is still under construction. Stay tuned for updates!

## 📋 Project Overview

- **Dataset**: COCO (Common Objects in Context)
- **Task**: Object Detection, Depth Estimation and Model Compression
- **Current Status**: Model trained on COCO dataset. Compression process to be initiated. Depth estimation to be initiated.

## 🚀 Getting Started

Follow these steps to test the model:

### 0. 🔧 Install Requirements

Go to the main directory and run the following command to install the necessary libraries:

```bash
pip3 install -v -e .
```

### 1. 📥 Download the Model

Download the model file from [Google Drive](https://drive.google.com/drive/u/0/folders/1jadffQiu44F5BTvHcNPziXN6vBu2Shvd).

### 2. 📁 Place the Model File

After downloading, place the model file in the main directory of this repository or within any subfolder of your choice.

### 3. 🏃‍♂️ Run the Demo

You can perform object detection on both images and videos using the following commands.

#### 🖼️ For Detection in Image

Use the following command to provide the paths to the image and model file:

```bash
python tools/demo.py image -n yolox-tiny -c path/to/model/file --path path/to/image.jpg --conf 0.25 --nms 0.45 --tsize 640 --save_result --device [cpu/gpu]
```

**Parameters Explained**:
- `-n yolox-tiny`: Specifies the model architecture
- `-c path/to/model/file`: Path to the compressed model file
- `--path path/to/image.jpg`: Path to the input image
- `--tsize 640`: Input image size
- `--device [cpu/gpu]`: Choose between CPU or GPU for inference

#### 🎥 For Live Video Detection

Use the following command to provide the paths to the video and model file:

```bash
python tools/demo.py video -n yolox-tiny -c path/to/model/file --path path/to/video.mp4 --conf 0.25 --nms 0.45 --tsize 640 --save_result --device [cpu/gpu]
```

**Parameters Explained**:
- `-n yolox-tiny`: Specifies the model architecture
- `-c path/to/model/file`: Path to the compressed model file
- `--path path/to/video.mp4`: Path to the input video
- `--conf 0.25`: Confidence threshold for detections
- `--nms 0.45`: Non-Maximum Suppression threshold
- `--tsize 640`: Input video frame size

## 🔍 Evaluation

Batch testing for fast evaluation using the following command:

```bash
python -m yolox.tools.eval -n yolox-tiny -c path/to/yolox_tiny.pth -b 64 -d 8 --conf 0.001 [--fp16] [--fuse]
```

**Parameters Explained**:
- `-n yolox-tiny`: Specifies the model architecture
- `-c path/to/yolox_tiny.pth`: Path to the model file
- `-b 64`: Total batch size across all GPUs
- `-d 8`: Number of GPUs used for evaluation. Default: All available GPUs will be used


> **Note**: Currently, only yolox-tiny is supported for evaluation.

## 🔧 Requirements

Go to the main directory and run the following command to install the necessary libraries:

```bash
pip3 install -v -e .
```

## 📫 Contact

Feel free to reach out to me at bsef21m013@pucit.edu.pk for any queries or collaborations. You can use this open-source work for personal usage or education. 
