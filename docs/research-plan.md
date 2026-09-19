# VAIS Voice — 12-week research plan

## Questions and hypotheses

1. Does a locally curated KZ/RU scenario suite reveal regressions missed by monolingual clean-audio tests?
2. Do end-to-end task and tool checks identify failures that WER alone misses?
3. How well do automated bilingual rubrics agree with human reviewers, especially for policy and interruption recovery?
4. How much do codecs, noise, new generators and replay environments degrade VoiceGuard?
5. Are repeated runs and pinned scenarios sufficient for stable version-to-version comparisons within the available budget?

These are hypotheses, not established findings. Compare against clean monolingual evaluation, ASR-only metrics, deterministic rule checks and human review using equal testing budgets.

## Weeks 1–4: benchmark and governance

Define consent, licences, retention, sandbox access and cost limits. Curate scenario families and local entities, prepare reviewed transcripts and expected mock tool outcomes, freeze split policy and metric definitions. Audit relevant public corpora before reuse.

**Gate:** bilingual reviewers can reconstruct approved fixtures and agree on expected outcomes; the connector cannot reach unauthorised destinations or transact against production systems.

## Weeks 5–8: bounded MVP

Implement one sandbox connector and a planned 100-call runner. Save inspectable evidence, implement deterministic assertions and latency measurement, add baseline STT/TTS evaluation. Evaluate a separate VoiceGuard baseline on approved audio; do not promise a joint model or calibrated fraud probability.

**Gate:** calls respect allowlists, cancellation, concurrency and cost caps; every report is traceable to versions. Infrastructure failures are visible, not silently retried away.

## Weeks 9–12: evaluation and restricted demo

Compare two agent revisions using paired fixtures and repeated runs. Audit evaluator agreement with bilingual reviewers. Test held-out speakers, scenarios, codecs and generators, calibrate only on development data, report uncertainty and limitations. Demonstrate regression reports and PASS/FAIL/REVIEW gates.

**Gate:** end-to-end reports, reproducibility instructions, quality/coverage analysis, human review and data-governance checks. If references or integrations are inadequate, publish a feasibility report rather than claim a complete platform.

## Compute planning

The prior ASR-training-first GPU estimate is superseded. Start by measuring cost per simulated call, audio minute, STT/TTS request, judge evaluation and local detector batch. Budget repeats, API quotas and storage retention. GPU training is conditional on a demonstrated adaptation need; no justified GPU-hour figure exists yet.

## After the MVP

Production monitoring, model/vendor comparison, enterprise policy workflows, CI adapters, broader language/channel coverage and on-prem deployments are separate roadmap phases. Access to live customer calls requires new approval and governance.
