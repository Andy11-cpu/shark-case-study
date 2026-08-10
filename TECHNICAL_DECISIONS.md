# SHARK Technical Decisions

## 1. Freeze evidence before interpretation

Acquisition artifacts are immutable. Canonical memory can be reconstructed from sealed evidence, but the evidence itself is not rewritten to accommodate later research conclusions.

## 2. Keep discovery and evaluation separate

The detector consumes a bounded historical view. Retrospective evaluation can inspect the future only after the candidate has been frozen. This makes historical replay useful without granting the detector impossible foresight.

## 3. Version the universe explicitly

A research universe is an identified object, not a mutable ticker list. Experiments bind to a specific universe version so membership cannot drift silently between discovery and evaluation.

## 4. Prefer state identification before prediction

The system prioritizes proving that a measurable market state exists and persists before optimizing a forecast of what happens next. Prediction without state evidence remains acceptable as a benchmark, but not as the preferred research sequence.

## 5. Treat failed experiments as useful output

Research logs preserve rejected hypotheses, tested specifications, and failure reasons. The objective is to avoid repeatedly rediscovering the same dead end and to make specification changes explicit new experiments.

## 6. Distinguish statistical evidence from executable economics

A measurable effect is not called alpha merely because a statistic is significant. The research process later has to consider trading frictions, capacity, latency, hedging, and the economic half-life of the effect.

## 7. Keep the canonical engine strongly typed

OCaml provides the main research core, with PostgreSQL as canonical memory. Python or R can be used where their ecosystems are materially advantageous, but notebook state does not become the source of research truth.
