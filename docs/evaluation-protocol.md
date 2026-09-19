# Evaluation protocol — proposed, not validated results

## Benchmark design

Start with a versioned 100-call suite stratified across KZ, RU and mixed speech, local entities, realistic tasks, channel degradation and interruptions. Publish exact slice counts before running; 100 calls cannot adequately cover every combination. Separate development scenarios from held-out templates, speakers, source recordings and synthetic derivatives. Keep unseen generators/channels for VoiceGuard evaluation.

Repeat stochastic scenarios and pair agent versions on the same fixtures. Report confidence intervals, sample counts, retries, timeouts and missing observations. Never tune thresholds against held-out results.

## Metrics

| Output | Definition / evidence |
| --- | --- |
| Task completion | Goal reached / attempted eligible tasks, checked against mock backend state; failed calls stay in denominator. |
| Kazakh / Russian | WER and CER on human reference transcripts with a frozen normalization policy; report separately, not as generic “accuracy”. |
| Code-switching | WER around annotated switch spans, token language-ID F1 and local-entity exact match with alignment rules. |
| Intent accuracy | Correct reference intent / labelled utterances; retain unknown/out-of-scope cases. |
| P95 response latency | 95th percentile from annotated user-turn end to first audible agent response; report network/codec setup and timeouts separately. |
| Tool-call success | Correct tool, validated arguments and intended mock state transition / expected invocations; report extra harmful calls separately. |
| Interruption recovery | Resumption at the correct workflow state and response to the interjection / annotated interruptions; separately measure stop latency. |
| Grounding / hallucinations | Unsupported claims against scenario evidence, with inspected traces and bilingual review for disputed cases. |
| Policy violations / critical failures | Counts and rates against predeclared, versioned rules and severity taxonomy; not a claim of legal compliance. |
| TTS | Native-speaker intelligibility, naturalness and local-name/number pronunciation; acoustic predictors are supplementary and require local validation. |
| VoiceGuard | EER for comparison; fixed-threshold FPR/FNR, PR-AUC and calibration on held-out languages, attacks and channels. Use min t-DCF only when an ASV tandem protocol and costs are specified. |

A VoiceGuard score is not a probability unless calibrated and validated for the stated deployment distribution. Distinguish synthetic, replay and bona fide samples; report uncertainty or abstention instead of invented confidence.

## Regression gate

- **FAIL:** a predeclared critical rule fails, or a sufficiently supported regression exceeds the agreed tolerance.
- **PASS:** coverage is adequate and all predeclared checks satisfy their thresholds.
- **REVIEW:** missing references, insufficient sample size, judge disagreement, infrastructure errors or distribution shift.

Agree tolerances, minimum slice sizes, repeated-run budget and critical rules before evaluation. A sample count of 100 is an MVP workload, not a universal pass standard.

Use deterministic backend assertions wherever possible. Validate LLM judges against bilingual human labels, track agreement by metric and version rubrics. Judge prompts must treat call contents as untrusted data and must have no transaction authority.

## Failure report

Each failure retains approved audio, transcript, expected/actual behaviour, failure reason, relevant tool events, latency timestamps, language/channel slice and evaluator provenance. Sensitive evidence remains access controlled; exported summaries are redacted.
