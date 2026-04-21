# 🔥 CAIR-Net: Reliability-Aware Information Routing for Robust Multimodal Object Detection under Modality Degradation

<p align="center">
  <img src="framework2.png" width="880"/>
</p>

<p align="center">
  <strong>IEEE TCSVT 2026</strong> | Reliability-Aware Optical–SAR Detection under Cloud Degradation
</p>

---

## 📖 Overview

Multimodal remote sensing combines **optical imagery** and **SAR** for robust object detection.  
However, in real-world scenarios:

- 🌥 Optical images are frequently degraded by **cloud occlusion**
- 📡 SAR remains stable but suffers from **noise and limited semantic detail**

❗ Under such conditions, directly fusing degraded optical features leads to **feature contamination** and severe performance degradation.

To address this, we propose **CAIR-Net**, a **reliability-aware information routing framework** that follows a:

> 🔑 **Denoise → Select → Fuse**

pipeline to suppress corrupted signals and adaptively exploit reliable information.

---

## 🚨 Limitations of Existing Methods

Existing multimodal detection approaches struggle under cloud degradation:

- ❌ **Naive fusion** assumes all modalities are equally reliable  
- ❌ **Attention-based fusion** focuses on semantics, ignoring signal quality  
- ❌ **Restoration-first methods** introduce artifacts and increase latency  
- ❌ **Lack of benchmark** for controlled cloud degradation evaluation  

👉 These methods suffer **rapid performance drop** under increasing cloud density.

---

## 📊 Dataset: MMD-C Benchmark

We construct a **controlled cloud-degraded multimodal benchmark (MMD-C)**.

### 🧩 Construction

- Built on **co-registered optical–SAR pairs**
- Only **optical modality is degraded**
- SAR remains unchanged → simulate **modality imbalance**

---

### 🌩 Cloud Degradation

Cloud corruption is generated via alpha blending:
Cloud density:

```text
0 → 0.2 → 0.5 → 0.8 → 1.0


---

### ✨ Key Features

- ✔ Controlled and reproducible  
- ✔ Spatially heterogeneous cloud occlusion  
- ✔ Same scene under multiple degradation levels  
- ✔ Fine-grained robustness evaluation  

---

## 📦 Dataset Download

**Train Dataset**  
🔗 https://pan.quark.cn/s/caa621e0ce5b  
🔑 Code: `ApzY`

**Test Dataset**  
🔗 https://pan.quark.cn/s/e35825478a69  
🔑 Code: `UssQ`

---

## 🧠 Method: CAIR-Net

### 🔹 Core Idea

> Reformulate multimodal detection as a **reliability-aware routing problem**

---

### 🔸 1. Local Reliability Modulation (LRM)

- 📍 Pixel-wise reliability estimation  
- 🔻 Suppresses cloud-corrupted regions  
- 🧠 Acts as spatial quality modeling  

👉 Prevents degraded optical features from entering fusion

---

### 🔸 2. Global Information Selection Mechanism (GISM)

#### ⚙️ Sparse Expert Activation (SEA)

- Replace FFN with **sparse MoE**
- Activate Top-K experts per token  
- Capture diverse feature patterns  

---

#### 🎯 Confidence-Aware Expert Aggregation (CEA)

- Dynamically weight:
  - Optical 🌥
  - SAR 📡
  - Fused 🔗
- Route information based on reliability  

👉 Automatically suppress unreliable modality

---

### 🔸 3. Reliability-Aware Fusion

- Combine local (LRM) + global (CEA)  
- Adaptive multimodal fusion  
- Robust under severe cloud occlusion  

---

## 🚀 Highlights

- 🌩 Controlled **cloud-degradation benchmark**
- 🧠 Reliability-aware routing (**LRM + GISM**)
- ⚡ End-to-end **denoise-then-fuse**
- 📉 Strong robustness under heavy clouds
- 🔄 No degradation labels required

---

## 📈 Results

| Method | AP | AP50 |
|--------|----|------|
| MMFDet | 57.1 | 87.0 |
| DDCI   | 58.5 | 86.4 |
| C2Former | 58.9 | 87.0 |
| ICAFusion | 50.3 | 91.2 |
| **CAIR-Net (Ours)** | **63.8** | **94.5** |

👉 CAIR-Net achieves **significant improvement** under cloud degradation.

---

## 🎨 Visualization

### Reliability-Aware Routing

- Optical weight ↓ as cloud increases  
- SAR weight ↑ under heavy occlusion  
- Adaptive expert selection  

👉 Model automatically **shifts reliance to reliable modality**

---
## Citation

```bibtex
@article{su2026cairnet,
  title={CAIR-Net: Reliability-Aware Information Routing for Robust Multimodal Object Detection under Modality Degradation},
  author={Su, Yudi and Ni, Jialei and Wen, Tiansheng and Liu, Hongwei and Su, Hongtao and Chen, Bo},
  journal={IEEE Transactions on Circuits and Systems for Video Technology},
  year={2026}
}

