# AUTOMATION QUEUE (workspace-wide) — 10 comics/turn cap

## DURABLE-STORAGE PROTOCOL (mandatory since incident 2, 25.09.2026)
The sandbox is re-cloned from GitHub and its artifact patchset is capped — untracked PNGs
and un-pushed commits do NOT survive turn ends. Therefore every turn:
1. Generate → optimize (256-colour PNG) → **commit AND push to
   `origin arena/01a0d70b-grok-build` before the turn ends.**
2. At turn start, if comics are missing: `git fetch origin arena/01a0d70b-grok-build &&
   git checkout origin/arena/01a0d70b-grok-build -- ccs-conduct-rules ccs-cca-rules`
   (or regenerate from the surviving specs).
3. Never leave comics only in the working tree.

## Incident log
- Incident 1 (25.09.2026, Series 1): entire `ccs-cca-rules/` folder (62 comics) evicted —
  cumulative artifacts exceeded the platform cap. Fix attempted: optimization + local git.
- Incident 2 (25.09.2026, Series 2, discovered at C-5 close): Batches C-1–C-4 comic PNGs
  (38) evicted; local git history reset to base clone. All specs/ledger/map text survived.
  Fix: push-per-turn protocol above. Batch C-5's 10 comics pushed immediately.

## Work queue
| Track | Block | Status |
|---|---|---|
| Conduct C-1…C-5 | Rule coverage COMPLETE (48 comics designed, map 100%) | ✅ text/specs complete |
| Conduct regen R-C1 | C1.1–C1.10 regenerated to spec, audited, pushed | ✅ DONE |
| Conduct regen R-C2 | Regenerate C2.1–C2.8 | NEXT |
| Conduct regen R-C3 | Regenerate C3.1–C3.10 | queued |
| Conduct regen R-C4 | Regenerate C4.1–C4.10 | queued |
| CCA regen R1–R7 | 62 comics per `../ccs-cca-rules/REGENERATION-MANIFEST.md` | queued after Conduct regen |

Each regen turn: generate ≤10 comics → optimize → audit → commit → **push**.
