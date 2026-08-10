# SHARK Validation

SHARK's validation model is designed to make false confidence expensive.

## Baseline data integrity

The frozen intraday baseline covers 200 symbols and 7,659,672 regular-session five-minute bars across roughly 720 calendar days. Evidence artifacts are hashed and reconciled against canonical PostgreSQL memory.

Identical re-imports are no-ops. Conflicting historical OHLC or volume observations fail closed rather than rewriting the past.

## Point-in-time controls

Research readers require explicit time bounds and, for universe-level work, an exact universe version. Cross-sectional queries operate at exact timestamps. Large scans use bounded or streaming interfaces.

## Experimental controls

A theory-driven experiment should freeze:

- observable
- transformation
- statistic
- horizon
- information set
- acceptance rule

before validation evidence is inspected.

Changing those after inspection creates a new experiment.

## Hostile validation

Candidate states are expected to survive simpler explanations and hostile controls before being treated as interesting. Depending on the experiment, this can include clock effects, persistence controls, null models, surrogate data, cross-sectional comparison, contamination checks, and economic friction analysis.

## Claim boundary

The following are deliberately different claims:

1. A pattern can be reconstructed historically.
2. A state survives independent statistical controls.
3. The state contains predictive information.
4. The information survives realistic execution frictions.
5. A production trading system can capture it reliably.

SHARK does not collapse those steps into one backtest metric. The current public case study makes no claim that step five has been achieved.
