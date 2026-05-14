[← Back to Correction](./index.md) · [← Back to report](../../public_report.md)

# 🐛 Correction — Shard 1

- [📊 Findings](#-findings)
- [⚡ Quick Wins](#-quick-wins)

## 📊 Findings

| File | Verdict | Correction | Conf. | Details |
|------|---------|------------|-------|---------|
| `pkg/retry/retryer.go` | 🟡 NEEDS_REFACTOR | 0 | 95% | [details](#pkgretryretryergo) |

## ⚡ Quick Wins

- [ ] <!-- ACT-e84021-1 --> **[correction · medium · small]** `pkg/retry/retryer.go`: Guard rng with a sync.Mutex in Retryer (or switch to a locked rand source) to prevent data races when Wait/NextDelay are called concurrently on the same instance. [L31]
