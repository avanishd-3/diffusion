# Latent Diffusion on CelebA

This repo implements a DiT-based conditional flow model heavily inspired by Stable Diffusion 3.

Our image generation pipeline has two main components: 

1. A variational autoencoder (VAE) trained to encode 128×128 RGB CelebA images into a compact 16-channel, 16×16 latent space

2. A diffusion transformer (DiT) trained with classifier-free guidance to model the distribution of those latent codes conditioned on CelebA's 40 binary facial attributes (we do not use a text encoder to save on compute). At inference time, the DiT generates latent samples which are decoded by the VAE back to full-resolution faces.

## References

Patrick Esser et al. 2024. [Scaling Rectified Flow Transformers for High-Resolution Image Synthesis](https://arxiv.org/abs/2403.03206). Preprint, arXiv:2403.03206.

Xingchao Liu, Chengyue Gong, and Qiang Liu. 2022. [Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow](https://arxiv.org/abs/2209.03003). Preprint, arXiv:2209.03003. 

William Peebles and Saining Xie. 2023. [Scalable Diffusion Models with Transformers](https://arxiv.org/abs/2212.09748). Preprint, arXiv:2212.09748.

Robin Rombach, Andreas Blattmann, Dominik Lorenz, Patrick Esser, and Björn Ommer. 2022. [High-Resolution Image Synthesis with Latent Diffusion Models](https://arxiv.org/abs/2112.10752). Preprint, arXiv:2112.10752.

Richard Zhang, Phillip Isola, Alexei A. Efros, Eli Shechtman, and Oliver Wang. 2018. [The Unreasonable Effectiveness of Deep Features as a Perceptual Metric](https://arxiv.org/abs/1801.03924). Preprint, arXiv:1801.03924.

Z-image Team et al. 2025. [Z-Image: An Efficient Image Generation Foundation Model with Single-Stream Diffusion Transformer](https://arxiv.org/abs/2511.22699). Preprint, arXiv:2511.22699.
