# SHARK Validation

SHARK's validation model is designed to make false confidence expensive.

## Baseline data integrity

The frozen intraday baseline covers **200 symbols and 7,659,672 regular-session five-minute bars** across roughly 720 calendar days. Evidence artifacts are hashed and reconciled against canonical PostgreSQL memory.

Identical re-imports are no-ops. Conflicting historical OHLC or volume observations fail closed rather than rewriting the past.

## Pattern-engine proof surface

The accepted retrospective gate records:

- **356 non-PostgreSQL tests**
- **152 native disposable-PostgreSQL tests**
- **508 passing tests in the combined gate**
- **174 focused Pattern Engine Room tests**
- three built-in detector families
- deterministic candidate and result fingerprints
- no-lookahead mutation proofs
- persisted result-digest reconstruction
- immutable update/delete refusal
- database-outage failure and recovery checks

The engine centrally re-validates detector output rather than trusting a detector module simply because it compiled. Candidate identity, source window, anchors, representation membership, fingerprints, measurement authority, and persisted result identity are all independently checked.

## Point-in-time controls

Research readers require explicit time bounds and, for universe-level work, an exact universe version. Cross-sectional queries operate at exact timestamps. Large scans use bounded or streaming interfaces.

A detector receives only the slice and representation store permitted by its declared measurement context. An unavailable research horizon receives no market-data authority rather than an empty object that could later be populated accidentally.

## Completed frozen experiment

`O0-MA-5M-MAGNITUDE-ACTIVITY-STRUCTURE-v1` is a completed research closure record with a frozen specification, canonical input identity, universe manifest, deterministic seed, immutable result bundle, and `FRESH_RUN` reproducibility label.

The accepted run used:

- 13 symbols
- 120 sessions per symbol
- 60 TRAIN, 30 CONFIRMATION, and 30 FINAL HOLDOUT sessions
- native 5-minute bars
- 12 lags spanning 5 to 60 minutes
- 5,000 permutation or circular-null replicates where specified
- 10,000 session-cluster bootstrap replicates where specified

### Stage A: primitive persistence

On final holdout, clock-normalized absolute return magnitude, log volume, and log trade count each qualified at lags of 20 to 60 minutes.

At the smallest qualifying lag:

- all **13/13 symbols** agreed in sign for all three primary observables
- log volume and log trade count reached the permutation-null resolution floor for all 13 symbols
- absolute return magnitude was weaker, with **8/13 symbols** reaching the pre-specified multiple-testing threshold

This establishes persistence of magnitude and activity under that experimental window. It does not establish signed-return predictability.

### Stage B: stronger joint-state hypothesis rejected

The experiment then asked whether magnitude×volume or magnitude×trade-count states carried incremental persistence beyond independently persistent marginals.

The joint statistic was positive, its bootstrap interval excluded zero, the cross-symbol sign gate passed, and the pooled result excluding AAPL stayed positive. However, the frozen circular-displacement null was not rejected after multiple-testing correction.

Result:

- **0 of 12 magnitude×volume family-lags qualified**
- **0 of 12 magnitude×trade-count family-lags qualified**
- **0 of 24 joint family-lag tests qualified overall**
- smallest adjusted q-value: **0.175165**, above the frozen 0.05 gate

The final experiment verdict is:

> **`PASS_PRIMITIVE_PERSISTENCE_ONLY`**

The stronger joint-state hypothesis was not promoted.

## Corrections before scientific output

The experiment closure record also preserves implementation defects found before Stage A or Stage B statistics were visible. Among them:

- repeated bootstrap session draws were being collapsed instead of treated as repeated clusters
- RNG identity could collide between symbols with equal-length names
- missing canonical-complete-through metadata could default too permissively
- one Stage B path could silently fall back to uniform state weights because the wrong session set was supplied
- the first execution design projected roughly 183 hours of sequential runtime

The fixes were made before scientific output. The accepted run used deterministic worker-independent RNG and completed in about **22 minutes** on eight workers with no change to the frozen statistic. The closure record explicitly reports **no post-result scientific adaptation**.

## Experimental controls

A theory-driven experiment freezes the observable, transformation, statistic, horizon, information set, null, and acceptance rule before validation evidence is inspected.

Changing those after inspection creates a new experiment and requires new evidence.

## Claim boundary

The following are different claims:

1. A pattern can be reconstructed historically.
2. A state survives independent statistical controls.
3. The state contains predictive information.
4. The information survives realistic execution frictions.
5. A production trading system can capture it reliably.

SHARK does not collapse those steps into one backtest metric. The current public case study makes no claim that steps three through five follow from the completed state-persistence experiment.
