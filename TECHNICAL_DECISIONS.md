# SHARK Technical Decisions

## 1. Freeze evidence before interpretation

Acquisition artifacts are immutable. Canonical memory can be reconstructed from sealed evidence, but the evidence itself is not rewritten to accommodate later research conclusions.

## 2. Separate discovery from evaluation

The detector consumes a bounded historical view. Retrospective evaluation can inspect the future only after the candidate has been frozen. This makes historical replay useful without granting the detector impossible foresight.

## 3. Version the universe explicitly

A research universe is an identified object, not a mutable ticker list. Experiments bind to a specific universe version so membership cannot drift silently between discovery and evaluation.

## 4. Prove state before optimizing prediction

The system prioritizes evidence that a measurable market state exists and persists before optimizing a forecast of what happens next. Prediction remains a valid benchmark, but it does not substitute for state evidence.

## 5. Record rejection as a research result

A failed experiment is retained with its frozen specification, inputs, result bundle, and failure reason. The completed magnitude/activity experiment is a concrete example: primitive persistence passed, while the stronger incremental joint-state hypothesis failed its pre-registered null gate and was not promoted.

## 6. Keep statistical evidence separate from execution economics

A measurable effect is not called alpha merely because a statistic is significant. Any later trading claim has to survive the relevant spread, slippage, latency, market-impact, financing, borrow, hedging, liquidity, and execution constraints.

## 7. Keep the canonical engine strongly typed

OCaml provides the main research core, with PostgreSQL as canonical memory. Python can be used where provider or scientific tooling makes it the better boundary language, but notebook state does not become the source of research truth.

## 8. Correct instruments before interpreting results

Several defects in the first frozen experiment were caught before scientific statistics became visible: cluster bootstrap draws were collapsing, RNG identity could collide, corpus-completeness metadata could default incorrectly, and one weighting path could fall back to uniform weights.

Those were not cosmetic fixes. Each could have changed the meaning or reproducibility of the experiment. The accepted run began only after the instrument itself was corrected and re-frozen.

## 9. Optimize runtime without changing the statistic

The first implementation projected roughly 183 hours of sequential runtime. The accepted implementation removed redundant computation, precomputed reusable indices, and introduced worker parallelism with deterministic replicate-level RNG. Runtime fell to about 22 minutes on eight workers while 1/4/8-worker output identity remained regression-tested.

The optimization target was throughput, not a different scientific answer.
