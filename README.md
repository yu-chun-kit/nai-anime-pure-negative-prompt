# nai-anime-pure-negative-prompt #

A research about "NAI anime" art with pure negative prompt. Such observation may be useful for "data visualization" to show that how the "number" works.

[Pixiv account for storing the images](https://www.pixiv.net/en/users/11525730)

### Core concept ###
- [UNCONDITIONAL DIFFUSION GUIDANCE](https://openreview.net/pdf?id=lsQCDXjOl3k) (I have no connection to any of the scholars.)
- The "solver" does a kind of [clustering](https://en.wikipedia.org/wiki/Cluster_analysis) which is a kind of [unsupervised learning](https://en.wikipedia.org/wiki/Unsupervised_learning).
- The [Gradient descent](https://en.wikipedia.org/wiki/Gradient_descent) inside the neural network is also somewhat a kind of [Reinforcement learning](https://en.wikipedia.org/wiki/Reinforcement_learning)
- Therefore you can "guide" the AI to somewhat generate waifu in a *almost pure random sense* without mentioning a positive prompt.

### How NovelAI / Stable Diffusion / CLIP works ###
- [Video.](https://www.youtube.com/watch?v=1CIpzeNxIhU&ab_channel=Computerphile)
- [Lenghty explaination which is expected.](https://blog.novelai.net/novelai-improvements-on-stable-diffusion-e10d38db82ac).

### Basic settings ###

- Network: `animefull-final-pruned` (with VAE)
- Skip CLIP layer: **2**
- Only `txt2img` is used.
- No high-res fix.
- Only output dimension, CFG and random seed is modified.
- Training step: **MORE THAN 150**. Sometimes it failed to converge to a "reasonable" image.
- **Cherry pick unless I'm sure how to generate with consistent quality** i.e. most of the contents inside is recognizable and approved by me.
- Therefore no scipt / notebook yet.

### Negative prompt used ###

- The **most general** you can find in the internet. However weighting may be adjusted.
- Somewhat they are really mandatory otherwise it create the image *exactly match the tags*.

```
lowres, bad anatomy, bad hands, text, error, missing fingers, extra digit, fewer digits, cropped, worst quality, low quality, normal quality, jpeg artifacts, signature, watermark, username, blurry, artist name
```

- Obviously more prompts can be added, however I'm not going to generate fap material. They've already flooded the internet.

### General result ###

- The range may varies across different random seed.

|Field|Content|Range|
|---|---|---|
|Random seed|Theme|`int()`|
|Dimension|Count of objects|No more than 4x area of 512x512|
|Aspect ratio|Pose (sometime count)|From 4:1 to 1:4|
|CFG|Brightnes, *in a complicated way*|Currently 9 to 20|
|Solvers|Minor art style (major one is the network itself)|Currnetly **Eular** only|

|Dimension|CFG|STEP|
|---|---|---|
512x512|12~16|150|
512x768|18~20|150|
768x512|NG|150|
