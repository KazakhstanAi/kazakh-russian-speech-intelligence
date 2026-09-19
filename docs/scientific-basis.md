# Synthetic speech authenticity — scientific basis

Sources checked 2026-09-19. The central literature concerns detection and generalization; KSC2 is a regional corpus reference and NISQA is supporting audio-quality work. None establishes VAIS Voice performance or grants blanket dataset rights.

## 1. ASVspoof 2021: Towards Spoofed and Deepfake Speech Detection in the Wild

Liu et al. · 2023 · IEEE/ACM TASLP.

[Primary source](https://arxiv.org/abs/2210.02437)

Reveals generalization gaps across deepfake source datasets and real replay environments. A core evaluation reference, not evidence that our detector already works in KZ/RU conditions.

## 2. AASIST: Audio Anti-Spoofing using Integrated Spectro-Temporal Graph Attention Networks

Jung et al. · 2022 · ICASSP 2022.

[Primary source](https://arxiv.org/abs/2110.01200)

Models spectro-temporal relationships for audio anti-spoofing; an official implementation is available. A reproducible baseline candidate. Its original benchmark results do not establish robustness to our languages or new generators.

## 3. Does Audio Deepfake Detection Generalize?

Müller et al. · 2022 · Interspeech 2022.

[Primary source](https://www.isca-archive.org/interspeech_2022/muller22_interspeech.html)

Finds substantial degradation when existing detectors are evaluated on collected in-the-wild audio. Motivates held-out domains and matched preprocessing. Publicly accessible recordings still require a data-use review.

## 4. ASVspoof 5: Design, Collection and Validation of Resources for Spoofing, Deepfake, and Adversarial Attack Detection Using Crowdsourced Speech

Wang et al. · 2025 · arXiv:2502.08857 · resource paper.

[Primary source](https://arxiv.org/abs/2502.08857)

Introduces diverse acoustic data, multiple attack algorithms and speaker-disjoint partitions. An additional benchmark/protocol reference. We must separately test unseen generators and codecs in KZ/RU, rather than transfer published scores.

## 5. KSC2: An Industrial-Scale Open-Source Kazakh Speech Corpus

Mussakhojayeva, Khassanov & Varol · 2022 · Interspeech 2022.

[Primary source](https://www.isca-archive.org/interspeech_2022/mussakhojayeva22_interspeech.html)

Includes transcribed Kazakh speech and Kazakh–Russian code-switching. A corpus reference for local speech coverage, not ready-made real/synthetic labels. Audit provenance and licences before selecting genuine-speech samples.

## 6. NISQA: A Deep CNN-Self-Attention Model for Multidimensional Speech Quality Prediction with Crowdsourced Datasets

Mittag et al. · 2021 · Interspeech 2021.

[Primary source](https://www.isca-archive.org/interspeech_2021/mittag21_interspeech.html)

Predicts perceived speech quality and communication-channel distortions. Optional quality-control reference, not a synthetic-speech detector or calibrated authenticity score.

## Research contribution to test

Leakage-safe KZ/RU real/synthetic evaluation, unseen-generator/channel robustness and calibrated, evidence-linked reports. Benchmark results must be measured, not borrowed from other papers. Generic agent-evaluation literature is outside the current scope.
