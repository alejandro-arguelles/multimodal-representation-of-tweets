# multimodal-representation-of-tweets
Experiment attempting to improve the multimodal architecture of the paper "Multimodal representations of biomedical knowledge from limited training whole slide images and reports using deep learning" by Marini et al. (2024). 

Aquí tienes un **README corto, directo, sin tono de IA, sin florituras**, explicando qué hace tu experimento, en qué trabajo se inspira y cómo configurar la API de Kaggle. Está escrito como lo pondría un estudiante/ingeniero que documenta un experimento interno.

---

# Multimodal MVSA-Single Experiment (Baseline vs Rigid-Givens)

This repository contains a modified multimodal experiment inspired by the architecture analysed in the report *“Analysis of Multimodal Representations of Biomedical Knowledge From Limited Data”* .
The original paper focuses on multimodal image–text alignment (WSI + pathology reports).
Here, the same general idea is applied to a simpler public dataset: **MVSA-Single** (sentiment analysis with image + tweet).

The experiment trains and compares two models:

1. **Baseline**: ResNet18 + BERT-tiny projected into a shared 128-D space.
2. **Rigid-Givens**: Same model, but the text embedding goes through a lightweight, learnable rigid transform (a few Givens rotations + translation).

Training uses a joint multimodal loss combining classification, NT-Xent, L1 and cosine alignment terms.
Cross-validation (10 folds) is performed, and results are compared with a paired t-test.

All metrics, plots and logs are written to `./results/`.

---

## Dataset: MVSA-Single (Kaggle)

The code automatically downloads the dataset *if and only if* a valid Kaggle API key is configured.

### How to set up the Kaggle API key (required)

1. Go to [https://www.kaggle.com](https://www.kaggle.com)
2. Click on your profile → **Settings**
3. Scroll down to **API** → **Create New API Token**
4. This downloads a file called **`kaggle.json`**
5. In Colab, the script will ask you to upload it when missing.
   Alternatively, place it manually in:

~/.kaggle/kaggle.json





Si quieres, te escribo también una versión más formal, una más breve todavía o una versión estilo “paper supplement”.

