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
<img width="3570" height="1470" alt="Academic_Result_Plot" src="https://github.com/user-attachments/assets/677f6196-87fb-4aeb-9cc7-58482e3cec78" />
*Figure 1: mAP and Loss evolution demonstrating high stability.*

### 2. Scientific Reliability
<img width="3000" height="2250" alt="confusion_matrix_normalized" src="https://github.com/user-attachments/assets/6bf5f9dd-8da6-471d-9df9-5465848b8cc7" />
*Figure 2: Perfect diagonal scores (1.00) indicating zero-error classification.*

### 3. Large-Scale Inference (1,001 Samples)
![image_10006105038133512240571![image_102820603644519315565112114322903280482](https://github.com/user-attachments/assets/919cc03b-b2d9-4a00-9178-5fe421c56e41)
![image_13488709593983917947377688377175224857](https://github.com/user-attachments/assets/2bcf2e6e-f6c5-435e-a66a-0656ace8f7be)
![image_111831504995325074319548509113012552193](https://github.com/user-attachments/assets/a0ce61ee-3d8c-45c7-a27e-dce4ed9f852f)
9538882377792147](https://github.com/user-attachments/assets/4dbb7ef3-719f-44b3-a2aa-65bc77a9c46d)
*Figure 3: Batch processing results for massive astronomical survey data.*

![val_batch0_pred](https://github.com/user-attachments/assets/241bb3a4-8eaf-4704-88e5-0c084cf6ed31)
*Figure 4: Einstein Ring localization with 0.97 confidence.*

---

## 🛠️ Environment & Weights
- **Python:** 3.12.12 | **Core:** `ultralytics`, `torch`
- **Model Weights (`best.pt`):** > **⚠️ NOTICE:** Due to GitHub's file size limit, the finalized 128MB `best.pt` weights are **not** included in the repository. They are stored locally for the live demonstration. For remote access, please contact the developer for a private link.

## 📜 Technical Report
For a deep dive into the methodology, refer to:  
`Project Technical Evaluation Report.docx` (or .pdf)

