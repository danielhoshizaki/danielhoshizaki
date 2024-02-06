---
layout: post
title:  "Manufactured Landscapes"
name:  "Daniel Hoshizaki"
image:
  path: /assets/images/diffusion/sd-banner_2.jpg
  thumbnail: /assets/images/diffusion/sd-banner_2.jpg
categories: [Remote Sensing, Deep Learning]
---

Generative techniques like StableDiffusion have been out for a while and are starting to make their way into the field of remote sensing. I thought I'd give these models a try and see what the hype was all about. From my very brief experiments, I can say two things: one, I'm not entirely sold on the utility of generative models for real world applications; two, these models make interesting and abstract art that resembles remote sensing imagery. Until these models and their supporting ecosystem develop further to allow practical application development, I'm content toying with these models to generate interesting art pieces.

## Base Knowledge

Interestingly, pretrained StableDiffusion (SD) models have a built in understanding of satellite imagery. These models are pretrained on LAION-5B, which includes both [captioned arial and satellite imagery](https://arxiv.org/pdf/2309.15535.pdf). I asked SD1.5 and SDXL to create "satellite images of mountains," and this is what they produced:

<p align="center">
  <img src="/assets/images/diffusion/xl_beach.png" width="512" height="512"/>
</p>
<p align="center">
  <figcaption>Finetuned SD1.5</figcaption>
</p>
<p align="center">
  <img src="/assets/images/diffusion/xl_beach.png" width="512" height="512"/>
</p>
<p align="center">
  <figcaption>Finetuned SDXL</figcaption>
</p>

Not too bad for models with no finetuning. I found SD1.5 to be fairly opinionated and using the influence of the other training images to increase the contrast and colors of generated satellite images. Being a bigger model, SDXL appears to have a better base knowledge of satellite images and doesn't force as much stylization as 1.5.

## Finetuning

I wanted to see if finetuning these models on a remote sensing dataset would yield anything different or, hopefully, better. I took a similar approach as [this article](https://www.reasonfieldlab.com/post/generative-ai-and-remote-sensing-imagery) and used part of the AID dataset to finetune on a single class: satellite images of mountains. I stuck to LoRA finetuning since I only had a plebe graphics card with limited memory. As a result, I only saw small modifications to the model outputs, due to the limited amount of influence LoRAs are designed to exert on the base network. Here are the images generated using the same seed as the examples from above:

<p align="center">
  <img src="/assets/images/diffusion/xl_beach.png" width="512" height="512"/>
</p>
<p align="center">
  <figcaption>Finetuned SD1.5</figcaption>
</p>
<p align="center">
  <img src="/assets/images/diffusion/xl_beach.png" width="512" height="512"/>
</p>
<p align="center">
  <figcaption>Finetuned SDXL</figcaption>
</p>

I'm not seeing a whole lot of difference from the baseline models. There may be hyperparmeter tweeks that would allow for larger LoRA influence, but I wasn't able to find them during my limited experiments. At this point, the capability of the models are largely determined by the original training dataset. Using a larger dataset and fully retraining the models would probably lead to the larger output changes I was initially hoping for.

## Final Thoughts
As I experimented with finetuning SD, I found myself wondering about the potential applications of generative models for the field of remote sensing. One thing that is immediately clear to me is that there is still a significant barrier to achieving reliable outputs that would serve a meaningful purpose in production environments. Synthetic data is only as good as training data used to create the generator model. To get really good results, a LOT of data is needed. I would argue that high quality labeled data is better used for directly training a model for a specific task or application, rather than using the data to train a generator. Even though the [outputs of SD variants can be impressive and realistic](https://arxiv.org/pdf/2312.03606.pdf), I still don't see what this generated imagery would be really used for. What am I going to do or make with more images of roads and stadiums?

I'm confident these models will get better in the future and I may even be proven wrong that more images of roads are, in fact, better for training models. In the meantime, the effort used to train and customize these models is probably better used on curating high quality datasets for much smaller models that can accomplish a specific task reliably. Until the generative landscape makes another tectonic shift, I'll be using these models for what they are best at: making art.

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
  <figcaption>The abstract art of manufactured landscapes</figcaption>
</p>
