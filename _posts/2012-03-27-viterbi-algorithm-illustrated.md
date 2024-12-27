---
layout: post
title: The Viterbi Algorithm - Illustrated! 
date: 2012-03-27 15:00:00
description: Example for generating trellis diagram plots with CommPy. 
tags: viterbi-algorithm trellis-diagram commpy python matplotlib
categories: communication-systems
featured: false
---
It is often helpful to visualize the operation of the Viterbi Algorithm used in the decoding of convolutional codes. Here is an attempt to do the same using Python, Matplotlib, NumPy, SciPy and CommPy.

Below is a video which shows one such illustration of the Viterbi Algorithm in action using the following parameters.

The convolutional code is represented by the encoder matrix,

$$ G(D)=[1+D^2, 1+D+D^2] $$

Let us assume that the transmitted message is [1, 0, 0, 0] and hence the corresponding codeword is [11, 01, 11, 00]. Also assume that there was a single bit error during the transmission and therefore, let the received codeword be [11, 11, 11, 00]. The Viterbi algorithm operates on this received codeword and recovers the correct codeword [11, 01, 11, 00] as shown below.


{% include video.liquid path="https://www.youtube.com/embed/RqpXrw1d19E" class="img-fluid rounded z-depth-1" %}

This animation was generated using Python code. The code along with this example can be found [here](https://github.com/veeresht/viterbi-algorithm-animation).
