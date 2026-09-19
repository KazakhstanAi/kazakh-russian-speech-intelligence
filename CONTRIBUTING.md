# Contributing to VAIS Voice

The scope is synthetic-speech detection for KZ/RU recordings and its supporting benchmark.

Propose datasets, models or API changes in an issue first. Document rights, label provenance, speaker/source/generator partitions, preprocessing, baselines, metrics, calibration, seeds, compute budget and failure analysis. Follow [the evaluation protocol](docs/evaluation-protocol.md).

Never commit private recordings, identity mappings, secrets, generated impersonation collections or model weights. Do not present planned inference as implemented or imply universal detector reliability.

```bash
python -m venv .venv
# Activate the virtual environment for your shell.
pip install -e ".[dev]"
ruff check .
ruff format --check .
pytest
```

Reusable code belongs in the package with tests. Code contributions use MIT; data/model rights are reviewed separately.
