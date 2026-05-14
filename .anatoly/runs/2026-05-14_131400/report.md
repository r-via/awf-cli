<p align="center">
  <img src="https://raw.githubusercontent.com/r-via/anatoly/main/assets/imgs/logo.jpg" width="400" alt="Anatoly" />
</p>

# Anatoly Audit Report

## Executive Summary

- **Files reviewed:** 3
- **Global verdict:** NEEDS_REFACTOR
- **Clean files:** 1
- **Files with findings:** 2

| Category | High | Medium | Low | Total |
|----------|------|--------|-----|-------|
| Utility | 14 | 1 | 0 | 15 |

## Documentation Reference

.anatoly/docs/ updated: 0 pages

Documentation coverage:
  Fully documented: 0% (0/15 symbols)
  At least partial: 0% (0/15 symbols)
  Modules: 0% (0/2 modules > 200 LOC in project docs)

Internal docs (.anatoly/docs/) coverage:
  Pages generated: 0
  Modules: 0% (0/2 modules > 200 LOC in internal docs)

## Axes

| Axis | Files | Shards | Link |
|------|-------|--------|------|
| Correction | 1 | 1 | [axes/correction/index.md](./axes/correction/index.md) |
| Utility | 2 | 1 | [axes/utility/index.md](./axes/utility/index.md) |
| Documentation | 2 | 1 | [axes/documentation/index.md](./axes/documentation/index.md) |

## Performance & Triage

| Tier | Files | % |
|------|-------|---|
| Skip | 0 | 0% |
| Evaluate | 3 | 100% |

Estimated time saved: **0.0 min**

## Run Statistics

| Metric | Value |
|--------|-------|
| Run ID | `2026-05-14_131400` |
| Duration | 16.9 min |
| API cost | $5.94 |

**Phase durations:**

| Phase | Duration |
|-------|----------|
| scan | 2.4s |
| estimate | 140ms |
| triage | 4ms |
| rag-index | 852.6s |
| review | 81.1s |
| refinement | 74.2s |

**Per-axis breakdown:**

| Axis | Calls | Duration | Cost | Tokens (in/out) |
|------|-------|----------|------|-----------------|
| utility | 3 | 0.0m | $0.00 | 0 / 0 |
| duplication | 3 | 0.5m | $0.03 | 10 / 4523 |
| correction | 3 | 2.5m | $0.57 | 9 / 11493 |

## Axis Summary

**Utility** — 15 symbols evaluated

| Verdict | Count | % |
|---------|-------|---|
| DEAD | 15 | 100% |

**Duplication** — 15 symbols evaluated

| Verdict | Count | % |
|---------|-------|---|
| UNIQUE | 15 | 100% |

**Correction** — 15 symbols evaluated

| Verdict | Count | % |
|---------|-------|---|
| OK | 15 | 100% |

---

## Methodology

Each file is evaluated through 7 independent axis evaluators running in parallel.
Every symbol (function, class, variable, type) is analysed individually and receives a rating per axis along with a confidence score (0–100).
Findings with confidence < 30 are discarded; those with confidence < 60 are excluded from verdict computation.

| Axis | Model | Ratings | Description |
|------|-------|---------|-------------|
| Utility | haiku | USED / DEAD / LOW_VALUE | Is this symbol actually used in the codebase? |
| Duplication | haiku | UNIQUE / DUPLICATE | Is this symbol a copy of logic that exists elsewhere? |
| Correction | sonnet | OK / NEEDS_FIX / ERROR | Does this symbol contain bugs or correctness issues? |
| Overengineering | haiku | LEAN / OVER / ACCEPTABLE | Is the implementation unnecessarily complex? |
| Tests | haiku | GOOD / WEAK / NONE | Does this symbol have adequate test coverage? |
| Best Practices | sonnet | Score 0–10 | Does the file follow Go best practices? |
| Documentation | haiku | DOCUMENTED / PARTIAL / UNDOCUMENTED | Are exported symbols properly documented with Go doc comment? |

See each axis folder for detailed rating criteria and methodology.

### Severity Classification

- **High**: ERROR corrections, or NEEDS_FIX / DEAD / DUPLICATE with confidence >= 80%.
- **Medium**: NEEDS_FIX / DEAD / DUPLICATE with confidence < 80%, or OVER (any confidence).
- **Low**: LOW_VALUE utility or remaining minor findings.

### Verdict Rules

- **CLEAN**: No actionable findings with confidence >= 60%.
- **NEEDS_REFACTOR**: At least one confirmed finding (DEAD, DUPLICATE, OVER, or NEEDS_FIX) with confidence >= 60%.
- **CRITICAL**: At least one ERROR correction found.

### Inter-axis Coherence

After individual evaluation, coherence rules reconcile contradictions:

- If utility = DEAD, tests is forced to NONE (no point testing dead code).
- If utility = DEAD, documentation is forced to UNDOCUMENTED (no point documenting dead code).
- If correction = ERROR, overengineering is forced to ACCEPTABLE (complexity is secondary to correctness).

*Generated: 2026-05-14T11:30:54.433Z*
