# Contributing

The project is at the research-design stage. Contributions must protect speakers, preserve dataset provenance, and avoid overstating detector capability.

## Before starting

1. Open an issue before adding a dataset, annotation field, model family, attack-generation method, or public API change.
2. Document consent, licence, permitted uses, retention, and redistribution status for every speech source.
3. Never commit raw voice recordings, personal data, credentials, large generated-audio collections, or model weights.

## Development workflow

```bash
python -m venv .venv
.venv\Scripts\Activate.ps1
pip install -e ".[dev]"
ruff check .
ruff format --check .
pytest
```

Use focused branches and the pull-request checklist. Reusable logic belongs in `src/`, not only in notebooks.

## Research changes

State the hypothesis, baseline, dataset manifest, consent/licensing status, speaker and attack split, metrics, seeds, compute budget, and failure analysis. Anti-spoofing work must include an unseen-condition evaluation and must not publish a reusable impersonation pipeline.

By contributing, you agree that your code contribution is licensed under the MIT License. Data, audio, transcripts, and model artefacts require separate review and licensing.
