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

Neural Style Transfer is an implementation of arbitrary image style transfer using Adaptive Instance Normalization. The goal is to combine the content of one image with the visual style of another while keeping the output recognizable and coherent.

The project includes TensorFlow/Keras and PyTorch components, an encoder-decoder network, a VGG-based perceptual loss network, and utilities for training visualization.

### What The Project Does

- Transfers style from a reference image onto a content image.
- Uses Adaptive Instance Normalization to match feature statistics between content and style.
- Preserves content structure through a perceptual content loss.
- Encourages style matching through feature-statistic losses.
- Tracks training progress with visual callbacks and generated GIFs.

### Model Architecture

The model follows an encoder-decoder structure. The encoder extracts feature representations from the content and style images. AdaIN adjusts the content features so their channel-wise statistics match the style features. The decoder then reconstructs an image from the adjusted representation.

A VGG-based loss network is used to measure whether the output preserves content structure while adopting the texture, color, and pattern characteristics of the style image.

### Training Workflow

The README documents a 30-epoch training setup using Adam with a low learning rate, mean squared error objectives, and a style-weighted loss. The training monitor visualizes the style image, content image, and generated output over time, which makes model progress easier to inspect.

The repository also includes a `localtoon` variant that experiments with a StyleGAN2-based cartoonization direction.

### Results

Style transfer is visually interpretable: the output can be judged by whether the content layout remains recognizable while the style reference influences color, brush texture, and pattern. The project includes sample images and utilities for creating animated outputs from training progress.

### Limitations

Style transfer models can struggle when the content and style images are very different in structure, texture density, or color distribution. The output is also sensitive to loss weights and training data, so visual quality often requires experimentation rather than a single universal setting.
