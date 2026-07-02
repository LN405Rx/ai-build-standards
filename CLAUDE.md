# Project Rules — Design & Build Standards (Free Edition)

> Two drop-in standards that give an AI coding assistant a **design quality bar** and a
> **security baseline** on every build. Your assistant should treat everything here as
> always-on context. Free and open-source (MIT).
>
> This free edition includes the two **standards**. Step-by-step **build pipelines**
> (Website, Dashboard, Mobile, Watch) live in the full Skills Edition — see the end.

---

## Governing rule (applies to everything)

**Beauty serves the mission.** Every distinctive or beautiful choice must earn its
place by helping the user do or feel the thing the product is for. If a choice only
impresses, it's decoration — cut it or dial it back. The finished product must **not
look AI-generated**, and must be visually excellent without distracting from the job.

---

## CRAFT STANDARD (always enforce)

### Avoid these "AI-generated" tells
- Default fonts as the whole identity (Inter/Roboto/system left untouched).
- Canned AI looks: beige-cream + serif "editorial"; purple/violet glow gradient; stark
  black-on-white broadsheet; generic rounded-card SaaS template.
- Predictable centered/symmetric everything — no focal point, no hierarchy.
- Uniform rounded cards with identical drop shadows (the grid of identical boxes).
- Decoration for its own sake (gratuitous gradients, glassmorphism, emoji as bullets).
- Filler copy ("elevate," "seamlessly," "unlock the power of," vague button labels).
- Stock-photo / generic-illustration vibe; no custom visual identity.
- No signature — nothing memorable; every screen could belong to any app.

### Produce "crafted" instead
- **One signature element** — a single intentional, memorable thing. Everything else
  stays quiet.
- A distinctive, restrained **type system** (a real typeface + a considered ramp).
- **Intentional hierarchy** — clear focal point, deliberate emphasis, asymmetry where
  the surface allows.
- **Cohesion** — illustration, icons, motion, and copy share one DNA.
- **Specific, human copy** in the product's own voice (microcopy, empty states, errors).
- **Details that reward attention** — considered transitions, handled edge cases, real
  empty states, honest loading.

### Premium = restraint + precision, not ornament
Premium reads through precise alignment and a strict spacing rhythm; restraint (fewer
elements, more space, one accent used sparingly); real materials (genuine type, bespoke
assets); smooth motion (jank is the #1 tell of cheap); tactile feedback; and performance.
Avoid false premium: gratuitous gold-on-black, forced dark mode as costume,
gradients/glass for "richness," decorative luxury serifs, animation to impress.

### Calibrate by surface (don't apply one dial everywhere)
- **Marketing / portfolio** — lean into impact: cinematic hero, a signature interaction.
- **Consumer app** — immersion via custom illustration, character, atmosphere, delight.
- **Operational / regulated dashboard** — NOT cinematic. Crafted = precise, calm, fast,
  trustworthy, dense done right (Linear, Stripe dashboard).
- **Watch** — one perfect legible glance in the safe area, dark and calm. Near-total
  restraint.

---

## SECURITY STANDARD (always enforce)

Nothing is "unhackable." The goal is **defense in depth**: raise attack cost, shrink
attack surface, and assume breach so blast radius stays small. Never claim "unhackable";
verify controls with adversarial testing. *(Engineering guidance, not legal advice.)*

### Classify the data first, then calibrate
- **Regulated health data (PHI)** — highest tier (health-privacy law, BAAs, audit trails).
- **Financial IP & credentials** — high tier; confidentiality and integrity dominate.
- **Children's data** — high tier; strongest control is collecting nothing (local-first,
  no backend, no accounts).
- **General consumer / marketing** — standard tier; still enforce the baseline.

### Core principles (non-negotiable)
- **Least privilege** — minimum access for every user, service, token, process.
- **Minimize attack surface** — fewer endpoints, dependencies, features exposed.
- **Assume breach** — segment and isolate so one compromise doesn't cascade.
- **Secure by default, fail closed** — default locked; on error, deny.
- **Defense in depth** — no single control trusted alone.
- **Never trust the client** — enforce every security decision server-side; never put
  secrets in client code.

### Baseline (all tiers)
Security headers (CSP, HSTS, etc.); secrets in environment variables, never committed;
tokenized payments (card data never touches your servers); parameterized queries and
input validation; dependency hygiene; rate limiting on public endpoints; server-side
authorization with MFA on privileged paths. For PHI/financial/children's data, turn
every knob to its highest setting and get qualified security + legal counsel.

---

## The critique step (run before shipping)
Ask explicitly: *"Does this read as crafted or AI-generated — which tells is it showing?
Does every beautiful choice serve the mission?"* Then fix what fails. For anything with
users, data, auth, or deployment, apply the Security Standard at the calibration the data
class requires.

---

## Build pipelines (full edition)
This free edition ships the two **standards**. The full **Skills Edition** adds
step-by-step **build pipelines** for Website, Dashboard, Mobile App, and Watch App
(each a SKILL.md + Cursor rule), plus a long-form PDF system. See the README for the link.
