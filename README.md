# 🌌 Deep-Space Gravitational Lensing Detection System
**Project Lead:** JingHao Zhang | **Framework:** RT-DETR (Real-Time Detection Transformer)

## 🏆 Project Achievements
- **Precision:** Peak **mAP@50 of 0.994** after 55 epochs.
- **Reliability:** **1.00 Confusion Matrix score**, achieving zero false positives.
- **Scale:** Automated "Search and Rescue" processing of **1,001 unseen samples**.

---

## 🏗️ Technical Architecture & Matrix Logic

### Hybrid Encoder & Tensor Transformation
The RT-DETR model processes astronomical images through a Hybrid Encoder. The high-dimensional tensor transformation is critical for capturing long-range dependencies in lensing arcs:

1. **Flattening:** Input feature map $\mathbf{X} \in \mathbb{R}^{C \times H \times W} \to \mathbf{X}_{flat} \in \mathbb{R}^{L \times C}$ where $L = H \times W$.
2. **Attention Mechanism:** $$\text{Attention}(Q, K, V) = \text{Softmax}\left(\frac{QK^T}{\sqrt{d_k}}\right)V$$
   This allows the model to correlate distant pixels, effectively distinguishing between a centered lens galaxy and its peripheral Einstein rings.

### Loss Function: GIoU Optimization
To achieve precise localization (GIoU Loss $\approx 0.1$), we implement Generalized Intersection over Union:
$$GIoU = IoU - \frac{|C \setminus (A \cup B)|}{|C|}$$
$$\mathcal{L}_{GIoU} = 1 - GIoU$$
This ensures continuous gradients even when the initial bounding box has no overlap with the lensing target.

---

## 📈 Performance Visualization
*(Note: Please ensure image files are located in the respective folders below)*

### 1. Training Convergence
![Training Log](03_Training_Log/Academic_Result_Plot.png)  
*Figure 1: mAP and Loss evolution demonstrating high stability.*

### 2. Scientific Reliability
![Confusion Matrix](04_Academic_Metrics/confusion_matrix_normalized.png)  
*Figure 2: Perfect diagonal scores (1.00) indicating zero-error classification.*

### 3. Large-Scale Inference (1,001 Samples)
![Inference List](05_Detection_Results/inference_list_screenshot.png)  
*Figure 3: Batch processing results for massive astronomical survey data.*

![Detection Sample](05_Detection_Results/best_sample.png)  
*Figure 4: Einstein Ring localization with 0.97 confidence.*

---

## 🛠️ Environment & Weights
- **Python:** 3.12.12 | **Core:** `ultralytics`, `torch`
- **Model Weights (`best.pt`):** > **⚠️ NOTICE:** Due to GitHub's file size limit, the finalized 240MB `best.pt` weights are **not** included in the repository. They are stored locally for the live demonstration. For remote access, please contact the developer for a private link.

## 📜 Technical Report
For a deep dive into the methodology, refer to:  
`Project Technical Evaluation Report.docx` (or .pdf)
