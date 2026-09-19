# Data directory

The planned VAIS Voice Benchmark includes reviewed KZ/RU scenarios, local terminology, expected task/tool outcomes, transcript/language annotations, interruption cases and failure taxonomy. It is not an existing released dataset. Future manifests must separate synthetic fixtures from consented recordings and freeze scenario-template splits as well as speaker splits.

This repository tracks manifests, schemas, and synthetic fixtures—not raw corpora.

Local-only `raw/`, `interim/`, and `processed/` directories are ignored by Git. Do not override the rules to commit recordings, transcripts with personal data, speaker mappings, embeddings, generated attacks, or signed download URLs.

Every manifest must record source, version, consent/legal basis, licence, permitted use, redistribution status, checksums, transformations, speaker partition, and retention/deletion policy.
