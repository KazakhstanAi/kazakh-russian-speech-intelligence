# Audio data and responsible use

Applies to synthetic-speech detection research and future audio uploads.

## Before ingestion

Every corpus requires source/owner, version, licence, consent or documented basis for use, permitted purposes, redistribution status, retention/deletion policy and access class. Unknown rights or uncertain real/synthetic provenance exclude a sample from supervised training.

Use only approved voices for synthetic-data generation. Do not build or release an impersonation pipeline. Public audio is not automatically authorised for training or redistribution.

## Privacy

Use research IDs, restrict and separate identity mappings, encrypt protected recordings and log access. Honour withdrawal through traceable manifests. Do not reuse uploads for training by default; define retention and deletion before any live demo. Redact exported reports and logs.

## Leakage and label integrity

Group speaker/source/derivative families across protected splits. Document synthetic generator version and source/target speaker provenance. Keep unseen generator families out of training, tuning and calibration. Audit duplicate audio, shared backgrounds and source-domain shortcuts.

Distinguish genuine, synthetic and uncertain/partially edited samples. Re-recorded genuine audio remains genuine for this task; an attack label is not identical to a synthetic label.

## Threat and release model

Study TTS/voice cloning, compression, telephony-like coding, noise and transcoding. Additional replay or manipulation detection is future work, not implied coverage.

Before release: verify rights, assess identification/reconstruction/impersonation risks, remove secrets, review access/rate limits and retention, and provide incident/deletion procedures. Keep restricted samples and model artefacts outside Git.

## Interpretation

Synthetic speech may be legitimate. Scores are not proof of fraud or verification of identity. Do not independently deny service or make accusations from a score. Calibrated probability requires a stated reference distribution; shift may invalidate it. Unsupported or poor-quality audio requires abstention or explicit uncertainty.
