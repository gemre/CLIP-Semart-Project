# Robustness of Pre-Trained CLIP for Artist Prediction Under Visual Transformations

This repository contains the code, experiments, and analysis for the project **“Robustness of Pre-Trained CLIP for Artist Predictions Under Visual Transformations”**, conducted as part of the *Applied AI Research Seminar* at the University of Amsterdam.

The project investigates how robust a **pre-trained CLIP model** is when performing **zero-shot artist attribution** on fine-art paintings under different visual transformations.

---

## 📌 Project Overview

CLIP (Contrastive Language–Image Pretraining) enables zero-shot image classification by aligning image and text embeddings in a shared representation space. While CLIP has shown strong performance on general vision–language tasks, its robustness in **fine-grained art attribution** remains underexplored.

In this project, we evaluate:
- Zero-shot artist prediction using CLIP
- The impact of **visual transformations** on prediction accuracy
- Which visual cues CLIP relies on most when identifying artists

---

## 🖼️ Dataset

We use the **SemArt dataset**, a collection of European fine-art paintings from the **13th to 19th century**, originally developed by Aston University.

After data cleaning:
- **20,798 paintings**
- **3,253 artists**
- Evaluation focused on the **top 100 most prolific artists**

Metadata includes:
- Artist (author)
- Artwork type
- School (origin country)
- Timeframe
- Technique

---

## 🤖 Model

- **Model:** Pre-trained CLIP (ViT-B/32)
- **Setting:** Zero-shot classification
- **Fine-tuning:** None
- **Prompt format:**  
  `"a painting by [artist name]"`

Artist prediction is performed by selecting the artist whose text embedding has the **highest cosine similarity** with the image embedding.

---

## 🔁 Visual Transformations

To assess robustness, three transformations were applied **only to paintings correctly classified in the baseline setting**:

1. **Grayscale Transformation**  
   Removes color information to test reliance on chromatic cues.

2. **Random Perspective Transformation**  
   Applies geometric distortions to simulate viewpoint and framing changes.

3. **Elastic Transformation**  
   Introduces non-rigid, local deformations to test sensitivity to fine-grained geometry.

Each transformation alters visual appearance while preserving semantic content.

---

## 📊 Key Results

### Baseline (No Transformation)
- **Accuracy:** 29.56%
- **Macro F1-score:** 0.23
- **Correct predictions:** 2,339 / 7,913 paintings
- Predictions span **76 artists**

### Post-Transformation Robustness  
(Computed on the 2,339 correctly classified paintings)

| Transformation | Accuracy |
|---------------|----------|
| Grayscale     | 65.3%    |
| Random Perspective | 59.9% |
| Elastic       | 40.2%    |

**Key findings:**
- CLIP is most robust to **color removal**
- Performance degrades under **geometric distortions**
- **Elastic transformations** have the strongest negative impact
- Confidence scores do not always align with prediction correctness

---

## 🧠 Conclusions

- Pre-trained CLIP shows **moderate zero-shot performance** for artist attribution
- CLIP relies more on **structural and compositional features** than color
- Non-rigid distortions significantly degrade performance
- Robustness varies strongly across artists

These findings highlight limitations of CLIP for fine-grained art attribution and motivate future work on task-specific fine-tuning and robustness-aware training.

---

## ⚠️ Limitations

- Limited computational resources
- Transformations applied only to correctly predicted samples
- No fine-tuning or prompt optimization
- Evaluation focuses on robustness rather than full multi-class performance

---


## 📄 Report

The full academic report (LNCS format) is available in the repository

## 👥 Authors

- **Shaoxuan Shi**
- **Emre Genç**
- **Linh Khanh Nguyen**
- **Bedirhan Gursoy**

University of Amsterdam

---

## 📜 License & Disclaimer

This repository is for **academic and research purposes only**.  
All artworks belong to their respective rights holders.  
CLIP is used under its original license.
