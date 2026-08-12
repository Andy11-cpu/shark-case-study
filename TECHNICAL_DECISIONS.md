# SHARK Technical Decisions

## 1. Freeze evidence before interpretation

Acquisition evidence is immutable. Canonical memory can be reconstructed from sealed evidence, but the evidence itself is not rewritten to accommodate a later scientific conclusion.

A correction changes the interpretation record, not the historical bytes.

## 2. Separate discovery from evaluation

Discovery consumes a bounded historical view. Evaluation may inspect later observations only after the candidate or state has been fixed.

This makes retrospective research useful without granting the original calculation impossible foresight.

## 3. Version the research universe

A universe is an identified object, not a mutable ticker list. Experiments bind to a specific version so membership cannot drift silently between discovery and evaluation.

The version is also allowed to carry limitations. A current point-in-time universe applied to older bars is not relabeled as survivorship-free historical membership.

## 4. Prove state before optimizing prediction

The preferred sequence is:

```text
observable
-> causal state reconstruction
-> state existence
-> state persistence
-> simpler controls
-> hostile nulls
-> prediction
```

Prediction is a valid experiment, but it does not substitute for evidence that the proposed state exists.

## 5. Treat prior research as infrastructure

SHARK builds on established quantitative finance, statistics, mathematics, econometrics, and mathematical physics.

Published methods are used as baselines, numerical references, prior art, and adversaries. Reimplementing a known idea does not create novelty. A new claim must survive comparison with the strongest relevant existing explanation.

Mathematical methods are construction material, not doctrine. Geometry, stochastic processes, rough paths, information theory, topology, optimal transport, spectral methods, statistical mechanics, control theory, optimization, and machine learning are admissible when their assumptions are explicit and their use is falsifiable.

## 6. Record rejection as a research result

A failed experiment is retained with its specification, inputs, result, and scientist disposition.

The magnitude/activity line illustrates why. An initial machine verdict survived execution, but a later forensic analysis narrowed the accepted scientific interpretation and closed the branch without a stable incremental state.

The original result remains part of the record. The later conclusion controls current research authority.

## 7. Red-team the instrument before spending scarce evidence

A plausible hypothesis can still be tested by an invalid instrument.

One later research candidate was stopped before market exposure because its nominal 5% procedure rejected a synthetic valid null in 1,815 of 2,000 replicates. The market claim was not rescued. The instrument was killed, the hypothesis remained untested, and the calibration failure became a binding lesson for later work.

This is now a general rule: where feasible, statistical machinery must demonstrate valid-null behavior under hostile synthetic conditions before untouched market evidence is spent.

## 8. Separate machine verdict from scientist conclusion

A machine result is not automatically the scientific conclusion.

SHARK OS records the machine verdict, scientist acceptance, scientific conclusion, branch disposition, and evidence exposure as distinct facts. A later correction can narrow a claim without rewriting what the original instrument actually reported.

## 9. Evidence spent once remains spent

Reanalysis can improve interpretation. It cannot restore confirmatory authority to evidence that has already been inspected.

Forensic reuse is recorded as reuse. Untouched evidence is treated as a different scientific resource.

## 10. Distinguish ruled out from untested

A failed state-persistence experiment does not imply that prediction was tested. A failed aggregate-bar experiment does not imply that event-level microstructure was tested.

Closed research branches therefore record both what evidence ruled out and what remains genuinely unknown.

## 11. Keep statistical evidence separate from execution economics

A significant statistic is not trading alpha.

Any later trading claim must survive the relevant spread, slippage, latency, market impact, financing, borrow, hedging, option liquidity, carry, capacity, and execution constraints.

The target is executable net alpha, not statistical significance in isolation.

## 12. Keep canonical authority strongly typed

The research core is primarily OCaml with PostgreSQL as canonical market-data memory.

The language choice is practical. Types encode boundaries, deterministic research state is easier to audit, and experiments remain separate from mutable notebook state. Python is available where provider or scientific ecosystems make it the appropriate specialist boundary.

## 13. Separate scientific surfaces

The daily Pattern Engine and the 5-minute intraday research laboratory are distinct systems with different data contracts and scientific authority.

A representation or detector does not become valid at another resolution merely because the code can be called there.

## 14. Optimize runtime without changing the scientific question

Research throughput matters because slow falsification wastes evidence and attention.

The first frozen magnitude/activity implementation projected roughly 183 hours of sequential runtime. Removing redundant computation and introducing deterministic worker-level parallelism reduced the accepted execution to about 22 minutes without changing the frozen statistic.

The optimization target was time to scientific answer, not a different answer.

## 15. Make scientific state executable

SHARK OS is deliberately simple: Git-native structured records, strict decoding, deterministic retrieval, and fail-closed verification.

The scientific lifecycle is therefore not only documentation. Repository verification can reject inconsistent evidence authority, invalid lifecycle state, or mutation of frozen experiment identity.

The scientist remains the decision authority. The system's role is to make the decision record difficult to corrupt, forget, or reinterpret accidentally.
