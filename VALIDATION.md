# SHARK Validation

SHARK's validation model is designed to make false confidence expensive.

## Baseline data integrity

The frozen intraday baseline covers **200 symbols and 7,659,672 regular-session five-minute bars** across approximately 720 calendar days. Evidence artifacts are hashed and reconciled against canonical PostgreSQL memory.

Identical re-imports are no-ops. Conflicting historical observations fail closed rather than rewriting prior state.

Every canonical bar preserves provenance to the evidence object that produced it.

## Local proof surface

The current repository gate contains more than **1,000 automated tests** across mathematical, database, storage, research-memory, and scientific-lifecycle surfaces, plus **174 focused Pattern Engine tests** and executable proofs.

The useful fact is not the count. The gate exercises failure modes that can change scientific meaning, including:

- point-in-time and no-lookahead boundaries
- immutable evidence and canonical provenance
- exact universe identity
- deterministic candidate and result reconstruction
- database outage and recovery
- statistical randomization identity
- research-memory graph integrity
- evidence-exposure authority
- Context Pack determinism
- frozen experiment identity
- scientific closure and fail-closed verification

Scientific verification is part of the ordinary local gate and cannot be bypassed while still producing the repository's verification pass.

## Point-in-time controls

Research readers require explicit time bounds and, for universe-level work, an exact universe version. Cross-sectional queries operate at exact timestamps. Large scans use bounded or streaming interfaces.

An experiment receives only the data permitted by its declared measurement context. Future observations cannot alter the representation or candidate that existed at cutoff `T`.

The current Liquid-200 universe is itself a point-in-time object. Applying its membership to earlier history does not create a survivorship-free historical universe, and SHARK does not make that claim.

## Scientific lifecycle controls

A theory-driven experiment freezes the scientific question and its governing objects before independent evidence is inspected.

Depending on the experiment, the frozen contract can include the observable, transformation, statistic, horizon, information set, null model, acceptance rule, scientific code identity, data identity, and protocol identity.

Changing a scientific claim after exposure creates a new scientific state. It does not silently rewrite the authority of the earlier evidence.

SHARK OS additionally records whether evidence has already been exposed. Re-reading evidence for forensic analysis can change interpretation but cannot restore untouched confirmatory authority.

## Completed magnitude/activity line

The original frozen experiment tested whether clock-normalized return magnitude, log volume, and log trade count showed persistent within-session structure, and whether magnitude/activity joint states added incremental persistence beyond the marginals.

The original machine verdict was:

> **`PASS_PRIMITIVE_PERSISTENCE_ONLY`**

A subsequent forensic reanalysis of the already-exposed evidence corrected the lag-specific inference and superseded the initial interpretation.

The accepted scientific conclusion is:

- **log volume persistence survives** the corrected inference over the tested 20 to 60 minute region
- **log trade-count persistence survives** over the tested region, with the final boundary slightly narrower at the longest lag
- **absolute-return magnitude persistence does not survive** the corrected inference standard
- the isolated incremental joint-state finding was confirmation-only and did not reproduce on final evidence
- no stable incremental state was established

The branch is closed rather than retuned on the same information.

This line established no signed-return predictability, executable alpha, profitability, or economic value.

## Methodological red-team example

A later time-asymmetry candidate was deliberately attacked before it was allowed to inspect market data.

Its mandatory valid-null calibration failed decisively:

```text
nominal test size: 5%
rejections under valid synthetic null: 1,815 / 2,000
observed rejection rate: 90.75%
```

The instrument was killed before market evidence was spent.

The underlying market hypothesis therefore remains **untested**, not refuted. The scientific result is that the proposed testing procedure was invalid for its intended use.

The failure is now retained as a methodological lesson: subsequent statistical instruments must earn calibration under hostile valid-null conditions before untouched evidence receives authority.

## Corrections are part of the scientific record

SHARK does not require the first interpretation or first implementation to remain correct.

Examples from the completed programme include:

- cluster-bootstrap resampling that initially collapsed repeated session draws
- random-seed identity that could collide across equal-length symbol names
- canonical-completeness metadata that could default too permissively
- a weighting path that could fall back to the wrong state weights
- an initial scientific interpretation later narrowed by corrected inference
- a later statistical instrument killed because its nominal null calibration was invalid

The relevant distinction is whether the correction occurred transparently and what evidence had already been exposed when it occurred.

Historical machine outputs remain preserved. Current research authority follows the accepted scientific conclusion.

## Research-memory validation

SHARK OS records Hypotheses, Experiments, Results, Lessons, Branches, and EvidenceExposures as separate structured objects.

The graph is validated repository-wide. Invalid references, contradictory branch state, malformed scientific identity, improper evidence authority, or inconsistent closure fail the research verification gate.

A deterministic Context Pack can reconstruct relevant prior state for a proposed experiment without using semantic inference, network access, market-data access, or an LLM.

This reduces a common research failure mode: repeating an old mistake or presenting already-spent evidence as if it were new because the earlier scientific meaning was distributed across documents and code history.

## Economic validation remains downstream

SHARK distinguishes at least these claims:

1. A historical structure can be reconstructed.
2. The structure survives independent statistical controls.
3. The structure contains predictive information.
4. The predictive information survives realistic execution frictions.
5. A controlled trading system can capture it reliably.

The current public record does not collapse those stages into one backtest metric.

SHARK makes no public claim that the completed research establishes executable alpha. A future economic claim would have to survive the costs, liquidity, latency, hedging, capacity, and implementation constraints relevant to the instrument used.
