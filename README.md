# 🔥 CAIR-Net: Reliability-Aware Information Routing for Robust Multimodal Object Detection under Modality Degradation

<p align="center">
  <img src="framework2.png" width="860"/>
</p>

<p align="center">
  <strong>IEEE TCSVT 2026</strong> | Reliability-Aware Multimodal Detection under Degradation
</p>

---

## 📦 Dataset Download

**Train Dataset**  
🔗 https://pan.quark.cn/s/caa621e0ce5b  
🔑 Code: `ApzY`

**Test Dataset**  
🔗 https://pan.quark.cn/s/e35825478a69  
🔑 Code: `UssQ`

---

## 📖 Overview

Multimodal remote sensing (Optical + SAR) provides complementary information for object detection.  
However, in real-world scenarios, **modality degradation is inevitable**:

- 🌥 Optical images → cloud, haze, low-light  
- 📡 SAR images → noise, interference  

❗ When degraded features are directly fused, they **contaminate the joint representation**, leading to severe performance drop.

---

## 🚨 Limitations of Existing Methods

Current approaches still suffer from critical weaknesses:

- ❌ **Naive fusion**: treats all modalities equally → ignores reliability  
- ❌ **Attention-based fusion**: focuses on semantics, not signal quality  
- ❌ **Restoration-first pipelines**: introduce artifacts + high latency  
- ❌ **No controlled benchmark**: lack reproducible degradation evaluation  

👉 These methods fail under **spatially heterogeneous and severe degradation**

---

## 📊 Dataset: MMD-C Benchmark

We propose a **controlled multimodal degradation benchmark**.

### 🧩 Construction

- Based on **co-registered Optical–SAR pairs**
- Only **optical modality is degraded**
- SAR remains unchanged → simulate **modality imbalance**

### 🌩 Degradation Design

- Realistic cloud masks + alpha blending  
- Continuous severity levels:

```text
0 → 0.2 → 0.5 → 0.8 → 1.0
