[← Back to Documentation](./index.md) · [← Back to report](../../public_report.md)

# 📝 Documentation — Shard 1

- [📊 Findings](#-findings)
- [🧹 Hygiene](#-hygiene)

## 📊 Findings

| File | Verdict | Documentation | Conf. | Details |
|------|---------|---------------|-------|---------|
| `pkg/retry/retryer.go` | 🟡 NEEDS_REFACTOR | 0 | 95% | [details](#pkgretryretryergo) |
| `pkg/retry/backoff.go` | 🟡 NEEDS_REFACTOR | 0 | 90% | [details](#pkgretrybackoffgo) |

## 🧹 Hygiene

- [ ] <!-- ACT-4e977b-2 --> **[documentation · medium · trivial]** `pkg/retry/backoff.go`: Add Go doc comment documentation for exported symbol:  `Strategy`, `StrategyConstant`, `StrategyLinear`, `StrategyExponential`, `Valid`, `CalculateDelay`, `ApplyJitter` (`Strategy, StrategyConstant, StrategyLinear, StrategyExponential, Valid, CalculateDelay, ApplyJitter`) [L10-L10, L14-L14, L16-L16, L18-L18, L22-L29, L33-L56, L60-L74]
- [ ] <!-- ACT-e84021-3 --> **[documentation · medium · trivial]** `pkg/retry/retryer.go`: Add Go doc comment documentation for exported symbol:  `Config`, `Logger`, `Retryer`, `NewRetryer`, `ShouldRetry`, `NextDelay`, `Wait`, `IsRetryableExitCode` (`Config, Logger, Retryer, NewRetryer, ShouldRetry, NextDelay, Wait, IsRetryableExitCode`) [L11-L19, L22-L25, L28-L32, L35-L41, L44-L54, L57-L67, L70-L90, L93-L109]
