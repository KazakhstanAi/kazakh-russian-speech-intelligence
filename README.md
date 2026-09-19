# VAIS Voice

## Synthetic Speech Authenticity for Kazakh–Russian Environments

VAIS Voice is a research project and future API for detecting synthetic speech in Kazakh, Russian and mixed KZ/RU audio. The product goal is focused: **upload audio → synthetic-speech score with quality, model version and calibration information**.

> Current status: research design and Python scaffold. There is no trained VAIS detector, running upload API or validated KZ/RU performance yet. “Research prototype” is the next deliverable, not a claim of existing functionality.

## What the detector should do

Analyse short voice messages and recordings processed through real audio codecs and channels. Return a score whose direction is explicit (higher means more synthetic-like), signal-quality observations, model/preprocessing versions, calibration status and limitations. Unsupported or poor-quality input should receive an inconclusive response.

A synthetic score is **not proof of fraud**, not identity verification and not a probability that a particular person is an attacker. Synthetic audio may be legitimate.

## One pipeline, three research components

```text
Audio → Preprocessing → Language/channel metadata
      → Synthetic speech detector → Calibration
      → Authenticity report / score → API / Web demo
```

- **Detection Model:** real vs synthetic, evaluated separately on KZ, RU and code-switching.
- **Robustness:** held-out TTS/voice-cloning generators; Opus, MP3, AAC and telephone-like compression; noise and repeated transcoding.
- **Benchmark:** protected real/synthetic samples, governed provenance and reproducible evaluation. This is R&D infrastructure for validating the detector, not a separate product.

## Planned MVP

Accept a short `.wav`, `.mp3`, `.ogg` or `.opus` file. Validate actual content, decode in isolation, measure signal properties, infer and return a versioned report. Set supported durations and upload limits after profiling.

A report should contain filename, duration/sample rate, language/channel metadata with provenance (supplied, inferred or unknown), raw synthetic score, calibration status, supported-domain checks, model version and uncertainty/abstention reason. Do not label confidence “high” merely because a raw score is large.

The website contains a **static report mockup**, not an upload service. Its 0.87 score and VAIS-VA v0.1 name are illustrative, not measured results or a released model.

## Evaluation

| Metric / test | Purpose |
| --- | --- |
| ROC-AUC | Threshold-independent ranking of real vs synthetic; synthetic is positive. |
| EER | Equal false-positive / false-negative error rate. |
| FPR@TPR95 | Real audio incorrectly flagged at 95% synthetic recall; record ROC interpolation and uncertainty. |
| Calibration | Reliability diagrams, Brier score, ECE and class prevalence on held-out data. |
| Unseen-generator | Generator families/versions excluded from training and calibration. |
| Codec/noise robustness | Matched transformations across both classes, including transcoding and re-recording. |
| Language slices | KZ, RU and KZ↔RU with counts and intervals. |
| Cross-speaker | No leakage of speakers, source recordings or derivatives across protected splits. |

Also choose operating thresholds on development data only, then report actual held-out TPR/FPR. FPR@TPR95 is an evaluation summary, not permission to tune a deployed threshold on the test set.

Read the [evaluation protocol](docs/evaluation-protocol.md) and [six annotated scientific references](docs/scientific-basis.md). These sources motivate research; they do not establish our model's accuracy.

## 12-week plan

- **Weeks 1–4:** licensed genuine/synthetic corpus, leakage-safe splits, baselines and reproducible benchmark.
- **Weeks 5–8:** KZ/RU, unseen generators, codecs/noise, calibration and model selection.
- **Weeks 9–12:** web/API prototype, public benchmark report and restricted demo, conditional on data/model readiness.
- **Later:** streaming, batch API, enterprise/on-prem deployments and additional anti-spoof scenarios. Replay detection requires separate validation.

[Research plan](docs/research-plan.md) · [Architecture](docs/architecture.md) · [Data and ethics](docs/data-and-ethics.md)

## Repository

The existing GitHub URL and Python import `kazakh_russian_speech_intelligence` remain stable. The public project name is VAIS Voice. Renaming the repository/package is a separate migration.

```text
benchmark/     Benchmark scope and evaluation contract
configs/       Reproducibility requirements
data/          Manifest rules; raw data remains local/external
docs/          Research, metrics, architecture and governance
models/        Model-card rules; no released weights
src/           Python scaffold
tests/         Scaffold checks, not detector-performance validation
notebooks/     Research exploration
```

The planned detection/preprocessing/evaluation code and future API/web components are described in [architecture](docs/architecture.md); they are not implemented by this documentation update.

## Development

Python 3.11+:

```bash
python -m venv .venv
# Windows: .venv\Scripts\Activate.ps1
# Linux/macOS: source .venv/bin/activate
pip install -e ".[dev]"
ruff check .
ruff format --check .
pytest
```

Do not commit recordings, sensitive transcripts, identity mappings, credentials or model weights. Do not train on user uploads by default.

[Contributing](CONTRIBUTING.md) · [Security](SECURITY.md) · [Citation](CITATION.cff) · [MIT code licence](LICENSE). Audio, datasets and weights have separate rights.

---

**По-русски:** VAIS Voice — исследовательский проект обнаружения синтетической речи в казахско-русской среде. Первый продуктовый MVP: загрузка короткого аудио и отчёт со score, качеством сигнала, версией модели и статусом калибровки. KZ/RU Anti-Spoofing Benchmark служит проверке детектора. Готовой модели и опубликованных результатов пока нет.
