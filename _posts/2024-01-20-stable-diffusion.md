---
layout: post
title:  "Stable Diffusion for Remote Sensing: Reality Check"
name:  "Daniel Hoshizaki"
image:
  path: /assets/images/diffusion/sd-banner_2.jpg
  thumbnail: /assets/images/diffusion/sd-banner_2.jpg
categories: [Remote Sensing, Deep Learning]
---

How useful are generative techniques like stable diffusion for remote sensing applications? I would argue that current versions with limited conditioning are not particularly useful. If you have enough data to train a generator, you might as well use that data directly for a target application. Unless the generator is configured for fine grained control, I don't see any practical use cases for open, prompt based remote sensing image generation.

A central problem with generated satellite imagery is the lack of predictability in the output. For one, prompt engineering for regular stable diffusion art is an iterative process 

All what said, however, stable diffusion trained on remote sensing data is great for one thing: making artistic satellite images. 

<p align="center">
  <img src="/assets/images/diffusion/river1.jpg" />
</p>
<p align="center">
  <img src="/assets/images/diffusion/sd3.jpg" />
</p>
<p align="center">
  <img src="/assets/images/diffusion/sd6.jpg" />
</p>
<p align="center">
  <img src="/assets/images/diffusion/sd9.jpg" />
</p>
