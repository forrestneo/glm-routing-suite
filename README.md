# glm-routing-suite

A [ZCode](https://zcode.z.ai) plugin ported from [yjh051108/dsh-routing-suite](https://github.com/yjh051108/dsh-routing-suite) (MIT/Apache-2.0): **four-stage workflow + delivery evidence gate + graded task protocol (with red-team gates) + a soft stage gate + spec/react variant presets**, adapted for the GLM session model.

Core promise: **zero injection by default** — installing changes nothing until you opt in (the upstream "not triggered = official behavior" iron law).

## Install in ZCode

**Option A — CDN marketplace (works everywhere, including networks where github.com is blocked):**

Plugin Marketplace → Add → Add Plugin Marketplace → paste:

```
https://cdn.jsdelivr.net/gh/forrestneo/glm-routing-suite@main/marketplace-cdn.json
```

**Option B — this repository directly:**

```
https://github.com/forrestneo/glm-routing-suite
```

Then: Personal → forrestneo-glm-routing-suite → glm-routing-suite → Install.

## Capabilities

| Capability | Entry | Notes |
|---|---|---|
| Task classification | `scripts/route.py` | Bilingual CN/EN regex: build/fix/weak (local, milliseconds, zero tokens) |
| Four-stage workflow | SKILL protocol | understanding→planning→development→verification; completion-signal advancement; tool use never skips |
| Delivery gate | `scripts/delivery_check.py` | Mandatory before declaring done: file checks + 8 evidence kinds + reviewed visuals + numeric hint |
| Graded task protocol | `scripts/graded.py` | Seven steps: star → two-tier spec gating (all-required) → review → marks (red-team gate) → final |
| Soft stage gate | PreToolUse hook | Holds write/edit during graded spec stages; state-file tamper protection; auto-downgrade after 3 consecutive blocks |
| Variant presets | `scripts/suite_mode.py preset` | standard / spec (deep-think first) / react (hands-on first) reminder styles |

Full docs: [plugins/glm-routing-suite/README.md](./plugins/glm-routing-suite/README.md).

## Measured-claims labeling

Upstream behavioral numbers (DSH+DeepSeek, P1-P23) are cited as design rationale only, not reproduced here; the alignment benefit on GLM-5.3 is **unverified** by an n=40 on/off A/B (labeled in the plugin README). The deterministic parts (34 exhaustive state-machine tests, 13 gate tests) all pass.

## License

MIT (the port); upstream component licenses in [NOTICE](./plugins/glm-routing-suite/NOTICE) (router-standard=MIT, graded=Apache-2.0 semantic port).
