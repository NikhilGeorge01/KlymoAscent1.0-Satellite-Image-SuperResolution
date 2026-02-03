# KlymoAscent1.0-Satellite-Image-SuperResolution
## Overview
This project implements a **4× super-resolution pipeline for satellite imagery**
with a focus on **structural accuracy and reliability**. The goal is to enhance
low-resolution satellite images without introducing hallucinated geospatial
features such as fake roads or buildings.
---
## Approach
- CNN-based super-resolution model inspired by **SRResNet**
- Eight residual blocks with PixelShuffle upsampling
- **L1 loss** used to discourage artificial textures
- Patch-based training to preserve spatial consistency
- Conservative training strategy to avoid hallucinations
---
## Training
- Dataset: WorldStrat LR–HR satellite image pairs
- LR patch size: 25 × 25
- HR patch size: 100 × 100 (4× scale)
- Optimizer: Adam (lr = 1e-4)
- Training performed on Google Colab (GPU)
---
## Results
Performance compared against bicubic interpolation:
| Metric | Bicubic | SRResNet |
|------|--------|---------|
| PSNR | 27.21 | **28.25** |
| SSIM | 0.669 | **0.699** |
Visual inspection confirms sharper structures with no hallucinated details.
---
## Unseen Data Inference
The model was evaluated on **unseen Sentinel-2 imagery** obtained from
**Google Earth Engine**, demonstrating good generalization while preserving
geospatial integrity.
---
## Reproducibility
A **Quick Restart / Demo** cell is included to load the trained model and
reproduce final results in under two minutes.
---
