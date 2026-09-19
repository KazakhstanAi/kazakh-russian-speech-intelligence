# VAIS Voice

**Voice AI quality and security infrastructure for Kazakh–Russian environments.**

VAIS Voice is a planned evaluation, security, and observability platform for voice AI in Kazakhstan and Central Asia. It brings together agent testing, STT/TTS evaluation, code-switching analysis, synthetic/replay audio detection, and regression monitoring.

> **Status: research and platform design.** This repository currently provides a Python scaffold and research documentation. It does not yet place test calls, host a dashboard, score audio, or provide production protection. All modules below are planned; no performance or customer claims are made.

## Platform modules

| Module | Planned role |
| --- | --- |
| **VAIS VoiceBench** | Scenario-driven automated voice-agent tests: task completion, intents, tool calls, grounded responses, policy checks, latency and interruption recovery. |
| **VoiceGuard** | Synthetic/deepfake and replay screening with documented thresholds, calibration and abstention. Separate from task-quality scoring. |
| **Speech Intelligence** | STT, language identification, diarization, code-switch detection, conversation transcripts, intent and failure analysis; TTS intelligibility and pronunciation evaluation. |
| **Continuous Evaluation** | Version-to-version comparisons and policy-defined CI gates over a pinned benchmark. Enterprise monitoring is a later phase. |

The name **VAIS VoiceBench** is a working module name, not the independent [academic VoiceBench](https://aclanthology.org/2026.tacl-1.18/). No affiliation is claimed.

## First MVP: 100 authorised test calls

A user connects an agent's **sandbox endpoint**, selects a versioned KZ/RU suite, and runs 100 simulated test calls. This is a planned deliverable, not a working feature.

```text
Agent version + approved sandbox
              ↓
100 versioned KZ / RU / mixed-speech scenarios
              ↓
Audio + transcript + tool trace + timings
              ↓
Deterministic checks + reviewed evaluation rubrics
              ↓
Regression report → PASS / FAIL / REVIEW
```

The report separates task completion, Kazakh and Russian WER/CER, code-switch errors, intent accuracy, P95 response latency, tool-call success, interruption recovery, policy violations, and critical failures. “Accuracy” is not a single unqualified percentage; definitions and denominators are in the [evaluation protocol](docs/evaluation-protocol.md).

Each failed test links approved audio, transcript, expected behaviour, actual behaviour, failure reason, agent/config versions, and evaluator provenance. Missing evidence is inconclusive, not a pass. VoiceGuard adds a separate research score with tested attack/channel scope, not an automatic fraud verdict.

One 100-call suite is a feasibility milestone, not evidence of enterprise readiness, comprehensive safety or statistically precise rare-failure rates.

## Regional focus and intended users

Kazakh, Russian and within-dialogue code-switching; local names, addresses, numbers, tenge amounts and banking terminology; regional speech, noisy channels, telephony compression and interruptions.

Initial intended users: banks/fintech, telecoms, insurance, contact centres, voice-agent developers and public services. These are target segments, not existing customers. VAIS Voice is intended to test vendors' agents independently, rather than replace them.

## Research contribution

The proposed asset is a governed **VAIS Voice Benchmark**: realistic, versioned local scenarios, reviewed annotations and documented failure cases. Such a corpus does not yet exist in this repository. Its value must be demonstrated through coverage, reproducibility, reviewer agreement and ability to catch held-out regressions; market defensibility is a hypothesis.

[Seven annotated scientific sources](docs/scientific-basis.md) explain the methodological basis and limitations. Sources motivate the work; they do not prove VAIS Voice's future effectiveness or business demand.

## Roadmap

- **Weeks 1–4:** governance, scenario taxonomy, sandbox contract, bilingual rubrics and reference annotations.
- **Weeks 5–8:** one agent connector, a 100-call runner and inspectable failure reports; baseline STT/TTS and separate VoiceGuard research evaluation.
- **Weeks 9–12:** paired regression experiments, repeated runs, unseen-condition testing and a restricted demonstration, subject to data and integration readiness.
- **Later:** production observability, policy/compliance workflows, model/vendor comparisons, larger suites, CI integrations and on-premises deployment.

See the [research plan](docs/research-plan.md), [architecture](docs/architecture.md) and [data and ethics](docs/data-and-ethics.md).

## Repository and local setup

The existing repository URL and Python package identifier `kazakh_russian_speech_intelligence` are retained for compatibility. **VAIS Voice** is the current project name; the historical identifier does not limit the new scope.

```text
configs/       Scenario and evaluation configuration guidance
data/          Manifest and local-data rules; no private recordings
docs/          Platform design, protocols, scientific basis, governance
models/        Model cards; weights remain external
notebooks/     Exploration only
src/           Python scaffold (not the platform implementation)
tests/         Scaffold checks, not model-quality validation
```

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

Do not commit raw audio, sensitive transcripts, credentials, customer endpoints, identity mappings or model weights. Calls must target owned or explicitly authorised test systems; tools must use mock transactions, never real money movement or real customer actions.

## Responsible use

Synthetic speech can be legitimate. VoiceGuard is an auxiliary signal, not identity verification, proof of fraud or a reason to deny service by itself. Policy tests are checks against specified rules, not legal certification. Human review remains necessary for ambiguous or high-impact cases.

[Contributing](CONTRIBUTING.md) · [Security](SECURITY.md) · [Citation](CITATION.cff) · [MIT code licence](LICENSE). Data and models retain separate licences.

---

**По-русски:** VAIS Voice — проект платформы тестирования, безопасности и мониторинга голосовых AI-систем для казахско-русской среды. Первый MVP: подключить sandbox голосового агента, выполнить 100 автоматических тестовых звонков и получить отчёт с метриками, аудио и причинами ошибок. VAIS VoiceBench, VoiceGuard, Speech Intelligence и Continuous Evaluation пока находятся на стадии проектирования. Production-мониторинг, enterprise-интеграции и on-prem — дальнейшие этапы, не готовые возможности.
