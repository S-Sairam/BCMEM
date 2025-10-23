# Bhargava Cube-Inspired Quadratic Regularization for Structured Neural Embeddings

[![Paper](https://img.shields.io/badge/Paper-arXiv:XXXX.XXXXX-b31b1b.svg)](https://arxiv.org/abs/XXXX.XXXXX) <!-- Replace with your arXiv link -->
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This repository contains the official PyTorch implementation and research artifacts for the paper "Bhargava Cube-Inspired Quadratic Regularization for Structured Neural Embeddings."

---

## Overview

This project presents a novel approach to neural representation learning that incorporates algebraic constraints inspired by **Bhargava cubes** from algebraic number theory. Traditional deep learning methods often learn representations in unstructured latent spaces, lacking interpretability and mathematical consistency. Our framework addresses this by mapping input data to a constrained 3-dimensional latent space where embeddings are regularized to satisfy learned quadratic relationships.

This research was a formal endeavor to move beyond applying existing tools and to explore, from first principles, whether deep, abstract mathematical structures could serve as effective inductive biases for building more structured and interpretable AI systems.

## The Core Idea: An Inductive Bias from Number Theory

The central hypothesis of this work is that the structural principles of high-level mathematics can provide a powerful new source of regularization for deep learning.
*   **The Problem:** Standard neural networks learn a chaotic, high-dimensional "filing cabinet" for data, which is effective but uninterpretable.
*   **Our Approach:** We aimed to force the network to learn a "crystal lattice"—a latent space with an inherent, mathematically consistent geometric structure.
*   **The Tool:** We used the formalism of Bhargava cubes, which encode profound relationships between quadratic forms, as the basis for a novel, differentiable auxiliary loss function. This loss function "guides" the learned embeddings to align with these number-theoretic constraints.

## Architecture & Methodology

The model, BCMEM (Bhargava Cube-based Memory Embedding Model), is an encoder-regularization framework with three key stages:
1.  **Encoder:** A series of fully connected layers that map an input image (e.g., MNIST) to a point in a 3D latent space, `z = (z1, z2, z3)`.
2.  **Quadratic Regularization:** A novel, differentiable auxiliary loss function (`L_quad`) that penalizes the latent representation `z` if it violates the discriminant consistency laws inspired by Bhargava cube compositions. This loss operates independently of the main classification task.
3.  **Classifier:** A standard classification head that predicts the final class label from the latent representation `z`.

The total training objective is `L_total = L_task + λ * L_quad`, balancing empirical accuracy with algebraic consistency.

## Results & Key Findings

*   **Performance:** On the MNIST benchmark, the model achieves a competitive **99.46%** classification accuracy.
*   **Structured Representation:** More importantly, the algebraic regularization forces the emergence of a highly structured and interpretable latent space. As shown below, the 3D embeddings for the MNIST test set naturally form distinct, well-separated clusters according to their digit class. This geometric structure is an **emergent property** of the algebraic constraints, not a result of direct geometric supervision.

![3D Bhargava Cube Embeddings](3d_embeddings.png)
*Figure 1: 3D embeddings of MNIST test samples. Each color represents a distinct digit class, demonstrating the clean, separated manifold learned by the model.*

## Status & Lessons Learned:

This project was formalized into a research paper and submitted for peer review. While the paper was not ultimately accepted for publication at the initial venue (citing a high volume of submissions), the process and the feedback were invaluable and have become a cornerstone of our current research philosophy.

*   **Validation of Novelty:** Positive feedback from reviewers validated the core concept as a **"highly original idea"** and the **"first application of number-theoretic constructs in neural representation learning."** This confirmed that the high-risk, first-principles approach was a valid and valuable scientific direction.
*   **The Critical Lesson: Execution is Everything.** Conversely, reviewer feedback also highlighted critical weaknesses in the paper's clarity, communication, and the narrative connecting the esoteric theory to the empirical results. This project served as a **crucible.** It taught us a vital lesson: a novel idea is worthless without an equally clear, rigorous, and compelling experimental story. The gap between a good idea and good *research* lies in the brutal details of execution.
*   **Informing Future Work:** The lessons in rigor and communication learned from this project are now being directly applied to our current, more ambitious research campaigns in Causal Neuro-Symbolic AI.

## Citation

If you find this work informative, please consider citing the preprint:
```bibtex
@article{sairam2025bhargava,
  title   = {Bhargava Cube-Inspired Quadratic Regularization for Structured Neural Embeddings},
  author  = {Sairam S, Prateek P Kulkarni},
  journal = {arXiv preprint arXiv:XXXX.XXXXX},
  year    = {2025}
}
