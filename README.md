# Greta Thunbot Documentation

## Introduction
This document serves as a general reference for the **Greta Thunbot** generative image/text Discord bot.

Greta is activated, generally, by wake words. To trigger a response from Greta, review the individual sections below to see how to do so. 

## Image Generation Basics

Greta's image generation capabilities come from feeding text-based prompts and parameters into **Stable Diffusion** directly via the SD API.

Greta currently has multiple methods available for generating images. While each method can produce a wide range of results, and you can experiment with the same prompt on each method, you should choose based on your needs...

## Realistic Image Generation Method

To do realistic images, Greta currently utilizes the [AbsoluteReality 1.8.1](https://civitai.com/models/81458?modelVersionId=108576) model.

The wake words to activate this method are: **`greta draw me`**

For example, **`greta draw me a woman in winter`** could result in an image such as:

![image](https://github.com/xydreen/greta-thunbot/blob/64fe59b30d2077e034af37b9663f0b0f33d69608/images/realistic.main.half.png)

To generate a selfie from Greta's perspective, the wake words are: **`greta take a selfie`**

For example, **`greta take a selfie in winter`** could result in an image such as:

![image](https://github.com/xydreen/greta-thunbot/blob/64fe59b30d2077e034af37b9663f0b0f33d69608/images/realistic.selfie.half.png)

The current default generation parameters for this method are as follows:

    cfg_scale: 7
    enable_hr: true
    clip_skip: 2
    negative_prompt: "BadDream, (UnrealisticDream:1.2)"
    sampler_name: "DPM++ SDE Karras"
    steps: 30
    width: 640
    height: 448
    denoising_strength: 0.25
    hr_scale: 2
    hr_upscaler: 8x_NMKD-Superscale_150000_G
    hr_second_pass_steps: 20

Click on the model link at the beginning of this section to see various examples of images generated using method. Many of these images include the prompt and parameters used for the image generation.

## Hybrid/Dreamlike Image Generation Method

To do hybrid/dreamlike images, Greta currently utilizes the [DreamShaper 8](https://civitai.com/models/4384?modelVersionId=128713) model.

The wake words to activate this method are: **`greta dream me`**

For example, **`greta dream me a beautiful cyborg with brown hair, intricate, elegant, highly detailed, majestic`** could result in an image such as:

![image](https://github.com/xydreen/greta-thunbot/blob/89ab296e7c59455499af19cd1c93e674b6668d27/images/dream.main.half.png)

To generate a selfie from Greta's perspective, the wake words are: **`greta dream a selfie`**

For example, **`greta dream a selfie intricate, elegant, highly detailed, majestic, hdr`** could result in an image such as:

![image](https://github.com/xydreen/greta-thunbot/blob/89ab296e7c59455499af19cd1c93e674b6668d27/images/dream.selfie.half.png)

The current default generation parameters for this method are as follows:

    cfg_scale: 7
    enable_hr: true
    clip_skip: 2
    negative_prompt: "BadDream, (UnrealisticDream:1.2)"
    sampler_name: "DPM++ SDE Karras"
    steps: 30
    width: 640
    height: 448
    denoising_strength: 0.25
    hr_scale: 2
    hr_upscaler: 8x_NMKD-Superscale_150000_G
    hr_second_pass_steps: 20

Click on the model link at the beginning of this section to see various examples of images generated using method. Many of these images include the prompt and parameters used for the image generation.

## Artistic/Cartoon/Anime Image Generation Method

To do artistic, cartoon and anime images, Greta currently utilizes the [MeinaMix 11](https://civitai.com/models/7240/meinamix) model.

The wake words to activate this method are: **`greta create me`**

For example, **`greta create me cinematic lighting, 1girl, soaked, long curly black hair, red detailed eyes, eye contact, forest, sakura leafs`** could result in an image such as:

![image](https://github.com/xydreen/greta-thunbot/blob/3e76352d140e8f620a8dc2d6b5adbc783711beea/images/art.main.half.png)

To generate a selfie from Greta's perspective, the wake words are: **`greta create a selfie`**

For example, **`greta create a selfie with a pig`** could result in an image such as:

![image](https://github.com/xydreen/greta-thunbot/blob/3e76352d140e8f620a8dc2d6b5adbc783711beea/images/art.selfie.half.png)

The current default generation parameters for this method are as follows:

    cfg_scale: 7
    enable_hr: true
    clip_skip: 2
    negative_prompt: "(worst quality, low quality:1.4), (zombie, sketch, interlocked fingers, comic)"
    sampler_name: "DPM++ SDE Karras"
    steps: 30
    width: 640
    height: 448
    denoising_strength: 0.3
    hr_scale: 2
    hr_upscaler: RealESRGAN_x4plus_anime_6B
    hr_second_pass_steps: 10

Click on the model link at the beginning of this section to see various examples of images generated using method. Many of these images include the prompt and parameters used for the image generation.

## Image Generation Advanced

*...add additional prompt information here...*

**Tunable Parameters**

There are many parameters you can fine-tune by adding them to your prompt. Here is currently what you are able to tune:

    cfg_scale
    enable_hr
    hr_scale
    hr_upscaler
    denoising_strength
    steps
    negative_prompt
    sampler_name
    seed
    height
    width
    clip_skip
    hr_second_pass_steps

For example, let's say your prompt is: **`greta dream me a pig`**

By default, Greta will generate landscape-style images. So, from the above prompt, you may receive something like:

![image](https://github.com/xydreen/greta-thunbot/blob/d03fc8a64a09ca41ce9da9f02d1f38678e345512/images/param.landscape.half.png)

Now, let's say you want a portrait-style image. Let's add **`height=768 width=512`** to the end of the prompt, which would give us a full prompt of: **`greta dream me a pig height=768 width=512`**

This would result in the dimensions of the image changing, and you may receive something like:

![image](https://github.com/xydreen/greta-thunbot/blob/2213cad35695c67d8834ebf71a8e0fb91a053934/images/param.portrait2.half.png)

Changing the orientation (landscape vs portrait) of an image generation can dramatically change the characteristics of the resulting image.

## Changelog

 - **Aug 05, 2023:** Initial commit.
