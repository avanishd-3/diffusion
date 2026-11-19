# Latent Diffusion on CelebA

This repo implements a DiT-based conditional flow model heavily inspired by Stable Diffusion 3.

Our image generation pipeline has two main components: 

1. A variational autoencoder (VAE) trained to encode 128×128 RGB CelebA images into a compact 16-channel, 16×16 latent space

2. A diffusion transformer (DiT) trained with classifier-free guidance to model the distribution of those latent codes conditioned on CelebA's 40 binary facial attributes (we do not use a text encoder to save on compute). At inference time, the DiT generates latent samples which are decoded by the VAE back to full-resolution faces.

**Note**: the images folder is just for images that appear in the notebook. It does not have any significance on its own.

## References

### Foundational

1. [High-Resolution Image Synthesis with Latent Diffusion Models](https://arxiv.org/abs/2112.10752) -> Latent Diffusion Model paper (April 2022)
2. [Scalable Diffusion Models with Transformers](https://arxiv.org/abs/2212.09748) -> DiT paper (March 2023)
3. [Flow Straight and Fast: Learning to Generate and Transfer Data with Rectified Flow](https://arxiv.org/abs/2209.03003) -> Rectified Flow paper (Sep 2022)

### Modern Diffusion Techniques
1. [Scaling Rectified Flow Transformers for High-Resolution Image Synthesis](https://arxiv.org/abs/2403.03206) -> Stable Diffusion 3 paper (March 2024)
2. [Z-Image: An Efficient Image Generation Foundation Model with Single-Stream Diffusion Transformer](https://arxiv.org/abs/2511.22699) -> Z-Image paper (Jul 2026)

### Improving VAE
1. [The Unreasonable Effectiveness of Deep Features as a Perceptual Metric](https://arxiv.org/abs/1801.03924) -> LPIPS paper (April 2018)
2. [Image-to-Image Translation with Conditional Adversarial Networks](https://arxiv.org/abs/1611.07004) -> PatchGAN paper (Nov 2018)
3. [Hierarchical Implicit Models and Likelihood-Free Variational Inference](https://arxiv.org/abs/1702.08896) -> Hinge Loss Paper (Nov 2017)
4. [EQ-VAE: Equivariance Regularized Latent Space for Improved Generative Image Modeling](https://arxiv.org/abs/2502.09509) -> EQ-VAE paper (Aug 2025)

### Other
1. [RoFormer: Enhanced Transformer with Rotary Position Embedding](https://arxiv.org/abs/2104.09864) -> RoPE paper
