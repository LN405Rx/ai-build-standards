---
name: security-hardening
description: Security and safety baseline for any app build. Use when creating or reviewing authentication, data handling, APIs, backends, deployment, or anything touching user data or credentials. Calibrate the level by data sensitivity (regulated health data, financial, children's, or general consumer). Enforces least privilege, never-trust-the-client, secure-by-default, and defense in depth.
---

# Security & Safety Hardening Standard

Apply whenever the work touches users, data, auth, APIs, or deployment.
*(Engineering guidance, not legal advice. For regulated products, consult qualified
security and legal counsel and re-verify time-sensitive requirements.)*

## Premise
Nothing is "unhackable." Never claim it. The goal is **defense in depth**: raise the
cost of attack, shrink the attack surface, and — assuming a breach will eventually
happen — keep blast radius small and detection/recovery fast. Controls are verified
with adversarial testing, not asserted.

## Step 1 — classify the data, then calibrate
- **Regulated health data (PHI)** — highest tier. Health-privacy law (e.g.
  HIPAA/HITECH), business-associate agreements, audit trails, breach notification.
- **Financial IP & credentials** — high tier. Confidentiality and integrity dominate;
  the strategy/algorithm and the broker/market/payment keys are the assets.
- **Children's data** — high tier. Children's-privacy law (e.g. COPPA); the strongest
  control is collecting nothing — local-first, no backend, no accounts.
- **General consumer / marketing** — standard tier. Still enforce the baseline; lower
  blast radius.

Turn every knob to its highest setting for the top three tiers.

## Core principles (non-negotiable)
- **Least privilege** — minimum access for every user, service, token, process.
- **Minimize attack surface** — fewer endpoints, dependencies, ports, features exposed.
- **Assume breach** — segment and isolate so one compromise doesn't cascade.
- **Secure by default, fail closed** — default locked; grant access explicitly; on
  error, deny (never fail open).
- **Defense in depth** — no single control is trusted alone.
- **Never trust the client** — the device/browser is attacker-controlled; enforce all
  security decisions server-side; never ship secrets in client code.

## Baseline controls (all tiers)
- Secrets in environment variables, never committed; rotate on exposure.
- Security headers (CSP, HSTS, X-Content-Type-Options, Referrer-Policy).
- Parameterized queries; validate and sanitize all input; defend against injection.
- Tokenized payments — card data never touches your servers.
- Rate limiting and abuse monitoring on public endpoints/APIs.
- Dependency hygiene — pin, audit, patch; minimize third-party surface.
- AuthZ enforced server-side on every request; MFA on privileged paths.

## Higher-tier additions (PHI / financial / children's)
- Encryption at rest and in transit; strict key management.
- Full audit logging with PII/secrets scrubbed from logs.
- Hard environment isolation (prod separate from dev/preview/agent-reachable envs);
  no real regulated data outside production.
- Signed data-processing agreements with every vendor in the path.
- Least-privilege scoped tokens (e.g. a read-only analytics agent can't write).

## Verify, don't claim
"Nearly impossible to hack" is a tested target: adversarial review, dependency and
secret scanning, and a test restore of backups. An untested backup is a hope, not a
control.
