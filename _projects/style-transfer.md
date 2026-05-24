---
layout: project
title: Neural Style Transfer
subtitle: Real-time style transfer with AdaIN
summary: "An Adaptive Instance Normalization style-transfer implementation with TensorFlow and PyTorch, VGG perceptual losses, encoder-decoder networks, and training visualizations."
year: "2023-2026"
status: "Open source implementation"
role: "Model architecture, training workflow, and evaluation"
project_sort_order: 5
permalink: /projects/style-transfer
repo_url: https://github.com/kmnis/style-transfer
image: /_images/projects/style-transfer.png
image_alt: "Sample content image for neural style transfer"
image_background: "linear-gradient(180deg, #DBE0EB 0%, #D4DCE6 55%, #D0D8E1 100%)"
github_stars: 0
github_forks: 0
tech_stack:
  - Python
  - TensorFlow
  - PyTorch
  - AdaIN
  - VGG loss
  - CUDA
tags:
  - computer-vision
  - style-transfer
  - deep-learning
  - pytorch
highlights:
  - Implemented Adaptive Instance Normalization for arbitrary image style transfer.
  - Used a VGG-based perceptual loss network to balance content and style preservation.
  - Built training, monitoring, and GIF-generation utilities around an encoder-decoder model.
collaborators:
  - name: Manish Kumar
    url: https://www.linkedin.com/in/kmnis/
gallery:
  - url: https://raw.githubusercontent.com/kmnis/style-transfer/main/data/sample/hp.jpg
    alt: "Sample content image for style transfer"
  - url: https://raw.githubusercontent.com/kmnis/style-transfer/main/data/sample/hp2.jpg
    alt: "Second sample content image for style transfer"
  - url: https://raw.githubusercontent.com/kmnis/style-transfer/main/data/sample/William_Turner_16.jpg
    alt: "William Turner style reference image"
related_projects:
  - comicface-ai
  - automatic-essay-grading
  - docscribe
---

This neural style transfer project implements the AdaIN approach for transferring the style of one image onto the content structure of another. The goal is real-time arbitrary style transfer: preserve the semantic layout of the content image while matching the feature statistics of a style reference.

The implementation includes TensorFlow/Keras and PyTorch components, an encoder-decoder architecture, a VGG-based perceptual loss network, and a training pipeline with monitoring callbacks.

### What I Worked On

- Built the model architecture around encoder features, decoder reconstruction, and AdaIN statistics matching.
- Implemented content and style loss terms using VGG feature representations.
- Added training utilities, validation hooks, visualization callbacks, and GIF generation for monitoring.

### Technical Shape

The README documents a 30-epoch training setup with Adam, mean squared error objectives, a style weight of 4.0, and visual training output at each epoch. The repository also includes a `localtoon` variant that experiments with a StyleGAN2-based cartoonization direction.

### Why It Matters

Style transfer is a useful bridge between classical computer vision intuition and generative image systems: it makes feature representations, perceptual loss, and image reconstruction easy to inspect visually.
