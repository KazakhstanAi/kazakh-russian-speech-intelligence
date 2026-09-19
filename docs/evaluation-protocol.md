# KZ/RU synthetic-speech detection protocol

## Labels and protected partitions

Synthetic speech is the positive class; genuine human speech is negative. Record label provenance and ambiguous/edited cases separately. Re-recording genuine speech does not make it synthetic. A real/synthetic classifier is not automatically a replay detector.

Use separate training, model-selection/development, calibration and protected test partitions. Group speakers, source recordings, near-duplicates, prompts where relevant, source/target voice identities and all synthetic derivatives. Unseen-generator evaluation holds out entire generator families/versions from training, tuning and calibration. Record what is known about pretrained-model exposure; do not claim universal absence of pretraining leakage.

Match language, duration and channel distributions across classes. Apply codec/noise transformations comparably, preventing shortcut detection of file format, silence or dataset provenance.

## Core metrics

- **ROC-AUC:** ranking quality; report class direction, sample counts and confidence intervals.
- **EER:** rate at equal FPR and FNR, documenting interpolation. Not necessarily a suitable operational threshold.
- **FPR@TPR95:** fraction of genuine audio flagged where synthetic recall reaches 95% on the evaluation ROC. Specify interpolation/ties and uncertainty. This threshold is descriptive, not deployable.
- **Operational FPR/FNR/TPR:** freeze a threshold on development data (e.g. target 95% development TPR) and report achieved held-out rates without retuning.
- **Calibration:** reliability diagrams, Brier score and ECE with binning, sample size and class prevalence; fit on calibration data only. Balanced-benchmark probability need not transfer to production.
- **Abstention:** coverage, rejected files, low-quality/unsupported inputs and errors. Report conditional metrics and coverage together; do not quietly remove hard examples.

Bootstrap at independent speaker/source groups rather than treating transformed copies as independent samples. Record seeds, versions, bootstrap settings and per-slice counts. Report uncertainty when 95% recall or rare false positives are poorly resolved by sample size.

## Required slices

KZ, RU and KZ↔RU; known/unseen generator; cross-dataset/domain; MP3/Opus/AAC and telephone-like coding; repeated encoding; microphone/background noise; re-recording; duration and quality. Publish transformation parameters. Document sample-rate conversions, channel mixing, clipping and silence processing identically across classes.

## Baselines and model selection

Compare a simple spectral-feature classifier with an established anti-spoof architecture such as AASIST under the same partitions and preprocessing. More complex encoders are candidates, not presumed winners. Select on development performance and robustness, not the held-out test.

## Meaning of a score

A raw model score measures model evidence, not truth. Do not display “high confidence” from magnitude alone. Any uncertainty label needs a specified validated method. A calibrated synthetic probability is conditional on the evaluated distribution and must not be represented as a person's fraud probability.

## Reproducible release

Publish configurations, manifest versions/checksums where rights permit, exclusions, calibration/threshold provenance, metrics with intervals and failure analysis. Raw restricted audio stays protected. Model cards identify tested and unsupported conditions.
