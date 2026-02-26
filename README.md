# Deep-Space Gravitational Lensing Detection System
**Project Lead:** Raymond Jing | **Date:** Feb 26, 2026

## 🚀 Overview
[span_10](start_span)[span_11](start_span)This project utilizes the **RT-DETR** (Real-Time Detection Transformer) architecture to automate the "search and rescue" of gravitational lensing targets in deep-space surveys[span_10](end_span)[span_11](end_span).

## 📈 Training & Convergence
[span_12](start_span)The model achieved near-perfect precision after 55 epochs of intensive training[span_12](end_span).

![Training Metrics](03_Training_Metrics/Academic_Result_Plot.png)
*[span_13](start_span)Figure 1: mAP@50 reached 0.994 with stable Bounding Box Regression (GIoU Loss ~0.1)[span_13](end_span).*

## 🔬 Scientific Reliability
[span_14](start_span)[span_15](start_span)Rigorous evaluation confirms the system's readiness for professional astronomical use[span_14](end_span)[span_15](end_span).

| Metrics | Performance | Impact |
| :--- | :--- | :--- |
| **mAP@50** | 0.994 | [span_16](start_span)Exceptional target identification[span_16](end_span). |
| **Confusion Matrix** | 1.00 | [span_17](start_span)Zero false positives/negatives[span_17](end_span). |
| **F1-Score Stability** | 1.00 (0.2-0.8 threshold) | [span_18](start_span)Robust against cosmic noise[span_18](end_span). |

![Confusion Matrix](04_Academic_Metrics/confusion_matrix_normalized.png)
*[span_19](start_span)[span_20](start_span)Figure 2: Perfect diagonal score (1.00) ensures zero-false-positive detections[span_19](end_span)[span_20](end_span).*

## 🔭 Large-Scale Deployment
[span_21](start_span)The model (best.pt) was deployed on **1,001 unseen samples**, demonstrating high generalization[span_21](end_span).

![File List](05_Inference_Results/inference_list_screenshot.png)
*[span_22](start_span)Figure 3: Automated processing of 1,001 deep-space images[span_22](end_span).*

![Lensing Detection](05_Inference_Results/best_detection_sample.png)
*[span_23](start_span)Figure 4: Precise localization of an Einstein Ring with 0.97 confidence[span_23](end_span).*

---
### 🛠️ Quick Start
1. Install dependencies: `pip install -r requirements.txt`
2. Run inference: `yolo predict model=02_Model_Weights/best.pt source=...`
