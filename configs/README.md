# Experiment configurations

VAIS Voice configuration designs cover scenario suites, authorised agent connectors, STT/TTS baselines, VoiceGuard and regression gates. Record scenario and agent versions, codec/noise profile, call limits, timeouts, evaluator versions and PASS/FAIL/REVIEW policy. Connector secrets and real destination numbers stay outside Git. No working runner is provided yet.

Committed configurations must be declarative and contain no credentials, personal information, private URLs, or machine-specific absolute paths. Every result should identify its configuration, code revision, data manifest, speaker/attack split, random seed, and runtime environment.
