# 12-week research plan

## Track A — code-switching ASR

### Hypothesis

Language-aware adaptation and sampling can reduce errors near Kazakh–Russian switch boundaries compared with an unadapted multilingual ASR baseline, without materially degrading monolingual Kazakh recognition.

### Evaluation rules

- speaker-disjoint train, validation, and test partitions;
- separate monolingual, code-switched, and switch-boundary reporting;
- explicit transcript normalisation policy for punctuation, numerals, casing, scripts, and loanwords;
- WER and CER plus a documented language-aware/switch metric;
- error analysis for named entities, morphology, rare words, acoustic conditions, and language confusion.

## Track B — anti-spoofing

### Hypothesis

A detector trained with diverse attack and channel augmentation can improve performance on unseen generators and codecs over a standard public-data baseline, while retaining calibrated scores on bona fide Kazakh and Russian speech.

### Evaluation rules

- speaker- and utterance-disjoint partitions;
- attack families and generator versions recorded in immutable manifests;
- a held-out unseen-attack set not used for model or threshold selection;
- EER, minDCF, ROC/PR-AUC, calibration, and fixed-threshold false-positive/false-negative rates;
- breakdown by language, codec, device, noise, duration, and attack family.

## Work packages

### WP1 — Governance, corpus, and baselines (weeks 1–4)

- Approve data-use, consent, retention, and access policies.
- Define transcript and language-span annotation guidance.
- Build manifests and leakage-safe partitions.
- Reproduce one multilingual ASR baseline and one anti-spoofing baseline.

**Gate:** a reviewer can reconstruct a small approved sample and reproduce baseline metrics without accessing undeclared data.

### WP2 — Adaptation and robustness (weeks 5–8)

- Compare full fine-tuning, parameter-efficient adaptation, and decoding/language-tag strategies within a fixed budget.
- Evaluate augmentation and representation choices for anti-spoofing.
- Test codec, channel, noise, duration, and missing-metadata sensitivity.

**Gate:** comparisons share the same data snapshot, partitions, metrics, and documented compute envelope.

### WP3 — Held-out evaluation and demo (weeks 9–12)

- Freeze configurations and thresholds before test-set evaluation.
- Evaluate unseen conditions and calibration; document failures and subgroup uncertainty.
- Package offline inference and a restricted demonstrator using approved samples only.
- Publish model cards, dataset documentation, and reproducibility reports where licences allow.

**Gate:** every displayed output is traceable to data, model, and configuration versions and includes an appropriate limitation notice.

## Initial compute estimate

This planning range must be updated after model size and corpus hours are fixed:

- ASR adaptation and ablations: approximately 300–900 accelerator-hours on 24–80 GB GPUs;
- anti-spoofing baselines and robustness experiments: approximately 150–500 accelerator-hours;
- evaluation and inference profiling: approximately 50–150 accelerator-hours;
- encrypted working storage: capacity driven by approved audio, derived features, checkpoints, and retention requirements.

## MVP completion criteria

The MVP requires governed manifests, speaker-disjoint splits, reproducible baselines for both tracks, code-switch-aware ASR analysis, unseen-attack anti-spoof analysis, model cards, and a restricted demo. Aggregate accuracy alone is not sufficient.
