# Review: `pkg/retry/backoff.go`

**Verdict:** NEEDS_REFACTOR

## Symbols

| Symbol | Kind | Exported | Correction | Over-eng. | Utility | Duplication | Tests | Confidence |
|--------|------|----------|------------|-----------|---------|-------------|-------|------------|
| Strategy | type | yes | OK | - | DEAD | UNIQUE | - | 90% |
| StrategyConstant | constant | yes | OK | - | DEAD | UNIQUE | - | 90% |
| StrategyLinear | constant | yes | OK | - | DEAD | UNIQUE | - | 90% |
| StrategyExponential | constant | yes | OK | - | DEAD | UNIQUE | - | 90% |
| Valid | method | yes | OK | - | DEAD | UNIQUE | - | 90% |
| CalculateDelay | function | yes | OK | - | DEAD | UNIQUE | - | 90% |
| ApplyJitter | function | yes | OK | - | DEAD | UNIQUE | - | 90% |

### Details

#### `Strategy` (L10–L10)

- **Utility [DEAD]**: Exported but imported by 0 files
- **Duplication [UNIQUE]**: No similar functions found in codebase
- **Correction [OK]**: Plain string typedef; no logic to evaluate.
- **Overengineering [-]**: *(not evaluated)*
- **Tests [-]**: *(not evaluated)*

#### `StrategyConstant` (L14–L14)

- **Utility [DEAD]**: Exported but imported by 0 files
- **Duplication [UNIQUE]**: No similar functions found in codebase
- **Correction [OK]**: Constant declaration is correct.
- **Overengineering [-]**: *(not evaluated)*
- **Tests [-]**: *(not evaluated)*

#### `StrategyLinear` (L16–L16)

- **Utility [DEAD]**: Exported but imported by 0 files
- **Duplication [UNIQUE]**: No similar functions found in codebase
- **Correction [OK]**: Constant declaration is correct.
- **Overengineering [-]**: *(not evaluated)*
- **Tests [-]**: *(not evaluated)*

#### `StrategyExponential` (L18–L18)

- **Utility [DEAD]**: Exported but imported by 0 files
- **Duplication [UNIQUE]**: No similar functions found in codebase
- **Correction [OK]**: Constant declaration is correct.
- **Overengineering [-]**: *(not evaluated)*
- **Tests [-]**: *(not evaluated)*

#### `Valid` (L22–L29)

- **Utility [DEAD]**: Exported but imported by 0 files
- **Duplication [UNIQUE]**: No similar functions found in codebase
- **Correction [OK]**: Empty string accepted as valid matches CalculateDelay's default-to-constant behaviour; no logic errors.
- **Overengineering [-]**: *(not evaluated)*
- **Tests [-]**: *(not evaluated)*

#### `CalculateDelay` (L33–L56)

- **Utility [DEAD]**: Exported but imported by 0 files
- **Duplication [UNIQUE]**: No similar functions found in codebase
- **Correction [OK]**: All three formulas match their doc-comment specs. Exponential loop produces multiplier^(attempt-1) correctly. maxDelay cap applied after delay computed.
- **Overengineering [-]**: *(not evaluated)*
- **Tests [-]**: *(not evaluated)*

#### `ApplyJitter` (L60–L74)

- **Utility [DEAD]**: Exported but imported by 0 files
- **Duplication [UNIQUE]**: No similar functions found in codebase
- **Correction [OK]**: randomFactor in [-1,1) yields jitterAmount in [-delay*jitter, delay*jitter), consistent with documented ±(delay*jitter) range. Negative-result guard is correct safety net for jitter>1.0 callers.
- **Overengineering [-]**: *(not evaluated)*
- **Tests [-]**: *(not evaluated)*

## Actions

### Quick Wins

- **[utility · high · trivial]** Remove dead code: `Strategy` is exported but unused `Strategy`, `StrategyConstant`, `StrategyLinear`, `StrategyExponential`, `Valid`, `CalculateDelay`, `ApplyJitter` (`Strategy, StrategyConstant, StrategyLinear, StrategyExponential, Valid, CalculateDelay, ApplyJitter`) [L10-L10, L14-L14, L16-L16, L18-L18, L22-L29, L33-L56, L60-L74]

### Hygiene

- **[documentation · medium · trivial]** Add Go doc comment documentation for exported symbol:  `Strategy`, `StrategyConstant`, `StrategyLinear`, `StrategyExponential`, `Valid`, `CalculateDelay`, `ApplyJitter` (`Strategy, StrategyConstant, StrategyLinear, StrategyExponential, Valid, CalculateDelay, ApplyJitter`) [L10-L10, L14-L14, L16-L16, L18-L18, L22-L29, L33-L56, L60-L74]
