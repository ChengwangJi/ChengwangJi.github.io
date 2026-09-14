---
layout: single
title: "Research"
permalink: /research/
author_profile: true
---

Our recent solution to CSI feedback with limited samples won the Winning Prize (ranking 9/1252 teams) of the First 6G Intelligent Wireless Communication System Competition held by the IMT-2030 (6G) Promotion Group and Guangdong OPPO Mobile Communications Corp., Ltd.

Deep learning based CSI feedback has received widespread attention from academia and industry in recent years. However, most of the existing deep learning based CSI feedback methods are purely data-driven. In addition to obtaining high-performance gains brought by data-driven, such methods also show poor generalization performance in different scenarios. Currently, to mitigate this issue, expensive data collection costs and long training time for different scenarios are inevitable, and thus poses further challenges for the implementation of such deep learning based CSI feedback methods. To address these challenges, we propose a CSI feedback method that uses only a small number of samples to obtain better generalization capabilities. Through frequency domain data augmentation and the advanced dual-attention-based CSI feedback model, the proposed CSI feedback method can achieve CSI feedback with good generalization ability in a very concise way. In addition, to mitigate quantization errors, we further propose a quantization ensemble framework which exploits several quantizers and dequantizers for ensemble. Specifically, constrained by 30-bit CSI feedback overhead and to balance the number of feedback bits, quantization error and the size of backbone networks, we use 27 bits for quantization and 3 bits as the quantizer index (which indicates that a total of 8 quantizers with different configurations can be utilized). Hybrid scalar quantization is considered, and each two quantizers share an Encoder backbone network to ensure that each Encoder backbone network has larger model scale and learning capabilities.

The dual-attention-based CSI feedback model (left) and the quantization ensemble framework (right):

<img width="6241" height="1589" alt="6GAICompetition_CSIFeedback" src="https://github.com/user-attachments/assets/39247fbf-e1b8-45f5-a94f-804af1bee7d8" />
