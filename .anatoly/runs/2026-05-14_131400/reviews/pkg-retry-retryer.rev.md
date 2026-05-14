# Review: `pkg/retry/retryer.go`

**Verdict:** NEEDS_REFACTOR

## Symbols

| Symbol | Kind | Exported | Correction | Over-eng. | Utility | Duplication | Tests | Confidence |
|--------|------|----------|------------|-----------|---------|-------------|-------|------------|
| Config | class | yes | OK | - | DEAD | UNIQUE | - | 95% |
| Logger | type | yes | OK | - | DEAD | UNIQUE | - | 95% |
| Retryer | class | yes | OK | - | DEAD | UNIQUE | - | 70% |
| NewRetryer | function | yes | OK | - | DEAD | UNIQUE | - | 90% |
| ShouldRetry | method | yes | OK | - | DEAD | UNIQUE | - | 85% |
| NextDelay | method | yes | OK | - | DEAD | UNIQUE | - | 85% |
| Wait | method | yes | OK | - | DEAD | UNIQUE | - | 95% |
| IsRetryableExitCode | method | yes | OK | - | DEAD | UNIQUE | - | 82% |

### Details

#### `Config` (L11–L19)

- **Utility [DEAD]**: Exported but imported by 0 files
- **Duplication [UNIQUE]**: No similar types found in RAG search
- **Correction [OK]**: Struct definition; no logic to evaluate.
- **Overengineering [-]**: *(not evaluated)*
- **Tests [-]**: *(not evaluated)*

#### `Logger` (L22–L25)

- **Utility [DEAD]**: Exported but imported by 0 files
- **Duplication [UNIQUE]**: No similar interfaces in RAG search
- **Correction [OK]**: Interface definition; no correctness issues.
- **Overengineering [-]**: *(not evaluated)*
- **Tests [-]**: *(not evaluated)*

#### `Retryer` (L28–L32)

- **Utility [DEAD]**: Exported but imported by 0 files
- **Duplication [UNIQUE]**: No similar struct types found
- **Correction [NEEDS_FIX]**: rng *rand.Rand is not safe for concurrent use; no mutex protects it.
- **Overengineering [-]**: *(not evaluated)*
- **Tests [-]**: *(not evaluated)*

#### `NewRetryer` (L35–L41)

- **Utility [DEAD]**: Exported but imported by 0 files
- **Duplication [UNIQUE]**: No similar constructors in RAG search
- **Correction [OK]**: Initialization is correct; race condition ownership belongs to the struct definition.
- **Overengineering [-]**: *(not evaluated)*
- **Tests [-]**: *(not evaluated)*

#### `ShouldRetry` (L44–L54)

- **Utility [DEAD]**: Exported but imported by 0 files
- **Duplication [UNIQUE]**: Score 0.722 with IsRetryableExitCode. Different contract: ShouldRetry checks attempt limit and delegates; IsRetryableExitCode validates code membership. Non-interchangeable despite structural similarity.
- **Correction [OK]**: Logic is correct assuming callers pass 1-indexed attempt counts consistent with MaxAttempts semantics (MaxAttempts=1 → no retry when attempt=1).
- **Overengineering [-]**: *(not evaluated)*
- **Tests [-]**: *(not evaluated)*

#### `NextDelay` (L57–L67)

- **Utility [DEAD]**: Exported but imported by 0 files
- **Duplication [UNIQUE]**: No similar delay calculation functions
- **Correction [OK]**: Correctly delegates to CalculateDelay and ApplyJitter; no visible logic errors in the delegation chain.
- **Overengineering [-]**: *(not evaluated)*
- **Tests [-]**: *(not evaluated)*

#### `Wait` (L70–L90)

- **Utility [DEAD]**: Exported but imported by 0 files
- **Duplication [UNIQUE]**: No similar context-aware wait functions
- **Correction [OK]**: Context cancellation and timer teardown via defer timer.Stop() are handled correctly.
- **Overengineering [-]**: *(not evaluated)*
- **Tests [-]**: *(not evaluated)*

#### `IsRetryableExitCode` (L93–L109)

- **Utility [DEAD]**: Exported but imported by 0 files
- **Duplication [UNIQUE]**: Score 0.722 vs ShouldRetry, 0.721 vs isRetryableStatus. Semantically distinct: validates exit code membership in configured list; different contexts prevent interchangeability.
- **Correction [OK]**: Correctly short-circuits on zero, allows any non-zero when allowlist is empty, and performs linear scan of explicit allowlist.
- **Overengineering [-]**: *(not evaluated)*
- **Tests [-]**: *(not evaluated)*

## Actions

### Quick Wins

- **[correction · medium · small]** Guard rng with a sync.Mutex in Retryer (or switch to a locked rand source) to prevent data races when Wait/NextDelay are called concurrently on the same instance. [L31]
- **[utility · high · trivial]** Remove dead code: `Config` is exported but unused `Config`, `Logger`, `NewRetryer`, `ShouldRetry`, `NextDelay`, `Wait`, `IsRetryableExitCode` (`Config, Logger, NewRetryer, ShouldRetry, NextDelay, Wait, IsRetryableExitCode`) [L11-L19, L22-L25, L35-L41, L44-L54, L57-L67, L70-L90, L93-L109]

### Refactors

- **[utility · medium · trivial]** Remove dead code: `Retryer` is exported but unused (`Retryer`) [L28-L32]

### Hygiene

- **[documentation · medium · trivial]** Add Go doc comment documentation for exported symbol:  `Config`, `Logger`, `Retryer`, `NewRetryer`, `ShouldRetry`, `NextDelay`, `Wait`, `IsRetryableExitCode` (`Config, Logger, Retryer, NewRetryer, ShouldRetry, NextDelay, Wait, IsRetryableExitCode`) [L11-L19, L22-L25, L28-L32, L35-L41, L44-L54, L57-L67, L70-L90, L93-L109]
