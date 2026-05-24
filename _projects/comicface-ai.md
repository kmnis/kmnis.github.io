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

comicface.ai is a generative computer-vision project for turning portrait photos into comic-style faces. It focuses on a clear image-to-image task: preserve the face structure while changing the visual style.

The project compares two approaches to the same problem: a convolutional variational autoencoder and a Pix2Pix GAN. It also includes a Hugging Face demo so the model can be tried interactively.

### What comicface.ai Does

- Converts face images into comic-style versions.
- Uses a paired dataset of real and comic-style synthetic faces.
- Compares CVAE and Pix2Pix-style image translation approaches.
- Includes training progress GIFs and sample generated outputs.
- Provides a Hugging Face Space for interactive use.

### Dataset

The project uses a Kaggle dataset with 10,000 paired face/comic images. Each pair gives the model both the source portrait and the desired comic-style target, which makes it suitable for supervised image-to-image translation.

This paired setup is especially useful for Pix2Pix, where the model learns a mapping from one visual domain to another rather than generating images from scratch.

### Models

The convolutional VAE explores a reconstruction-based approach: compress the face image into a latent representation, then decode it into a stylized output. This can capture broad structure, but may produce softer or less detailed results.

Pix2Pix frames the task as conditional generation. A generator creates the comic-style image while a discriminator pushes the output toward sharper, more realistic comic-domain examples. The repository includes architecture diagrams, training notebooks, inference notebooks, and saved training progress.

### Results

The sample results show the difference between the two modeling approaches. The VAE gives a useful baseline for reconstruction and style transformation, while Pix2Pix is better suited for the paired translation setting and sharper visual outputs.

### Limitations

The output quality depends heavily on the paired training data. A model trained on synthetic comic faces may not generalize equally well to every lighting condition, pose, face shape, or photo style. Like most image-generation systems, it also needs careful handling if used with real personal photos.
