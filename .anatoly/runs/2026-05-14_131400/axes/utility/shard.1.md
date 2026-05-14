[← Back to Utility](./index.md) · [← Back to report](../../public_report.md)

# ♻️ Utility — Shard 1

- [📊 Findings](#-findings)
- [🔍 Symbol Details](#-symbol-details)
- [⚡ Quick Wins](#-quick-wins)
- [🔧 Refactors](#-refactors)

## 📊 Findings

| File | Verdict | Utility | Conf. | Details |
|------|---------|---------|-------|---------|
| `pkg/retry/retryer.go` | 🟡 NEEDS_REFACTOR | 8 | 95% | [details](#pkgretryretryergo) |
| `pkg/retry/backoff.go` | 🟡 NEEDS_REFACTOR | 7 | 90% | [details](#pkgretrybackoffgo) |

## 🔍 Symbol Details

### `pkg/retry/retryer.go`

| Symbol | Lines | Utility | Conf. | Detail |
|--------|-------|---------|-------|--------|
| `Config` | L11–L19 | 🔴 DEAD | 95% | Exported but imported by 0 files |
| `Logger` | L22–L25 | 🔴 DEAD | 95% | Exported but imported by 0 files |
| `Retryer` | L28–L32 | 🔴 DEAD | 70% | Exported but imported by 0 files |
| `NewRetryer` | L35–L41 | 🔴 DEAD | 90% | Exported but imported by 0 files |
| `ShouldRetry` | L44–L54 | 🔴 DEAD | 85% | Exported but imported by 0 files |
| `NextDelay` | L57–L67 | 🔴 DEAD | 85% | Exported but imported by 0 files |
| `Wait` | L70–L90 | 🔴 DEAD | 95% | Exported but imported by 0 files |
| `IsRetryableExitCode` | L93–L109 | 🔴 DEAD | 82% | Exported but imported by 0 files |

### `pkg/retry/backoff.go`

| Symbol | Lines | Utility | Conf. | Detail |
|--------|-------|---------|-------|--------|
| `Strategy` | L10–L10 | 🔴 DEAD | 90% | Exported but imported by 0 files |
| `StrategyConstant` | L14–L14 | 🔴 DEAD | 90% | Exported but imported by 0 files |
| `StrategyLinear` | L16–L16 | 🔴 DEAD | 90% | Exported but imported by 0 files |
| `StrategyExponential` | L18–L18 | 🔴 DEAD | 90% | Exported but imported by 0 files |
| `Valid` | L22–L29 | 🔴 DEAD | 90% | Exported but imported by 0 files |
| `CalculateDelay` | L33–L56 | 🔴 DEAD | 90% | Exported but imported by 0 files |
| `ApplyJitter` | L60–L74 | 🔴 DEAD | 90% | Exported but imported by 0 files |

## ⚡ Quick Wins

- [ ] <!-- ACT-4e977b-1 --> **[utility · high · trivial]** `pkg/retry/backoff.go`: Remove dead code: `Strategy` is exported but unused `Strategy`, `StrategyConstant`, `StrategyLinear`, `StrategyExponential`, `Valid`, `CalculateDelay`, `ApplyJitter` (`Strategy, StrategyConstant, StrategyLinear, StrategyExponential, Valid, CalculateDelay, ApplyJitter`) [L10-L10, L14-L14, L16-L16, L18-L18, L22-L29, L33-L56, L60-L74]
- [ ] <!-- ACT-e84021-2 --> **[utility · high · trivial]** `pkg/retry/retryer.go`: Remove dead code: `Config` is exported but unused `Config`, `Logger`, `NewRetryer`, `ShouldRetry`, `NextDelay`, `Wait`, `IsRetryableExitCode` (`Config, Logger, NewRetryer, ShouldRetry, NextDelay, Wait, IsRetryableExitCode`) [L11-L19, L22-L25, L35-L41, L44-L54, L57-L67, L70-L90, L93-L109]

## 🔧 Refactors

- [ ] <!-- ACT-e84021-4 --> **[utility · medium · trivial]** `pkg/retry/retryer.go`: Remove dead code: `Retryer` is exported but unused (`Retryer`) [L28-L32]
