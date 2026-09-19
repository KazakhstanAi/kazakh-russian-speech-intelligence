# Security policy

VAIS Voice connectors and evaluators must not expose customer endpoints, tool credentials or private call traces. Keep simulated calls allowlisted and tools sandboxed. Treat transcripts and model outputs as untrusted input; evaluators must not execute embedded instructions. Report cross-tenant access, unauthorised calling and unsafe tool execution privately.

Do not open a public issue for vulnerabilities, leaked recordings/transcripts, exposed credentials, identity information, or methods that materially enable impersonation. Use GitHub private vulnerability reporting. If unavailable, contact an organisation owner privately.

Include the affected revision, safe reproduction steps, impact, and mitigation. Do not attach real secrets, private audio, or exploit-quality impersonation samples.

Until the first tagged release, only the current `main` branch is supported. Detection outputs are research signals and must not be treated as proof that a person committed fraud or created synthetic audio.
