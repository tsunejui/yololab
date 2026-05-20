# YoloLab

A development playground for building computer vision systems with **OpenCV** and **YOLO** (You Only Look Once).

This repository serves as a lab environment to prototype, experiment, and ship object detection, image processing, and real-time vision applications.

## Overview

YoloLab focuses on:

- **Object Detection** — Train and deploy YOLO models (YOLOv5, YOLOv8, YOLOv11, and beyond) for custom detection tasks.
- **Image & Video Processing** — Leverage OpenCV for preprocessing, augmentation, drawing, and post-processing pipelines.
- **Real-time Inference** — Build webcam, video file, and streaming inference applications.
- **Model Experimentation** — Compare model architectures, benchmark performance, and tune hyperparameters.
- **Dataset Tooling** — Utilities for labeling, dataset conversion, and validation.

## Tech Stack

- **Python 3.10+**
- **OpenCV** (`opencv-python`)
- **Ultralytics YOLO** (`ultralytics`)
- **PyTorch** as the underlying deep learning framework
- **NumPy**, **Pillow**, **matplotlib** for supporting utilities

## Getting Started

### Prerequisites

- Python 3.10 or newer
- `pip` or `uv` for dependency management
- (Optional) CUDA-capable GPU for accelerated training and inference

### Installation

```bash
git clone https://github.com/tsunejui/yololab.git
cd yololab

python -m venv .venv
source .venv/bin/activate

pip install --upgrade pip
pip install opencv-python ultralytics
```

### Quick Example

```python
import cv2
from ultralytics import YOLO

model = YOLO("yolo11n.pt")

image = cv2.imread("sample.jpg")
results = model(image)

annotated = results[0].plot()
cv2.imshow("YoloLab", annotated)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

## Project Structure

```
yololab/
├── data/         # Datasets, images, and labels
├── models/       # Trained model weights (.pt)
├── notebooks/    # Jupyter experiments
├── scripts/      # Training, inference, and utility scripts
└── src/          # Reusable library code
```

## Roadmap

- [ ] Baseline detection demo with a pretrained YOLO model
- [ ] Custom dataset training pipeline
- [ ] Real-time webcam inference example
- [ ] Model export (ONNX / CoreML / TensorRT)
- [ ] Benchmarking suite across YOLO versions

## Contributing

Issues and pull requests are welcome. Please open an issue first to discuss any significant changes.

## License

MIT
