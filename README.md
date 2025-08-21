# 🧠 EEG-to-Image Reconstruction using StyleGAN2 & Stable Diffusion

This project explores how **electroencephalography (EEG) brain signals** can be transformed into **images** using **deep unsupervised learning**. By combining **StyleGAN2** and **Stable Diffusion** models with sequence encoders, we aim to bridge the gap between neural signals and visual representations.

---

## ✨ Overview
- Developed a pipeline to reconstruct images from EEG signals.  
- Implemented both **supervised and semi-supervised learning** approaches.  
- Handled **label mismatches and missing classes** by introducing an `Unknown` category.  
- Designed and tested models in a **CPU-only environment** due to hardware constraints.  

---

## 📚 Datasets

1. **EEG-ImageNet (Kaggle)**  
   - [Kaggle Dataset Link](https://www.kaggle.com/datasets/zhannalucky/eeg-imagenet)  
   - EEG signals recorded while subjects viewed images.  
   - Used for training EEG encoders and EEG → image latent mapping.

2. **ImageNet-100**  
   - A **100-class subset** of ImageNet, widely used for faster prototyping.  
   - Supported conditional training of GANs and evaluation with a manageable label space.  
   - Required for reconstructing target images conditioned on EEG signals.

⚠️ **Note:** This repository does not redistribute datasets. Please download them from their official sources and respect licensing requirements.

---

## ⚙️ Methodology

- **EEG Preprocessing**  
  - Feature extraction and normalization of raw EEG data.  
  - Sequence modeling with **LSTMs and Transformers**.  

- **Image Generation**  
  - **StyleGAN2** for baseline image reconstruction.  
  - **Stable Diffusion** for more diverse, realistic generations.  

- **Integration**  
  - EEG encoders mapped to latent spaces of generative models.  
  - Introduced an **Unknown class** to handle mismatched EEG–ImageNet labels.  

---

## 🔬 Evaluation

We evaluated generated images against ground truth using:  
- **MS-SSIM (Multi-Scale Structural Similarity Index)** for structural similarity.  
- **CLIP Cosine Similarity** for semantic alignment between generated and target images.  

---

## 💡 Highlights of our project:

- Multi-modal AI (EEG → Vision) requires robust encoders and careful label alignment.  
- Even with hardware and data constraints, it’s possible to achieve **proof-of-concept EEG-to-Image reconstruction**.
  
## Future improvements:  
  - Larger datasets with more subjects and trials which would also ensure the calculation of FID score
  - GPU training for better convergence  
  - Stronger EEG feature extraction pipelines  

---
