# VAIS Voice — focused 12-week research plan

## Research question

How reliably can synthetic speech be distinguished from genuine speech in Kazakh, Russian and mixed-language recordings when generators and audio channels differ from training?

The benchmark is R&D evidence for this detector, not the product itself.

## Weeks 1–4: data and baselines

Audit licences/consent and label provenance for genuine and synthetic corpora. Create leakage-safe speaker/source/derivative splits and hold out generator families. Define matched preprocessing and quality checks. Reproduce simple spectral and established anti-spoof baselines.

**Gate:** traceable approved samples, split audit and reproducible baseline report; no claims based on unknown rights or labels.

## Weeks 5–8: robustness and calibration

Evaluate language slices, unseen generators, codec/noise shifts, repeated encoding and re-recording. Fit calibration on held-out development data. Select a model with documented compute/latency constraints.

**Gate:** frozen model/configuration, operating threshold and calibrator; independent test remains untouched until selection completes.

## Weeks 9–12: product prototype

Implement bounded audio upload, isolated decoding, inference and a versioned report. Publish benchmark methodology and aggregate results, with a restricted demo using permitted samples. Clearly report unsupported inputs, score direction, calibration scope and uncertainty.

**Gate:** reproducible held-out metrics plus a safe web/API prototype; no prototype is claimed before it exists. If data/model gates fail, publish the feasibility findings rather than promising reliable detection.

## Compute planning

Measure throughput and memory for chosen baselines first. Budget adaptation, independent runs, robustness matrices and calibration separately. Storage depends on licensed audio, protected source/derivative manifests and retention. No justified fixed GPU-hour commitment exists yet.

## Later

Streaming inference, batch API, enterprise deployment, on-premises operation and additional anti-spoof scenarios/integrations. Genuine replay is not synthetic speech; replay detection is a separate validation scope.
