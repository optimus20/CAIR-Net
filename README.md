# CAIR-Net

## Dataset Download

Train dataset:  
https://pan.quark.cn/s/caa621e0ce5b  
Code: `ApzY`

Test dataset:  
https://pan.quark.cn/s/e35825478a69  
Code: `UssQ`


---

## Paper

**CAIR-Net: Reliability-Aware Information Routing for Robust Multimodal Object Detection under Modality Degradation**

<p align="center">
  <img src="framework2.png" width="800"/>
</p>


---

## Motivation

Multimodal remote sensing (e.g., optical + SAR) has become a standard paradigm for robust object detection.  
However, in real-world scenarios, **different modalities are often affected by heterogeneous degradations**, leading to severe **information inconsistency and unreliable fusion**.

- Optical images: cloud, low-light, color distortion  
- SAR images: speckle noise, system artifacts  

### Limitations of Existing Methods

- ❌ **Naive fusion strategies** treat all modalities equally, ignoring reliability differences  
- ❌ **Degradation-specific methods** rely on explicit labels, limiting real-world applicability  
- ❌ **General multimodal detectors** fail to suppress corrupted features under cross-modal interference  

As a result, existing approaches often suffer from **performance degradation under severe or mixed corruption**.


---

## Dataset Construction

To systematically study this problem, we construct a multimodal degradation benchmark:

### **MMD-C Benchmark**

- Covers **three degradation families**:
  - Atmospheric: cloud, halo, low-light, color cast  
  - Geometric: motion blur, downsampling  
  - Systemic: noise, shadow, local distortion, stripe, speckle  

### Key Properties

- ✔ Controlled degradation levels (e.g., cloud density from 0 → 1.0)  
- ✔ Same scene with multiple degradation variants  
- ✔ Enables fair and quantitative robustness evaluation  

This benchmark provides a **standardized testbed** for multimodal detection under realistic degradation conditions.


---

## Method

CAIR-Net introduces a **reliability-aware information routing mechanism** for multimodal detection.

### Key Components

### 1. Local Reliability Modulation (LRM)

- Learns **pixel-wise reliability maps**
- Suppresses degraded regions via soft modulation  
- Provides a **data-driven estimation of feature quality**

---

### 2. Global Information Selection Mechanism (GISM)

Replaces standard Transformer FFN with **sparse expert routing**

- **SEA (Sparse Expert Aggregation)**  
  - Selects Top-K experts  
  - Captures diverse degradation-aware feature patterns  

- **CEA (Conditional Expert Aggregation)**  
  - Dynamically weights expert outputs  
  - Enables input-dependent global feature selection  

---

### 3. Reliability-Aware Fusion

- Adaptive fusion of optical and SAR features  
- Guided by reliability estimation  
- Reduces cross-modal interference  

---

## Highlights

- ✔ First framework to explicitly model **reliability-aware routing** in multimodal detection  
- ✔ Handles **heterogeneous degradation without requiring labels**  
- ✔ Effectively suppresses corrupted features and improves robustness  
- ✔ Consistent gains under severe degradation conditions  


---

## Citation

```bibtex
@article{cairnet2026,
  title={CAIR-Net: Reliability-Aware Information Routing for Robust Multimodal Object Detection under Modality Degradation},
  author={XXX},
  journal={IEEE TCSVT},
  year={2026}
}
