# Contributing

VAIS Voice is at the platform-design stage. Contributions must protect speakers, preserve benchmark provenance, and distinguish planned features from working implementations.

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

State the hypothesis, baseline, scenario/corpus manifest, consent/licensing status, speaker/scenario/attack splits, metrics, seeds, cost budget, and failure analysis. Follow docs/evaluation-protocol.md. Automated calls require an authorised sandbox, allowlisted destinations, cost limits and mocked tools. Never invoke real financial or customer actions. Anti-spoofing work must include unseen-condition evaluation and must not publish a reusable impersonation pipeline.

By contributing, you agree that your code contribution is licensed under the MIT License. Data, audio, transcripts, and model artefacts require separate review and licensing.
