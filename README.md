# renovate-config

Shared [Renovate](https://docs.renovatebot.com/) preset for stratione repos.

Each repo opts in with a `renovate.json`:

```json
{ "$schema": "https://docs.renovatebot.com/renovate-schema.json", "extends": ["local>stratione/renovate-config"] }
```

Policy:
- Weekly (Monday before 6am CT) grouped PR for minor/patch updates; GitHub Actions grouped and kept SHA-pinned.
- Majors require approval on each repo's Dependency Dashboard issue.
- `minimumReleaseAge: 3 days` — new releases must age before Renovate proposes them (defense against freshly-published malicious versions, e.g. the 2026-10 Shai-Hulud/Tensorlake worm). Security fixes bypass the delay and schedule.
- Monthly lockfile maintenance. No automerge.
