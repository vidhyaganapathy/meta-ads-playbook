# 01 · Account structure

## Lead gen (B2B or service)

```
Campaign: Leads objective
├── Ad set: Broad (location + age only)
│   └── 3–6 ads: different hooks and formats
├── Ad set: Retargeting (site visitors, video viewers, engagers)
│   └── 2–4 ads: proof, case study, offer reminder
└── (Optional) Ad set: Lookalike of qualified leads
```

- **Destination:** instant form for volume, website for quality. Test both; judge on qualified leads.
- **Instant form:** add a qualifying question (role, company size, budget or timeline) so low-intent leads filter themselves out.
- **Conversion event:** send qualified leads back to Meta (Conversions API or CRM integration) when possible, so delivery learns what a *good* lead looks like.

## App installs (consumer)

```
Campaign: App promotion objective
├── Ad set: Broad
│   └── 4–8 ads: UGC, demo, creator, problem/solution
└── Ad set: Re-engagement (installed, not activated)
```

- **Optimise for an in-app event** (signup, first key action) once volume allows, not just installs.
- **Judge on cost per activated user**, not cost per install.

## Budget and learning

- Keep ad sets few and budgets meaningful, so each exits the learning phase.
- Avoid big edits mid-test (budget swings, audience changes, swapping all creative at once).
- Scale budgets in steps rather than doubling overnight.

## Naming convention

```
Campaign: [Brand]_[Objective]_[Market]_[Date]
Ad set:   [Audience]_[Placement]_[Optimisation event]
Ad:       [Concept]_[Hook]_[Format]_[Version]

e.g. AppX_Installs_AU_2026-11 / Broad_Auto_Signup / Demo_HookB_Reel_v2
```

## UTMs

```
utm_source=meta&utm_medium=paid_social&utm_campaign={{campaign.name}}&utm_content={{ad.name}}
```
Meta's dynamic URL parameters fill in names automatically, so reporting stays consistent.
