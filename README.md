# Founder Playbook

> **The Skill is open source. The underlying research datasets, private knowledge base, and proprietary research materials are not included in this repository and are not licensed under this project license.**

A data-driven decision engine for founders. Distilled from **12,149 real founder case studies**, it walks you through the entire startup journey — direction selection, demand validation, cold start, customer acquisition, monetization, and knowing when to quit.

No generic advice. Every recommendation ships with a **generality score** (how often the pattern appeared across the sample) and a **verifiable real-world case** you can trace back to.

## Why this exists

Most startup advice is vibes. This is the opposite: a set of executable rules distilled from thousands of real founder stories, each tagged with how generalizable it is and grounded in actual cases.

- **Five iron rules** distilled from the data (validate before building, give value before acquiring, narrow-and-deep beats broad-and-shallow, diversify lifelines while focusing attack, profit over revenue).
- **Decision flow** across 6 phases: profile → direction → validation → cold start → acquisition → kill-switch/calibration.
- **Self-correcting**: maintains a per-project archive (`~/ventures/<project>/profile.json`) and recalibrates its judgment as your real results come in.
- **Works offline**: all knowledge is embedded in the `reference/` library. No network or external dependencies at runtime.

## What's inside

```
founder-playbook/
├── SKILL.md                          # Main flow (decision engine)
└── reference/
    ├── direction_playbook.md         # Direction selection + validation (10 idea sources, 9 validation methods)
    ├── coldstart_playbook.md         # Cold start + first customers (12 paths)
    ├── acquisition_playbook.md       # Customer acquisition (38 tactics, 6 meta-patterns)
    ├── failure_playbook.md           # Kill-switch signals + anti-patterns
    ├── benchmarks_report.md          # Revenue percentiles + category matrix + team effects
    └── benchmarks.json               # Structured benchmarks (data source for the report)
```

## The five iron rules

1. **Validate before you build** — paid traction is the only hard signal. Likes, email signups, and friend approval don't count.
2. **Give value before acquiring** — community help, free tools, public work: all are trust-first conversion.
3. **Narrow and deep beats broad and shallow** — one audience, one pain point wins over "selling everything".
4. **Diversify lifelines, focus your attack** — no single channel/platform/customer/founder bottleneck; but attack one niche, one offer, one channel.
5. **Profit over revenue** — negative unit economics at scale is accelerated death.

## How to use it

Load `SKILL.md` as your agent skill, then walk through the phases:

| Phase | What it does | Reference |
|---|---|---|
| 0 — Profile | Collect the founder's skills, budget, time, audience, and edge | — |
| 1 — Direction | Match idea sources to profile, set revenue expectations by category | `direction_playbook`, `benchmarks_report` |
| 2 — Validation | Run the 9 validation methods, cheapest first; paid customers are the pass bar | `direction_playbook` |
| 3 — Cold start | Start from trust relationships or value-first, not ads | `coldstart_playbook` |
| 4 — Acquisition | Pick 1–2 channels by business type, stay focused | `acquisition_playbook` |
| 5 — Kill-switch | Proactively scan for single-point dependency, negative unit economics, founder burnout | `failure_playbook` |
| 6 — Calibration | Record every decision; update the project archive when results come back | `~/ventures/<project>/profile.json` |

Each phase is conservative by default; the skill switches to an aggressive mode only when the window is short, failure is affordable, and the founder has a unique edge — with a double kill-switch (time box + money box) as guardrails.

## Data & limitations

The numbers in `benchmarks_report.md` / `benchmarks.json` are computed from a dataset of real founder businesses. Read them with the following caveats:

- **Survivorship bias**: only profitable businesses are in the sample — failure cases are absent, so all distributions skew optimistic.
- **Self-reported revenue**: figures are self-reported/estimated, unverified, and point-in-time.
- **Coverage skew**: only ~29% of profiles carry revenue data; category-level samples are small (15–24 each).
- **No attribution**: channel data is mention-frequency, not causal effectiveness.
- **Industry/geo skew**: software/content/e-commerce and English-speaking markets dominate.

Use this data to answer *"what do successful founders look like and what did they do"* — not *"what is my expected revenue"*.

## License

[Apache License 2.0](LICENSE)

The Skill itself is open source under the Apache License 2.0. The underlying research datasets, private knowledge base, and proprietary research materials are not included in this repository and are not licensed under this project license.
