# MCFAD-YOLO

[![Python 3.7+](https://img.shields.io/badge/Python-3.7+-green.svg)](https://www.python.org/)
[![PyTorch 1.7+](https://img.shields.io/badge/PyTorch-1.7+-red.svg)](https://pytorch.org/)

MCFAD-YTOLO is a real-time object detection framework based on YOLOv11, designed for small-scale object detection in complex scenarios.

## 📦 Installation

Install ultralytics package with all dependencies in Python 3.7-3.10 environment:

```bash
pip install -r requirements.txt
```

This will install ultralytics and all required packages including PyTorch>=1.7.

## 🚀 Usage

### 2.1 Train

```bash
python train.py
```

Or use Python API:

```python
from ultralytics import YOLO
model = YOLO('ultralytics/cfg/models/11/yolo11.yaml')
model.train(data='data/simd.yaml', epochs=600, imgsz=640)
```

### 2.2 Validate

```bash
python predict.py
```

Or use Python API:

```python
from ultralytics import YOLO
model = YOLO('path/to/best.pt')
model.val(data='data/simd.yaml')
```

## 📁 Key Directory Structure

### 3.1 Configuration Files (`ultralytics/cfg`)

- **Model Architecture**: Located in `models/11/` subdirectory, contains detailed network structure configurations
- **Dataset Settings**: Stored in `datasets/` subdirectory, defines paths, classes and related parameters
- **Training/Test Settings**: Managed by `default.yaml`, including hyperparameters, optimizer settings and other training configurations

### 3.2 Module Implementation (`ultralytics/nn/modules`)

Contains core neural network modules and custom layer implementations.

## 📊 Dataset

The project uses **SIMD Dataset** with 15 object classes:

- Vehicles: car, truck, van, longvehicle, bus
- Aircraft: airliner, propeller, trainer, chartered, fighter, other
- Ground Support: stairtruck, pushbacktruck
- Others: helicopter, boat

Configure dataset in `data/simd.yaml`.

## 📄 License

This project is licensed under the MIT License.

---

⭐ Star this repository if you find it helpful!
