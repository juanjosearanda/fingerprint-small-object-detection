# Figure 1. Complete Methodology Workflow

Purpose: Overview of the entire pipeline.
```
SOCOFing
    │
    ▼
Bounding Box Generation
    │
    ▼
YOLO Label Creation
    │
    ▼
Synthetic Dataset Generator
    │
    ├─ Multi-scale fingerprints
    ├─ Occlusions
    ├─ Noise
    └─ Random placement
    │
    ▼
YOLOv8 Training
    │
    ▼
Real-World Evaluation
    │
    ▼
CLAHE Analysis
```
