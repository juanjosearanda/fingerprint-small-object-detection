# Small Object Fingerprint Detection on Printed Documents Using YOLOv8 and Synthetic Dataset Augmentation

## Overview
This repository contains the code, notebooks, and documentation used to investigate small fingerprint detection in printed documents using YOLOv8.

### Research Goal
Detect small printed fingerprints embedded in larger document images captured under real-world acquisition conditions.

## Key Findings
- Automatic bounding-box generation from SOCOFing.
- Synthetic dataset generation for small-object detection.
- YOLOv8n training for printed fingerprint localization.
- Real-world validation identified contrast as a dominant factor.
- CLAHE preprocessing improved real-world detectability.

## Repository Structure
```text
fingerprint-small-object-detection/
├── paper/
├── notebooks/
├── src/
├── configs/
├── docs/
├── examples/
├── requirements.txt
└── README.md
```

## Environment Setup
### Ubuntu 24.04
```bash
sudo apt update
sudo apt install python3-venv python3-tk
python3 -m venv .venv
source .venv/bin/activate
pip install --upgrade pip
pip install -r requirements.txt
```

### Windows
```powershell
python -m venv .venv
.venv\Scriptsctivate
pip install --upgrade pip
pip install -r requirements.txt
```

## Dataset Acquisition
This repository does NOT redistribute SOCOFing.

1. Obtain SOCOFing from its original source.
2. Place images in:
```text
data/raw/
```
3. Run bounding-box generation.
4. Generate the synthetic dataset.
5. Train the detector.

## Reproducibility Workflow
### 01 Generate Bounding Boxes
```bash
python src/bbox_generator.py
```

### 02 Generate Synthetic Dataset
```bash
python src/dataset_generator_v2.py
```

### 03 Train YOLOv8
```bash
python src/training.py
```

### 04 Evaluate
```bash
python src/camera_app.py
```

## Kaggle Reproduction
1. Create a Kaggle Dataset from the generated synthetic dataset.
2. Upload notebooks.
3. Enable GPU.
4. Run training notebook.
5. Export weights and results.

## Results Reported So Far
### retrain
- mAP50: 0.994
- mAP50-95: 0.958

### small_fingerprints_v1
- Precision: 0.989
- Recall: 0.997
- mAP50: 0.995
- mAP50-95: 0.995

## Important Observation
The largest deployment bottleneck was not model accuracy but image acquisition quality. Real-world experiments showed that CLAHE preprocessing substantially improved fingerprint detectability.
