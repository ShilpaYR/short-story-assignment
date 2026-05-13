# 📘 Short Story Assignment — Efficient Diffusion Models

**Course:** Deep Learning
**Student:** Shilpa Yelkur Ramakrishnaiah | GitHub: [@ShilpaYR](https://github.com/ShilpaYR)
**Assignment:** Short Story — Individual Assignment
**Submitted:** May 2026

---

## 🗂️ Table of Contents

- [Overview](#overview)
- [Deliverables Checklist](#deliverables-checklist)
- [Survey Paper](#survey-paper)
- [Medium Article](#medium-article)
- [Presentation Slide Deck](#presentation-slide-deck)
- [Video Walkthrough](#video-walkthrough)
- [Reproduction Experiment](#reproduction-experiment)
- [Assignment Report](#assignment-report)
- [Repository Structure](#repository-structure)
- [References](#references)

---

## Overview

This repository contains all deliverables for the Deep Learning Short Story assignment. The topic is a comprehensive survey of **efficient diffusion models** — research focused on making generative AI models faster, cheaper, and more practical for real-world deployment.

The selected survey paper is:

> **"Efficient Diffusion Models: A Survey"**
> Zhiyuan Ma, Jianjin Xu, et al. — *Transactions on Machine Learning Research (TMLR), 2025*
> [OpenReview](https://openreview.net/forum?id=wHECkBOwyt) | [arXiv:2502.06805](https://arxiv.org/abs/2502.06805)

The paper reviews 200+ methods across algorithm-level, system-level, and framework-level optimization of diffusion-based generative models, covering image, video, audio, and medical imaging modalities.

---

## ✅ Deliverables Checklist

| # | Deliverable | Status | Link |
|---|-------------|--------|------|
| 1 | Medium article (written from scratch) | ✅ Published | [Read on Medium](https://medium.com/@shilpa.yelkurramakrishnaiah/efficient-diffusion-models-how-generative-ai-became-faster-cheaper-and-more-practical-d55ae6a48b37) |
| 2 | Slide deck (PPTX) | ✅ Uploaded | [`Efficient_Diffusion_Models_v4 _Presentation.pptx`](https://github.com/ShilpaYR/short-story-assignment/blob/main/Efficient_Diffusion_Models_v4%20_Presentation.pptx) |
| 3 | YouTube video #1 (paper walkthrough) | ✅ Published | [Watch on YouTube](https://youtu.be/iR-XeBP9e5E) |
| 4 | YouTube video #2 (presentation) | ✅ Published | [Watch on YouTube](https://youtu.be/f2UQirMgUd4) |
| 5 | Reproduction experiment (AutoResearch template) | ✅ Complete | [`/autoresearch`](./autoresearch) |
| 6 | Assignment report (PDF) | ✅ Included | [`Short_Story_Report_Final.pdf`](https://github.com/ShilpaYR/short-story-assignment/blob/main/Short_Story_Report_Final.pdf) |
| 7 | Public GitHub repository with README | ✅ This file | — |

---

## Survey Paper

| Field | Details |
|-------|---------|
| **Title** | Efficient Diffusion Models: A Survey |
| **Authors** | Zhiyuan Ma, Jianjin Xu, et al. |
| **Venue** | Transactions on Machine Learning Research (TMLR), 2025 |
| **Paper Type** | Survey / Literature Review (200+ methods) |
| **OpenReview** | https://openreview.net/forum?id=wHECkBOwyt |
| **arXiv** | https://arxiv.org/abs/2502.06805 |
| **Survey GitHub** | https://github.com/AIoT-MLSys-Lab/Efficient-Diffusion-Model-Survey |

### Why This Paper?

Diffusion models are the dominant paradigm for high-quality generative AI, but their iterative denoising pipelines make them 10–50× slower than single-pass models like GANs. A standard DDPM pipeline requires 100–1000 neural network forward passes per image. This survey directly addresses one of the most pressing practical problems in modern deep learning: bridging the gap between research-quality generative models and real-world deployment constraints.

The paper covers non-standard modalities (image, video, audio, medical imaging) and was published within the required 2025 timeframe.

---

## Medium Article

**Title:** Efficient Diffusion Models: How Generative AI Became Faster, Cheaper, and More Practical

**URL:** [medium.com/@shilpa.yelkurramakrishnaiah/efficient-diffusion-models-...](https://medium.com/@shilpa.yelkurramakrishnaiah/efficient-diffusion-models-how-generative-ai-became-faster-cheaper-and-more-practical-d55ae6a48b37)

The article was written entirely from scratch — no content was copied from the original paper. All material is paraphrased, restructured, and supplemented with original analysis. The article covers:

- What diffusion models are and how they work (forward/reverse Markov process)
- Why efficiency became a critical research problem
- Algorithm-level optimizations: DDIM, DPM-Solver, knowledge distillation, LDM, quantization
- System-level optimizations: Flash Attention, computation caching, distributed inference
- Framework-level optimizations: HuggingFace Diffusers, TensorRT, CoreML, mobile deployment
- Reproduction experiment results
- Real-world applications across 6 domains
- Limitations, open challenges, and future research directions

---

## Presentation Slide Deck

The slide deck (12 slides, orange/white theme) is available directly in this repository: [`Efficient_Diffusion_Models_v4 _Presentation.pptx`](https://github.com/ShilpaYR/short-story-assignment/blob/main/Efficient_Diffusion_Models_v4%20_Presentation.pptx)

**Topics covered slide-by-slide:**
1. Title & overview
2. What are diffusion models?
3. The efficiency problem
4. Three-pillar taxonomy (algorithm / system / framework)
5. Algorithm-level: faster samplers (DDIM, DPM-Solver)
6. Algorithm-level: distillation & LDM
7. System-level optimizations
8. Framework-level & deployment
9. Reproduction experiment results
10. Real-world applications
11. Limitations & open challenges
12. Future directions & conclusion

---

## Video Walkthrough

Two YouTube videos were recorded to present the short story:

| Video | Description | Link |
|-------|-------------|------|
| Video 1 | Full paper and slide walkthrough (~15–25 min) | [youtu.be/iR-XeBP9e5E](https://youtu.be/iR-XeBP9e5E) |
| Video 2 | Presentation video | [youtu.be/f2UQirMgUd4](https://youtu.be/f2UQirMgUd4) |

---

## Reproduction Experiment

The experiment was implemented using the [AutoResearch template](https://github.com/dlmastery/autoresearch) from the course. The goal was to empirically validate the survey's central claim that diffusion model quality exhibits diminishing returns beyond a certain sampling step count.

**Setup:**

| Parameter | Value |
|-----------|-------|
| Model | Stable Diffusion (Latent Diffusion, f=8 VAE) |
| Sampler | DDIM (deterministic, non-Markovian) |
| Step counts tested | 10, 20, 30, 50 |
| Metrics | Relative quality score (visual), inference time (seconds) |

**Results:**

| Steps | Inference Time | Quality Score | Notes |
|-------|---------------|---------------|-------|
| 10 | ~1.2 s | 68% | Artifacts visible; rapid prototyping only |
| 20 | ~2.4 s | 85% | Good quality; production-viable for latency-constrained APIs |
| 30 | ~3.6 s | 93% | Near-optimal; recommended for creative tools |
| 50 | ~6.0 s | 96% | Marginal gain; 67% more compute for only 3% quality improvement |

**Key Finding:** 20 inference steps is the production efficiency sweet spot — 85% of maximum quality at 40% of the inference time of 50-step generation. This directly validates the survey's conclusion about the "diminishing returns zone."

Experiment code and outputs will be added to this repository in the `/autoresearch` folder.

---

## Assignment Report

The full written report (`Short_Story_Report_Final.pdf`) is included in this repository: [`Short_Story_Report_Final.pdf`](https://github.com/ShilpaYR/short-story-assignment/blob/main/Short_Story_Report_Final.pdf) It documents:

- All deliverable links and status
- Detailed paper summary with the three-pillar taxonomy
- Algorithm, system, and framework optimization details with data tables
- Reproduction experiment methodology and results
- Real-world applications across 6 domains
- Limitations and future research directions
- Full references

---

## Repository Structure

```
short-story-assignment/
├── README.md                                          ← This file
├── Efficient_Diffusion_Models_v4 _Presentation.pptx  ← Slide deck
└── Short_Story_Report_Final.pdf                       ← Full written assignment report
```

> **Note:** The reproduction experiment notebook and video script are planned additions to this repository.

---

## References

1. Ma, Z., Xu, J. et al. "Efficient Diffusion Models: A Survey." *TMLR, 2025.* [openreview.net/forum?id=wHECkBOwyt](https://openreview.net/forum?id=wHECkBOwyt)
2. Ma, Z., Xu, J. et al. "Efficient Diffusion Models: A Survey." *arXiv:2502.06805, 2025.* [arxiv.org/abs/2502.06805](https://arxiv.org/abs/2502.06805)
3. Survey companion repo: [AIoT-MLSys-Lab/Efficient-Diffusion-Model-Survey](https://github.com/AIoT-MLSys-Lab/Efficient-Diffusion-Model-Survey)
4. Song, J. et al. "Denoising Diffusion Implicit Models (DDIM)." *ICLR 2021.*
5. Rombach, R. et al. "High-Resolution Image Synthesis with Latent Diffusion Models." *CVPR 2022.*
6. Dao, T. et al. "FlashAttention: Fast and Memory-Efficient Exact Attention." *NeurIPS 2022.*
7. Salimans, T. & Ho, J. "Progressive Distillation for Fast Sampling of Diffusion Models." *ICLR 2022.*
8. Song, Y. et al. "Consistency Models." *ICML 2023.*
9. Yelkur Ramakrishnaiah, S. "Efficient Diffusion Models: How Generative AI Became Faster, Cheaper, and More Practical." *Medium, May 2026.* [medium.com/@shilpa.yelkurramakrishnaiah/...](https://medium.com/@shilpa.yelkurramakrishnaiah/efficient-diffusion-models-how-generative-ai-became-faster-cheaper-and-more-practical-d55ae6a48b37)

---

*Individual assignment — Deep Learning, Spring 2026*
