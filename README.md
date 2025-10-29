# BCMEM: An Exploration of Number-Theoretic Priors for Structured Representation Learning

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![PyTorch](https://img.shields.io/badge/PyTorch-Framework-EE4C2C.svg)](https://pytorch.org/)
[Paper](/bcmem_icaa.pdf)
This repository contains the official PyTorch implementation for BCMEM, an independent research project exploring the use of number-theoretic priors for structured representation learning.

---

## 1. Core Idea

Traditional deep learning methods learn representations in high-dimensional, unstructured latent spaces. This project investigates whether incorporating algebraic constraints from number theory—specifically, the composition laws of quadratic forms as described by Manjul Bhargava's cubes—can serve as a principled inductive bias.

The core of this work is a **differentiable auxiliary loss function**. This loss operates independently of the primary classification objective and penalizes the model for violating these algebraic relationships. The goal is to guide the model toward learning a latent space that is not just effective for a task, but also possesses a consistent, verifiable mathematical structure.

![3D Bhargava Cube Embeddings](/bhargava_cube_3d_visualization.png)
_**Figure 1:** 3D embeddings of MNIST test samples. The clustered structure is an emergent property of the algebraic regularization loss, demonstrating that the model has learned an organized, interpretable manifold._

## 2. Results of the Experiment

This framework was tested on the MNIST benchmark as a proof-of-concept. The primary results were:

-   **Classification Accuracy:** The model achieves **99.46%** accuracy on the held-out test set.
-   **Structured Latent Space:** As shown above, the model successfully learns a low-dimensional, interpretable manifold where classes are well-separated.
-   **Algebraic Consistency:** The learned embeddings were shown to satisfy the imposed quadratic constraints, validating the effectiveness of the auxiliary loss.

## 3. Project Context & Key Takeaway

This was an early, independent research project driven by my interest in the intersection of pure mathematics and machine learning.

While the experiment was successful on its own terms, its most valuable outcome was the lesson it provided in research methodology. Validating an idea on a controlled environment like MNIST is a necessary first step, but proving the true value of a new architectural idea requires rigorous testing on more complex, large-scale benchmarks.

This realization has directly shaped my current research focus on developing scalable, robust, and empirically-validated machine learning systems.

## 5. Project Status & Peer Review

A paper formalizing this study was submitted for peer review. The feedback received provided a clear roadmap for future improvements, particularly concerning large-scale validation beyond the MNIST benchmark.

To pursue this more rigorous direction and incorporate the expert feedback from the review process, the paper has been withdrawn from publication to undergo a comprehensive rework. The core code for the original proof-of-concept remains available in this repository for archival purposes.
