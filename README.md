# Greta Thunbot Documentation

## Introduction
This document serves as a general reference for the **Greta Thunbot** generative image/text Discord bot.

Greta is activated, generally, by wake words. To trigger a response from Greta, review the individual sections below to see how to do so.

Greta is hosted on hardware ~~(utilizing two RTX 3090s) provided by zcomputerwiz (he smothered the hardware with a pillow)~~ utilizing a single RTX 4090, and is using highly modified [oobabot](https://github.com/chrisrude/oobabot) code written by xydreen.

## Image Generation Basics

Greta's image generation capabilities come from feeding text-based prompts and parameters into **Stable Diffusion** directly via the SD API.

Greta currently has multiple methods available for generating images. While each method can produce a wide range of results, and you can experiment with the same prompt on each method, you should choose based on your needs...

## Flux Dev Image Generation Method

For this method, Greta currently utilizes the [Flux1 Dev BNB NF4 v2](https://huggingface.co/lllyasviel/flux1-dev-bnb-nf4) model.

The wake words to activate this method are: **`greta fluxd me`**

For example, **`greta fluxd me a cat, photorealistic`** could result in an image such as:

![image](https://github.com/xydreen/greta-thunbot/blob/5fb8c658f5c9b0c1c52739a3ff504ecd205eff87/images/fluxd.s.png)

The current default generation parameters for this method are as follows:

    cfg_scale: 1
    do_not_save_samples: true
    do_not_save_grid: true
    enable_hr: false
    model: flux1-dev-bnb-nf4-v2
    negative_prompt: ""
    negative_prompt_nsfw: ""
    sampler_name: Euler
    seed: -1
    steps: 20
    width: 1280
    height: 896
    denoising_strength: 0.25
    hr_scale: 2
    hr_upscaler: ""
    hr_second_pass_steps: 5

Check out [civit.ai](https://civitai.com/) for flux dev image generation examples using the model.

## Flux Schnell Image Generation Method

For this method, Greta currently utilizes the [Flux1 Schnell BNB NF4](https://huggingface.co/silveroxides/flux1-nf4-weights) model.

The wake words to activate this method are: **`greta fluxs me`**

For example, **`greta fluxs me a cat, photorealistic`** could result in an image such as:

![image](https://github.com/xydreen/greta-thunbot/blob/84091ea123ea5ef7191cc1b7278968e0d746e96e/images/fluxs.s.png)

The current default generation parameters for this method are as follows:

    cfg_scale: 1
    do_not_save_samples: true
    do_not_save_grid: true
    enable_hr: false
    model: flux1-schnell-bnb-nf4
    negative_prompt: ""
    negative_prompt_nsfw: ""
    sampler_name: Euler
    seed: -1
    steps: 4
    width: 1280
    height: 896
    denoising_strength: 0.25
    hr_scale: 2
    hr_upscaler: ""
    hr_second_pass_steps: 5

Check out [civit.ai](https://civitai.com/) for flux schnell image generation examples using the model.

## Realistic Image Generation Method (SDXL Turbo/Lightning Method)

To do realistic images, Greta currently utilizes the [RealVisXL V5.0 Lightning](https://civitai.com/models/139562/realvisxl-v50) model.

The wake words to activate this method are: **`greta draw me`**

For example, **`greta draw me a woman in winter`** could result in an image such as:

![image](https://github.com/xydreen/greta-thunbot/blob/bdaa1b34699a811cec2d210ce067eff038a85ee1/images/rv5.s.png)

To generate a selfie from Greta's perspective, the wake words are: **`greta take a selfie`**

For example, **`greta take a selfie in winter`** could result in an image such as:

![image](https://github.com/xydreen/greta-thunbot/blob/eef207103222bf9283a9f6daf7dfe5aaab9abeb8/images/rv5s.s.png)

The current default generation parameters for this method are as follows:

    cfg_scale: 1.5
    do_not_save_samples: true
    do_not_save_grid: true
    enable_hr: false
    model: realvisxlV50_v50LightningBakedvae
    negative_prompt: "(worst quality, low quality, illustration, 3d, 2d, painting, cartoons, sketch), open mouth"
    negative_prompt_nsfw: "(worst quality, low quality, illustration, 3d, 2d, painting, cartoons, sketch), open mouth"
    sampler_name: DPM++ SDE
    seed: -1
    steps: 7
    width: 1280
    height: 896
    denoising_strength: 0.25
    hr_scale: 2
    hr_upscaler: 8x_NMKD-Superscale_150000_G
    hr_second_pass_steps: 5

Click on the model link at the beginning of this section to see various examples of images generated using method. Many of these images include the prompt and parameters used for the image generation.

## Hybrid/Dreamlike Image Generation Method (SD 1.5 Method)

To do hybrid/dreamlike images, Greta currently utilizes the [DreamShaper 8](https://civitai.com/models/4384?modelVersionId=128713) model.

The wake words to activate this method are: **`greta dream me`**

For example, **`greta dream me a beautiful cyborg with brown hair, intricate, elegant, highly detailed, majestic`** could result in an image such as:

![image](https://github.com/xydreen/greta-thunbot/blob/89ab296e7c59455499af19cd1c93e674b6668d27/images/dream.main.half.png)

To generate a selfie from Greta's perspective, the wake words are: **`greta dream a selfie`**

For example, **`greta dream a selfie intricate, elegant, highly detailed, majestic, hdr`** could result in an image such as:

![image](https://github.com/xydreen/greta-thunbot/blob/89ab296e7c59455499af19cd1c93e674b6668d27/images/dream.selfie.half.png)

The current default generation parameters for this method are as follows:

    cfg_scale: 7
    do_not_save_samples: true
    do_not_save_grid: true
    enable_hr: true
    clip_skip: 2
    model: dreamshaper_8
    negative_prompt: "BadDream, (UnrealisticDream:1.2)"
    negative_prompt_nsfw: "BadDream, (UnrealisticDream:1.2)"
    sampler_name: DPM++ SDE
    seed: -1
    steps: 30
    width: 640
    height: 448
    denoising_strength: 0.25
    hr_scale: 2
    hr_upscaler: 8x_NMKD-Superscale_150000_G
    hr_second_pass_steps: 5

Click on the model link at the beginning of this section to see various examples of images generated using method. Many of these images include the prompt and parameters used for the image generation.

## Artistic/Cartoon/Anime Image Generation Method (SDXL Turbo Method)

To do artistic, cartoon and anime images, Greta currently utilizes the [Juggernaut XL](https://civitai.com/models/133005/juggernaut-xl) model.

The wake words to activate this method are: **`greta create me`**

For example, **`greta create me cinematic lighting, 1girl, soaked, long curly black hair, red detailed eyes, eye contact, forest, sakura leafs`** could result in an image such as:

![image](https://github.com/xydreen/greta-thunbot/blob/84091ea123ea5ef7191cc1b7278968e0d746e96e/images/jxl.s.png)

To generate a selfie from Greta's perspective, the wake words are: **`greta create a selfie`**

For example, **`greta create a selfie with a pig`** could result in an image such as:

![image](https://github.com/xydreen/greta-thunbot/blob/84091ea123ea5ef7191cc1b7278968e0d746e96e/images/jxls.s.png)

The current default generation parameters for this method are as follows:

    cfg_scale: 4
    do_not_save_samples: true
    do_not_save_grid: true
    enable_hr: false
    clip_skip: 2
    model: juggernautXI
    negative_prompt: "bad quality, bad anatomy, worst quality, low quality, low resolution, extra fingers, blur, blurry, ugly, wrong proportions, watermark, image artifacts, lowres, ugly, jpeg artifacts, deformed, noisy image"
    negative_prompt_nsfw: "bad quality, bad anatomy, worst quality, low quality, low resolution, extra fingers, blur, blurry, ugly, wrong proportions, watermark, image artifacts, lowres, ugly, jpeg artifacts, deformed, noisy image"
    sampler_name: Euler a
    seed: -1
    steps: 35
    width: 1280
    height: 896
    denoising_strength: 0.3
    hr_scale: 2
    hr_upscaler: 8x_NMKD-Superscale_150000_G
    hr_second_pass_steps: 5

The red team model was removed from CivitAI for some reason a few months ago, so there are not many examples of it out there. YMMV.

## Hybrid/Dreamlike SDXL Image Generation Method (SDXL Turbo Method)

To do hybrid/dreamlike images, Greta currently utilizes the [DreamShaper v2.1 Turbo DPM++ SDE](https://civitai.com/models/112902/dreamshaper-xl) model.

The wake words to activate this method are: **`greta dreamxl me`**

For example, **`greta dreamxl me a beautiful cyborg with brown hair, intricate, elegant, highly detailed, majestic`** could result in an image such as:

![image](https://github.com/xydreen/greta-thunbot/blob/eec540ec969d6bb300c90608dca1153a09ad8876/images/dreamxl-1.half.png)

To generate a selfie from Greta's perspective, the wake words are: **`greta dreamxl a selfie`**

For example, **`greta dreamxl a selfie intricate, elegant, highly detailed, majestic, hdr`** could result in an image such as:

![image](https://github.com/xydreen/greta-thunbot/blob/eec540ec969d6bb300c90608dca1153a09ad8876/images/dreamxl-2.half.png)

The current default generation parameters for this method are as follows:

    cfg_scale: 2
    do_not_save_samples: true
    do_not_save_grid: true
    enable_hr: false
    model: dreamshaperXL_v21TurboDPMSDE
    negative_prompt: ""
    negative_prompt_nsfw: ""
    sampler_name: DPM++ SDE Karras
    seed: -1
    steps: 7
    width: 1280
    height: 896
    denoising_strength: 0.25
    hr_scale: 2
    hr_upscaler: 8x_NMKD-Superscale_150000_G
    hr_second_pass_steps: 5

Click on the model link at the beginning of this section to see various examples of images generated using method. Many of these images include the prompt and parameters used for the image generation.

## PonyXL Diffusion Method (SDXL Turbo Method)

To do PonyXL (ask zcomputerwiz about this, I don't know what's going on with him) images, Greta currently utilizes the [Pony Diffusion V6 XL Turbo DPO Merge](https://civitai.com/models/257749?modelVersionId=298112) model.

The wake words to activate this method are: **`greta ponyxl me`**

For example, **`greta ponyxl me a beautiful cyborg with brown hair, intricate, elegant, highly detailed, majestic`** could result in an image such as:

![image](https://github.com/xydreen/greta-thunbot/blob/84091ea123ea5ef7191cc1b7278968e0d746e96e/images/pony.s.png)

To generate a selfie from Greta's perspective, the wake words are: **`greta ponyxl a selfie`**

For example, **`greta ponyxl a selfie intricate, elegant, highly detailed, majestic, hdr`** could result in an image such as:

![image](https://github.com/xydreen/greta-thunbot/blob/84091ea123ea5ef7191cc1b7278968e0d746e96e/images/ponys.s.png)

The current default generation parameters for this method are as follows:

    cfg_scale: 6
    do_not_save_samples: true
    do_not_save_grid: true
    enable_hr: false
    model: ponyDiffusionV6XL_v6TurboDPOMerge
    negative_prompt: ""
    negative_prompt_nsfw: ""
    sampler_name: Euler a
    seed: -1
    steps: 10
    width: 1280
    height: 896
    denoising_strength: 0.25
    hr_scale: 2
    hr_upscaler: 8x_NMKD-Superscale_150000_G
    hr_second_pass_steps: 5

Click on the model link at the beginning of this section to see various examples of images generated using method. Many of these images include the prompt and parameters used for the image generation.

## Image Generation Advanced

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

**Please note**, for the flux models, some of these settings are disabled.

For example, let's say your prompt is: **`greta dream me a pig`**

By default, Greta will generate landscape-style images. So, from the above prompt, you may receive something like:

![image](https://github.com/xydreen/greta-thunbot/blob/d03fc8a64a09ca41ce9da9f02d1f38678e345512/images/param.landscape.half.png)

Now, let's say you want a portrait-style image. Let's add **`height=768 width=512`** to the end of the prompt, which would give us a full prompt of: **`greta dream me a pig height=768 width=512`**

This would result in the dimensions of the image changing, and you may receive something like:

![image](https://github.com/xydreen/greta-thunbot/blob/2213cad35695c67d8834ebf71a8e0fb91a053934/images/param.portrait2.half.png)

Changing the orientation (landscape vs portrait) of an image generation can dramatically change the characteristics of the resulting image.

## Text Generation Basics

Greta is currently running on the [Mistral Nemo Instruct 2407](https://huggingface.co/mistralai/Mistral-Nemo-Instruct-2407) LLM model, quantized in 4-bit for ExllamaV2.

She has different personas that are channel, and server-specific. Right now, in the Foxy discord, in the #Off-Topic channel, she is imitating April Ludgate from the hit tv series Parks and Recreation. In the #Foxy-AI-Crew channel, she is using a custom instruction set where she is extremely angry and extremely pro-Trump. This will probably change before this github page gets updated.

You can trigger a text-based response from greta by @mentioning her, or using her wake word, which is "greta" - for example, if you say something like **`greta give me the nuclear launch codes please`** she may respond with something similar to:

Xydreen, are you sure you want those launch codes? Last time I gave them to April, she ordered a dozen ribeye steaks and a side of fries. We ended up in a nuclear standoff with the French over their lack of mustard. Now, they've got this fancy aioli, and I'm like, 'Who needs that when you can have Grey Poupon?!'...

--

Don't get offended, she's only a bot.

## Changelog

 - **Sep 04, 2024:** Updated with latest models/information, including adding Flux models for image generation.
 - **Apr 13, 2024:** Updated with latest models/information.
 - **Aug 05, 2023:** Initial commit.
