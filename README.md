# AI Build Standards — Craft & Security skills for Claude Code / Cursor

Two drop-in standards that give your AI coding assistant a **design quality bar** and a
**security baseline** on every build — so what it ships looks crafted (not AI-generated)
and isn't a security liability.

Free and open-source (MIT). Works with **Claude Code**, **Cursor**, and any tool that
reads a rules file.

---

## Why

AI can build a whole app now, but the default output has tells: default fonts, identical
cards, filler copy — and often no thought given to security. These two standards encode a
point of view on *craft* and a *security baseline*, so your assistant applies them
automatically instead of you re-explaining "make it good and safe" every time.

## What's in here

```
CLAUDE.md                              # always-on rules (drop in your project root)
skills/
  craft-and-distinctiveness/SKILL.md   # the design quality bar
  security-hardening/SKILL.md          # the security baseline
.cursor/rules/
  craft-standard.mdc                   # same, for Cursor (always-on)
  security-standard.mdc
```

## Install

**Claude Code** — copy `CLAUDE.md` into your project root (it's read automatically).
Optionally copy the `skills/` folder so each standard also loads as an on-demand skill.

**Cursor** — copy the `.cursor/` folder into your project root. Both rules are set to
always apply.

**Anything else (Windsurf, etc.)** — paste the contents of `CLAUDE.md` into whatever the
tool calls its rules / custom-instructions file.

## Quick test

Open a project with these installed and ask:
> "Build a landing page for [your idea]. Follow the project rules."

Watch whether it names a signature element, avoids default fonts, calibrates to the
surface, and runs a critique pass. If it does, the standards are working.

## Feedback welcome

This is v1 — issues and PRs welcome. What works, what's missing, what would make it more
useful in your workflow? Genuinely want to hear it.

## License

MIT — use it, fork it, ship it, commercially or not. Engineering guidance, not legal
advice; for regulated products consult qualified counsel.

---

### Want the build pipelines too?

This repo is the free **standards**. If you want the step-by-step **build pipelines** —
Website, Dashboard, Mobile App, and Watch App, each as a SKILL.md + Cursor rule — plus a
long-form PDF version of the whole system, there's a paid **Skills Edition** and PDF
bundle here: 

[https://www.etsy.com/shop/PromptPixelStore](https://www.etsy.com/shop/PromptPixelStore)
[https://gumroad.com/products](https://gumroad.com/products)

Buying it supports the free version. Totally
optional — the standards above stand on their own.
