
# Object Detection with TensorFlow Hub

A Google Colab project that runs pre-trained COCO 2017 object detection models (SSD MobileNet V2 / EfficientDet) on custom images using a T4 GPU

## Features
- **Pre-trained Models:** Supports switching between lightweight (`SSD MobileNet V2 FPNLite`) and high-accuracy (`EfficientDet`) architectures via TensorFlow Hub.
- **Custom Image Inference:** Loads and runs detection on uploaded `.jpg` / `.png` images with RGB conversion to avoid 4-channel alpha errors.
- **Readable Bounding Boxes:** Automatically resizes high-resolution phone photos (`800x800` thumbnail) before inference so bounding box lines and confidence labels stay clearly visible.

## Key Fix for Google Colab (Python 3.13)
Google Colab's Python 3.13 runtime fails on the legacy `tensorflow_io` dependency inside `tensorflow/models`. This notebook resolves it by installing the Object Detection API without outdated dependencies:

```bash
python -m pip install --no-deps .
