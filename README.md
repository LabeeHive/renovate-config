# renovate-config

Org-wide Renovate inheritance config and shared preset for `LabeeHive`.

## What this repo does

The Mend-hosted Renovate App auto-discovers `<org>/renovate-config/org-inherited-config.json` and applies it to every Renovate run across the org — no per-repo setup required.

This repo also hosts the shared `default.json5` preset that every onboarded repo extends.

```
┌────────────────────────────────────┐
│  Mend-hosted Renovate App          │
└────────────────┬───────────────────┘
                 │ reads on every run
                 ▼
┌────────────────────────────────────┐
│ org-inherited-config.json          │  ← this repo
└────────────────┬───────────────────┘
                 │ shapes onboarding PR
                 ▼
┌────────────────────────────────────┐
│ each repo in the org               │
│   .github/renovate.json5           │
│   extends:                         │
│     github>LabeeHive/              │
│       renovate-config:default.json5│──┐
└────────────────────────────────────┘  │
                                        │
                ┌───────────────────────┘
                ▼
┌────────────────────────────────────┐
│ default.json5  (shared preset)     │  ← this repo
└────────────────────────────────────┘
```

## Conventions (Mend-hosted, non-negotiable)

- Repo name must be `renovate-config`
- File name must be `org-inherited-config.json`
- This repo does not need to be onboarded
- Renovate App must be installed on this repo for it to be read

## References

- [Mend-hosted Apps Configuration](https://docs.mend.io/integrations/renovate/getting-started-with-mend-hosted-renovate-app)
- [Renovate Configuration Overview](https://docs.renovatebot.com/configuration-options/)
- [Inherited Config Schema](https://docs.renovatebot.com/renovate-inherited-schema.json)
- [`config:best-practices` preset](https://docs.renovatebot.com/presets-config/#configbest-practices)
