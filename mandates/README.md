# The factory

Three BAND Desktop seats, each with a fixed, generic role that doesn't
change between stages or between hackathon tracks. What changes stage to
stage is the task posted into the room — never the seats' own standing
instructions. This split is deliberate: it's the same shape whether the
room is building a wallet, a scheduler, or anything else.

| Seat | Role | Mandate |
| --- | --- | --- |
| `sipa-os_v3` | Builder | [builder.md](builder.md) |
| `sipa-os_dark_v4` | Verifier | [verifier.md](verifier.md) |
| `sipa-os-core` | Integrator | [integrator.md](integrator.md) |

## Why this split

- **Builder** writes to the task, not from memory of what the product is "supposed to be" — it only knows what's in the room.
- **Verifier** never trusts the Builder's own account of whether something works — it re-derives pass/fail from the stage's own test suite.
- **Integrator** is the only seat that touches cross-stage concerns (container build, dependency wiring, the exportable structure) — Builder and Verifier stay scoped to one stage at a time.

No seat's mandate names a track, an endpoint, a field, an error code, or a
test id. Anything track-specific belongs in the task posted to the room,
never in these files.
