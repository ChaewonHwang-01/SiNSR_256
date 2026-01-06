# Reproducing SiNSR: Experiments under Limited and Full GPU Settings

**SinSR: Diffusion-Based Image Super-Resolution in a Single Step**

This repository is based on the official implementation of the paper  ["SinSR: Diffusion-Based Image Super-Resolution in a Single Step"](https://arxiv.org/pdf/2311.14760.pdf).

![Alt text](assets/framework.png)
## Overview
This repository is based on the official implementation of **SiNSR**.
The goal of this project is to reproduce the SinSR model and verify its behavior
under both limited computational resources and the original experimental settings
described in the paper.

## Experimental Setup and Reproduction Strategy
To validate the functionality and behavior of the SinSR model, 
experiments were conducted in two stages.

**Stage 1: Reduced-scale verification**
Due to limited GPU resources, an initial experiment was performed
to confirm the core behavior of the SinSR model.
The training setup was intentionally simplified by reducing the dataset size
to approximately 5,000 images, lowering
the image resolution to 128, setting the batch size to 1, and 16,000 training iterations.
This stage aimed to verify that the model functions as described in the paper
before scaling up to the full experimental setting.

**Stage 2: Full-scale reproduction**
After confirming the model behavior, the experiment was repeated
under conditions matching the original paper.
Using two GPUs, the model was trained with approximately 70,000 training images,
image resolution of 256, batch size of 4, and 500,000 training iterations.
This stage focuses on reproducing the quantitative and qualitative results
reported in the original SinSR paper.

## Results: Stage 1 – Reduced-scale Verification
In the reduced-scale setting, the objective was not to fully reproduce
the quantitative results of the paper, but to verify the core behavior
of the SinSR model under constrained computational resources.
Despite the simplified setup, the model successfully demonstrated
one-step diffusion-based super-resolution behavior as described in the paper.

### Qualitative Results

The following examples show super-resolution results obtained
from the reduced-scale training setting (resolution 128, batch size 1,
approximately 5,000 training images).

| LR Image | SinSR (1-step) | ResShift (1-step) | ResShift (15-step) |
|---------|----------------|-------------------|--------------------|
| <a href="assets/stage1/lr_dogs.png"><img src="assets/stage1/lr_dogs.png" width="240"/></a> | <a href="assets/stage1/single_sinsr_dogs.png"><img src="assets/stage1/single_sinsr_dogs.png" width="240"/></a> | <a href="assets/stage1/single_resshift_dogs.png"><img src="assets/stage1/single_resshift_dogs.png" width="240"/></a> | <a href="assets/stage1/15steps_resshift_dogs.png"><img src="assets/stage1/15steps_resshift_dogs.png" width="240"/></a> |
