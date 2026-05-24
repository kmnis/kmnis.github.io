---
layout: project
title: comicface.ai
subtitle: Photo-to-comic generation with CVAE and Pix2Pix
summary: "A generative vision project that turns portraits into comic-style images using paired face/comic data, a convolutional VAE, and a Pix2Pix GAN."
year: "2023"
status: "Demo prototype"
project_sort_order: 3
permalink: /projects/comicface-ai
repo_url: https://github.com/kmnis/comicface.ai
demo_url: https://huggingface.co/spaces/kmnis/comicface.ai
image: /_images/projects/comicface-ai-project-image.png
image_alt: "Pix2Pix comic face generation results"
image_background: "linear-gradient(180deg, #5BC7F3 0%, #55C0EF 55%, #5BC2EF 100%)"
tech_stack:
  - Python
  - Pix2Pix
  - GANs
  - Convolutional VAE
  - Hugging Face Spaces
tags:
  - generative-ai
  - computer-vision
  - gan
  - image-generation
highlights:
  - Portrait-to-comic translation using 10,000 paired face and comic images from a synthetic Kaggle dataset.
  - Side-by-side exploration of a convolutional variational autoencoder and a Pix2Pix GAN.
  - Interactive Hugging Face demo for trying the comic generation workflow.
collaborators:
  - name: Manish Kumar
    url: https://www.linkedin.com/in/kmnis/
gallery:
  - url: https://raw.githubusercontent.com/kmnis/comicface.ai/main/assets/sample-data.jpg
    alt: "Paired face and comic training examples"
  - url: https://raw.githubusercontent.com/kmnis/comicface.ai/main/saved_models/vae/training_progress/vae_training.gif
    alt: "VAE comic face training progress"
  - url: https://raw.githubusercontent.com/kmnis/comicface.ai/main/saved_models/pix2pix/training_progress/pix2pix_training.gif
    alt: "Pix2Pix comic face training progress"
related_projects:
  - style-transfer
  - zen-ai
  - docscribe
---

comicface.ai is a compact generative vision project: upload or provide a face image, and transform it toward a comic-book visual style.

The project uses a paired synthetic dataset of 10,000 face/comic examples, each at 1024 by 1024 resolution. Two modeling approaches are explored: a convolutional variational autoencoder and a Pix2Pix GAN. The repository includes training notebooks, inference notebooks, model architecture code, saved model progress GIFs, and sample outputs.

### Technical Shape

The implementation separates data loading, model networks, losses, training utilities, and app code. The notebooks document exploratory data analysis, CVAE training, Pix2Pix training, and Pix2Pix inference.

### Why It Matters

It is a focused example of applied generative AI: a clear input, a playful output, and a side-by-side look at how different neural architectures behave on the same translation task.
