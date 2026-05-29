# License Plate Detection and Recognition System

## Overview

This project detects vehicle license plates using **YOLOv8** and extracts the license plate text using **OCR (EasyOCR/PaddleOCR)**. The system can identify license plates from images, draw bounding boxes around them, and convert the detected plate numbers into readable text.

## Features

* License plate detection using YOLOv8
* Optical Character Recognition (OCR) using EasyOCR and PaddleOCR
* Bounding box visualization on detected plates
* License plate text extraction
* CSV logging of detected license plate numbers
* Trained custom model for improved detection accuracy

## Tech Stack

* Python
* YOLOv8 (Ultralytics)
* OpenCV
* EasyOCR
* PaddleOCR
* NumPy
* Matplotlib

## Project Workflow

1. Collect and prepare a labeled license plate dataset.
2. Train a custom YOLOv8 model on the dataset.
3. Detect license plates in input images.
4. Crop the detected license plate region.
5. Apply OCR to extract the license plate number.
6. Store the extracted text and detection details.

## Installation

### Clone the Repository

```bash
git clone https://github.com/your-username/license-plate-detection.git
cd license-plate-detection
```

### Install Dependencies

```bash
pip install ultralytics
pip install easyocr
pip install paddleocr paddlepaddle
pip install opencv-python matplotlib numpy
```

## Dataset Structure

```text
dataset/
│
├── images/
│   ├── train/
│   └── val/
│
├── labels/
│   ├── train/
│   └── val/
│
└── config.yaml
```

## Training the Model

```python
from ultralytics import YOLO

model = YOLO("yolov8n.pt")
model.train(data="config.yaml", epochs=25)
```

## Running Detection

```python
from ultralytics import YOLO

model = YOLO("best.pt")
results = model("test_image.jpg")
```

## OCR Extraction

The detected license plate region is cropped and passed to EasyOCR or PaddleOCR to extract the plate number.

Example Output:

```text
MH12AB1234
```

## Results

* Successfully detects vehicle license plates from images.
* Extracts plate numbers using OCR.
* Generates annotated output images with detected bounding boxes.


## Applications

* Smart Parking Systems
* Traffic Monitoring
* Toll Collection Systems
* Vehicle Access Control
* Law Enforcement
