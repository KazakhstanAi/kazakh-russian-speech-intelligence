# Data and ethics

## Before ingestion

Every corpus needs an owner, canonical source, version, licence, consent or other documented legal basis, permitted purposes, redistribution status, retention period, deletion procedure, and access classification. If any field is unknown, the data stays out of training.

## Identity and privacy

- assign research identifiers instead of using participant names;
- store re-identification keys separately with restricted access;
- minimise demographic metadata and justify every retained field;
- encrypt restricted audio at rest and in transit;
- log access to private corpora;
- honour withdrawal and deletion obligations through traceable manifests.

Voice is biometric data in many contexts. Public availability is not automatically permission for model training, redistribution, or impersonation research.

## Partitioning and leakage

The same speaker, source recording, near-duplicate utterance, or synthetic derivative must not cross protected partitions. Attack generators and versions must be recorded so unseen-attack evaluation is meaningful. Text overlap and shared background audio should also be audited.

## Anti-spoof threat model

The detector may encounter replay, text-to-speech, voice conversion, cloned speech, editing/splicing, compression, telephony, noise, and adversarial post-processing. The project does not claim universal deepfake detection. Each model card must specify which attacks and channels were tested and what remains unknown.

## Release review

Before publishing audio, transcripts, embeddings, checkpoints, or a demo:

1. verify consent and licence compatibility;
2. assess speaker-identification, reconstruction, impersonation, and harassment risks;
3. remove secrets, identity mappings, and unintended personal content;
4. limit rate, access, retention, and output detail where needed;
5. document takedown, correction, and incident-response contacts.

Generated speech used for detector research should be access-controlled when release would materially improve impersonation capability.
