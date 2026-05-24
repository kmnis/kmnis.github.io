---
layout: project
title: Neural Style Transfer
subtitle: Real-time style transfer with AdaIN
summary: "An Adaptive Instance Normalization style-transfer implementation with TensorFlow and PyTorch, VGG perceptual losses, encoder-decoder networks, and training visualizations."
year: "2023-2026"
status: "Open source implementation"
project_sort_order: 5
permalink: /projects/style-transfer
repo_url: https://github.com/kmnis/style-transfer
image: /_images/projects/style-transfer.png
image_alt: "Sample content image for neural style transfer"
image_background: "linear-gradient(180deg, #DBE0EB 0%, #D4DCE6 55%, #D0D8E1 100%)"
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
  - Adaptive Instance Normalization implementation for arbitrary image style transfer.
  - VGG-based perceptual loss network for balancing content preservation and style matching.
  - Training, monitoring, and GIF-generation utilities around an encoder-decoder model.
collaborators:
  - name: Manish Kumar
    url: https://www.linkedin.com/in/kmnis/
related_projects:
  - comicface-ai
  - automatic-essay-grading
  - docscribe
---

This neural style transfer project implements the AdaIN approach for transferring the style of one image onto the content structure of another. The goal is real-time arbitrary style transfer: preserve the semantic layout of the content image while matching the feature statistics of a style reference.

The implementation includes TensorFlow/Keras and PyTorch components, an encoder-decoder architecture, a VGG-based perceptual loss network, and a training pipeline with monitoring callbacks.

### Technical Shape

The README documents a 30-epoch training setup with Adam, mean squared error objectives, a style weight of 4.0, and visual training output at each epoch. The repository also includes a `localtoon` variant that experiments with a StyleGAN2-based cartoonization direction.

### Why It Matters

Style transfer is a useful bridge between classical computer vision intuition and generative image systems: it makes feature representations, perceptual loss, and image reconstruction easy to inspect visually.
