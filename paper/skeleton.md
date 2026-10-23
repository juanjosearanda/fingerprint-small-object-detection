# 1. Introduction
Motivation
Printed documents frequently contain fingerprints.

Traditional fingerprint datasets:
- SOCOFing
- FVC
- NIST

## Contributions
- Bounding box generation workflow.
- Synthetic dataset generator.
- Small-object fingerprint detector.
- Real-world evaluation.
- Analysis of illumination and contrast effects.

## The strongest contribution is the engineering methodology:
SOCOFing
↓
bounding boxes
↓
synthetic small-object dataset
↓
YOLOv8 training
↓
real-world failure
↓
contrast analysis
↓
CLAHE improvement

This is a compelling and reproducible story that other researchers can learn from.

# 2. Related Work
- Fingerprint Recognition
- Object Detection
- Small Object Detection
- Synthetic Dataset Augmentation
- YOLO Applications

# 3. Dataset Preparation
- SOCOFing

- Description.

- Bounding Box Generation

- Automatic contour extraction.

- Label Generation

- YOLO format.

# 4. Synthetic Dataset Construction
- 640×480 Document Simulation
- Multi-scale Fingerprints:
1. 40–60 px
2. 60–90 px
3. 90–120 px
- Occlusions:
1. horizontal
2. vertical
3. diagonal
- Noise
- Placement

# 5. Model Training
- YOLOv8n
- Training Configuration:
1. epochs
2. batch
3. imgsz
4. patience

## Hardware Configuration
- Windows + CUDA
- Ubuntu + CPU

# 6. Experimental Results
- retrain
- small_fingerprints_v1

Comparison table.

# 7. Real-World Validation
This section includes:
- Initial failure: 0/4 detections
- CLAHE preprocessing: 3/4 detections

# 8. Discussion
- dataset shift
- domain adaptation
- illumination
- contrast
- small object limitations

# 9. Conclusions

# 10. Future Work
- small_fingerprints_v2
- mobile deployment
- embedded deployment
- user workflow
