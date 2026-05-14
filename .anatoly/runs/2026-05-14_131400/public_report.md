<p align="center">
  <img src="https://raw.githubusercontent.com/r-via/anatoly/main/assets/imgs/logo.jpg" width="400" alt="Anatoly" />
</p>

# Anatoly Audit Report

> **3 files** reviewed in **17 min** — **$5.94** in AI analysis so you don't have to.
> Verdict: **NEEDS_REFACTOR** · 15 findings in 2 files

## Axes

| Axis | Health | Findings | Details |
|------|--------|----------|---------|
| Correction | 🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩 100% OK | — | [View →](./axes/correction/index.md) |
| Utility | ⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜ 0% used | 14 high · 1 med | [View →](./axes/utility/index.md) |
| Duplication | 🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩 100% unique | All clear | — |
| Overengineering | 🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩 No data | All clear | — |
| Tests | 🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩 No data | All clear | — |
| Documentation | 🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩 100% documented | — | [View →](./axes/documentation/index.md) |
| Best Practices | 🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩 No data | All clear | — |

## Top Findings

### 🐛 Correction

✨ **CLEAN** — Only low-confidence findings. [View details →](./axes/correction/index.md)

### ♻️ Utility

> Showing top 5 of 15 findings. [View all →](./axes/utility/index.md)

- 🔴 **pkg/retry/retryer.go** `Config` — Exported but imported by 0 files
- 🔴 **pkg/retry/retryer.go** `Logger` — Exported but imported by 0 files
- 🔴 **pkg/retry/retryer.go** `Wait` — Exported but imported by 0 files
- 🔴 **pkg/retry/backoff.go** `Strategy` — Exported but imported by 0 files
- 🔴 **pkg/retry/backoff.go** `StrategyConstant` — Exported but imported by 0 files

### 📋 Duplication

✨ **CLEAN** — No issues found!

### 🏗️ Overengineering

✨ **CLEAN** — No issues found!

### 🧪 Tests

✨ **CLEAN** — No issues found!

### 📝 Documentation

✨ **CLEAN** — Only low-confidence findings. [View details →](./axes/documentation/index.md)

### ✅ Best Practices

✨ **CLEAN** — No issues found!

## Documentation Coverage

Measures inline doc comments (`///` in Rust, `/** */` in JS/TS, docstrings in Python) on exported symbols.
Anatoly also generates reference pages in `.anatoly/docs/` for every reviewed module.

**Project docs (docs/):**

| Metric | Coverage | Description |
|--------|----------|-------------|
| Complete doc comments | ⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜ 0% (0/15) | Exported symbols with a complete inline doc comment covering description, params, and return |
| Any doc comment | ⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜ 0% (0/15) | Exported symbols with at least a partial inline doc comment |
| Module guides | ⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜ 0% (0/2) | Modules > 200 LOC with a dedicated page in docs/ |

**Internal docs (.anatoly/docs/):**

| Metric | Coverage | Description |
|--------|----------|-------------|
| Reference pages | 0 pages | Anatoly-generated module and API reference pages |
| Module guides | ⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜ 0% (0/2) | Modules > 200 LOC with a page in .anatoly/docs/ |

> Check the internal Anatoly docs in `.anatoly/docs/` or simply replace your current `docs/` with the internal docs to speed up future Anatoly runs.


## 📚 Documentation

Anatoly generated a complete documentation for this project during the audit.

**[Browse the documentation →](./docs/index.md)**

---

<details>
<summary><strong>Run Details</strong></summary>

Run `2026-05-14_131400` · 16.9 min · $5.94

| Axis | Calls | Duration | Cost | Tokens (in/out) |
|------|-------|----------|------|-----------------|
| utility | 3 | 0.0m | $0.00 | 0 / 0 |
| duplication | 3 | 0.5m | $0.03 | 10 / 4523 |
| correction | 3 | 2.5m | $0.57 | 9 / 11493 |

**Phase durations:**

| Phase | Duration |
|-------|----------|
| scan | 2.4s |
| estimate | 140ms |
| triage | 4ms |
| rag-index | 852.6s |
| review | 81.1s |
| refinement | 74.2s |

</details>

<details>
<summary><strong>Methodology</strong></summary>

Each file is evaluated through 7 independent axis evaluators running in parallel.
Every symbol is analysed individually with a confidence score (0–100).
Findings below 30% confidence are discarded; those below 60% are excluded from verdicts.

**Verdicts:** CLEAN (no findings) · NEEDS_REFACTOR (confirmed findings) · CRITICAL (ERROR-level bugs)

**Severity:** High = ERROR or high-confidence NEEDS_FIX/DEAD/DUPLICATE · Medium = lower confidence or OVER · Low = minor

See each axis folder for detailed rating criteria.

</details>

*Generated: 2026-05-14T11:30:54.435Z*
