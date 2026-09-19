# Scientific basis for VAIS Voice

Sources checked 2026-09-19. These external works motivate evaluation methods, not VAIS Voice performance, enterprise readiness or commercial demand. Preprints are labelled separately. No paper establishes comprehensive coverage of our intended KZ/RU use cases.

## 1. KSC2: An Industrial-Scale Open-Source Kazakh Speech Corpus

Mussakhojayeva, Khassanov & Varol · 2022 · Interspeech 2022 · Peer-reviewed corpus paper.

[Primary source](https://www.isca-archive.org/interspeech_2022/mussakhojayeva22_interspeech.html)

KSC2 includes transcribed Kazakh speech and Kazakh–Russian code-switching. A starting point for local ASR evaluation, not a complete enterprise-call benchmark. Check licensing and domain coverage.

## 2. τ-bench: A Benchmark for Tool-Agent-User Interaction in Real-World Domains

Yao, Shinn, Razavi & Narasimhan · 2025 · ICLR 2025 · preprint 2024 · Peer-reviewed benchmark.

[Primary source](https://openreview.net/pdf?id=roNSXZpUDN)

Evaluates tool-using agents against goal states and checks consistency over repeated interactions. A basis for task and tool checks. It does not validate audio latency, Kazakh speech or our implementation.

## 3. VoiceBench: Benchmarking LLM-Based Voice Assistants

Chen et al. · 2026 · TACL 14, 378–398 · Peer-reviewed benchmark.

[Primary source](https://aclanthology.org/2026.tacl-1.18/)

Evaluates spoken instructions under speaker, environment and content variations, beyond transcription alone. Supports end-to-end evaluation. This external academic VoiceBench is not the planned VAIS VoiceBench module; no affiliation is implied.

## 4. IHBench: Evaluating Post-Interruption Recovery in Voice Agents with Structured Workflows

Salimi et al. · 2026 · arXiv:2606.19595 · Preprint.

[Primary source](https://arxiv.org/abs/2606.19595)

Separately evaluates task fulfillment and recovery after interruptions in structured workflows. Motivates recovery tests, not just barge-in timing. Local-language transfer remains unverified.

## 5. ASVspoof 2021: Towards Spoofed and Deepfake Speech Detection in the Wild

Liu et al. · 2023 · IEEE/ACM TASLP · DOI 10.1109/TASLP.2023.3285283 · Peer-reviewed challenge analysis.

[Primary source](https://arxiv.org/abs/2210.02437)

Reports limitations across real replay environments and deepfake source datasets. VoiceGuard needs unseen-generator and channel tests. A score is not proof of fraud or a calibrated probability by default.

## 6. NISQA: A Deep CNN-Self-Attention Model for Multidimensional Speech Quality Prediction with Crowdsourced Datasets

Mittag, Naderi, Chehadi & Möller · 2021 · Interspeech 2021 · Peer-reviewed methods paper.

[Primary source](https://www.isca-archive.org/interspeech_2021/mittag21_interspeech.html)

Predicts perceptual quality and several distortion dimensions for communication audio. Useful as a candidate acoustic metric, not a substitute for native-speaker TTS listening tests or factual correctness.

## 7. Benchmarking LLM Judges for Voice-Agent Evaluation: Reliability, Calibration, and Human Oversight

Purwar, Singh & Srivastava · 2026 · arXiv:2608.24314 · Preprint.

[Primary source](https://arxiv.org/abs/2608.24314)

Finds that agreement between human and LLM judges depends on metric and evaluation configuration. Validate automated rubrics with bilingual reviewers; retain human review for ambiguous or high-impact failures.

## Proposed contribution

A locally reviewed scenario collection, reproducible end-to-end runs and evidence-linked regression reports. Test its incremental value against simpler baselines; do not claim novelty of voice-agent evaluation or universal deepfake detection. The external academic VoiceBench is not VAIS VoiceBench.
