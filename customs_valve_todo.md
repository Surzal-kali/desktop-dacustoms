# Customs Valve — TODO (revisit at another time)

Carried out of `dadeb` `evasion_design.md` v0.2 (2026-11-05) — §14 placement policy
and §2 non-goals. The ration engine was approved for the **public red lane
(dadeb)**; §14 reserves a CUSTOMS VALVE for capability-adjacent machinery that
must never ship public. This file is the standing reminder of what that lane
would hold. **DESIGN TODO ONLY — nothing here has been scoped or built.**

## What belongs in customs (per evasion_design.md §14)

- [ ] Synthetic TLS / JA3-fingerprint forging machinery
      (§2 non-goal carries a `[revisit]` marker — the forgery BAN itself is
      revisit-flagged, not fixed doctrine)
- [ ] Anything that manufactures imitation client stacks (fake browser/agent
      stacks beyond what `webshape`'s real-client identity stack already does)
- [ ] Persistence-grade concealment machinery

## Candidates flagged during the v0.2 pass — decide on revisit

- [ ] **Encrypted-payload pairing loader.** `payloads/msfvenom_tools.py`
      ships encrypted raw shellcode only — inert, no decryptor stub, no
      wrapper (decided there). The pairing loader (decrypt + execute at
      runtime) is that module's named future expansion lane; it plausibly
      lands customs-side. Confirm or reject placement.
- [ ] Where the customs boundary meets the lab lane — public/lab/customs is
      a three-way taxonomy; v0.2 only placed two of the three
      (`SHAPING_LAB_MODE=1` presets = lab_only, NOT customs — decided).

## What stays OUT of customs (public-safe, dadeb)

- Driving REAL clients (curl/browser) — genuine fingerprint, public-safe
- `SHAPING_LAB_MODE=1` presets (`decoy`/`fragment`) — commodity nmap flags,
  lab_only (v0.2 §14 taxonomy placement)
- The whole ration engine (budget/fleet/queue/refill/controller) — noise
  shaping + resource accounting, zero capability-addition

## Standing rules if/when the lane materializes

- Customs is NOT tool-discoverable: outside `ALLOWED_TOOL_ROOTS` and outside
  `BRAIN_SCAN_DIRS` — nothing there surfaces via registry discovery or the
  Brain's startup import.
- Constitution authority is the same as the ration engine's: config-authored,
  no model lane writes it; operator/REPL authority only.
- The scope gate remains the authorization predicate above everything,
  unchanged — customs adds no bypass of it.

## Source

- `dadeb`: `/home/kali/github/systempackage/daharness/evasion_design.md` (v0.2,
  §14, §2 non-goals, §11 coherence rule, §16 register row #4)
- v0.2 discussion 2026-11-05: dadeb placement approved; taxonomies placed.
