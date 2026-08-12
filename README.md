# SHARK

## Scientific quantitative research infrastructure

SHARK is a short-horizon quantitative research laboratory for liquid U.S. equities. Its purpose is not to defend a preferred model or produce a favorable backtest. It is to discover measurable market structure, attempt to falsify it, preserve the scientific record, and advance only the effects that survive increasingly difficult tests.

The implementation and active research programme remain private. This case study presents the architecture, operating rules, selected completed research, and current scientific boundaries.

## My role

I own the research thesis, experimental rules, information boundaries, architecture constraints, acceptance criteria, and research decisions for SHARK. I review implementation and evidence against those rules, including whether a result is promoted, narrowed, rejected, or closed.

AI-assisted engineering tools are part of the build workflow. Scientific authority remains with frozen specifications, immutable evidence, executable validation, and the recorded scientist decision.

**Period:** active quantitative research programme, 2026.  
**Current status:** the local research laboratory is operational, the 200-equity intraday corpus is frozen in canonical PostgreSQL memory, the OCaml research engine is executable, and the scientific lifecycle is machine-verified. SHARK is research infrastructure, not a production trading system.

## Research objective

The long-run objective is to build a research process capable of repeatedly discovering, falsifying, validating, monitoring, and retiring independent market effects.

Models are disposable. Individual hypotheses are disposable. A valid effect may also be temporary. The durable asset is the process that can distinguish an interesting observation from a reproducible state, a predictive effect, and eventually an economically executable source of alpha.

```text
observe structure
-> formulate a falsifiable claim
-> attack the method
-> freeze the experiment
-> test independent evidence
-> accept, narrow, or reject
-> test prediction
-> test economics
-> monitor decay
-> preserve what was learned
-> repeat
```

A high rejection rate is compatible with a productive research programme. The objective is to learn what is false cheaply enough that research effort can move to better questions.

## Current laboratory

The canonical intraday environment contains:

- **200 liquid U.S. equities** in a versioned research universe
- approximately **720 calendar days** of history
- native **5-minute regular-session bars**
- **7,659,672 frozen baseline bars**
- Alpaca SIP historical data as acquisition evidence
- PostgreSQL as canonical research memory
- immutable source evidence with content hashes and provenance

The research stack is primarily OCaml 5.2+ with PostgreSQL. Python is used selectively where provider or scientific tooling makes it the appropriate boundary language.

The repository also contains a daily Pattern Engine with directional sequence, turning-angle, and triangle/path-ratio detector families. The daily detector system and the 5-minute intraday research laboratory are separate scientific surfaces and do not silently inherit authority from one another.

## System shape

```mermaid
flowchart LR
    A[Immutable acquisition evidence] --> B[Canonical PostgreSQL memory]
    B --> C[Point-in-time bounded research view]
    C --> D[Mathematical representation or experiment]
    D --> E[Methodological red team]
    E --> F[Frozen specification]
    F --> G[Independent evidence]
    G --> H[Scientist decision]
    H --> I[Research memory]
    I --> J[Next hypothesis]
```

At research time `T`, the experiment receives only information available at or before `T`. Retrospective evaluation may inspect later observations after the candidate or state has been fixed. Future observations cannot alter what the original experiment was allowed to know.

## Scientific memory

A research programme can become unreliable even when every individual file is preserved. The difficult problem is remembering which result was provisional, which evidence has already been exposed, which interpretation was later corrected, what a branch actually ruled out, and what remains genuinely untested.

SHARK therefore maintains a deterministic, Git-native scientific memory called **SHARK OS**. It records six distinct object classes:

```text
Hypothesis       the question being asked
Experiment       what ran and under what authority
Result           machine verdict and scientist acceptance
Lesson           what later research should retain
Branch           what a research family established or exhausted
EvidenceExposure which evidence has already been spent
```

Machine output and scientific conclusion are deliberately separate. Evidence that has been inspected cannot later be presented as untouched confirmation. A closed branch records both what was ruled out and what remains untested.

Before new work advances, SHARK can render a deterministic Context Pack from this graph. The pack reconstructs relevant lineage, prior results, lessons, evidence exposure, closure state, and unresolved questions without semantic search, embeddings, an LLM, market-data access, or network access.

The lifecycle is executable. Repository-wide verification fails closed when scientific state is internally inconsistent, when evidence authority is invalid, or when frozen experiment identity has been altered.

## Selected research record

### Magnitude and activity structure

An early frozen experiment tested whether clock-normalized return magnitude, volume, and trade count contained persistent within-session structure, and whether a joint magnitude/activity state added information beyond the marginals.

The machine initially reported `PASS_PRIMITIVE_PERSISTENCE_ONLY`. A later forensic reanalysis of the already-exposed evidence corrected the lag-specific inference. The accepted scientific interpretation is narrower:

- log volume and log trade count show robust within-session persistence over the tested 20 to 60 minute region
- absolute-return magnitude persistence does **not** survive the corrected inference standard
- the isolated incremental joint-state finding appeared only on confirmation evidence and did not reproduce on final evidence
- the branch is closed with **no stable incremental state established**

The correction is part of the result, not an exception to it. The original machine output remains preserved alongside the later scientist disposition.

### Killing an invalid instrument before market evidence

A subsequent time-asymmetry research candidate was subjected to methodological red-team testing before it was permitted to inspect market data.

Its nominal 5% procedure rejected a valid synthetic null in **1,815 of 2,000 replicates**. The statistical instrument was therefore killed before market evidence was spent. The underlying market hypothesis remains untested.

That failure became a reusable methodological constraint: a future instrument must demonstrate valid-null calibration under hostile synthetic stress before receiving market-data authority.

This is the intended research behavior. A plausible idea does not earn protection from a failed test.

## Research stance

SHARK is explicitly cumulative. Established quantitative finance, statistics, mathematics, econometrics, and mathematical physics are treated as prior art, baselines, numerical references, and adversaries.

Potential tools include geometry, stochastic processes, nonlinear dynamics, rough paths, information theory, topology, optimal transport, spectral methods, statistical mechanics, control theory, optimization, and machine learning. No framework receives authority from elegance or novelty alone.

The useful question is not whether a method is new to SHARK. It is whether a causally valid construction explains residual structure that survives simpler models, hostile nulls, independent evidence, and economic constraints.

Public literature narrows the search space. Where strong prior work already explains a phenomenon, SHARK should reproduce or benchmark it rather than rename it. Novelty, if it emerges, must come from a reproducible empirical effect, method, or combination that remains unexplained after comparison with the existing literature.

## Research frontier

The current programme is moving beyond aggregate bar structure toward richer questions about market state, liquidity response, path dependence, cross-sectional interaction, and conditional future distributions.

The working hypothesis is not that complexity creates alpha. It is that difficult, state-dependent interactions across market information may contain structure that simpler representations leave unresolved.

Active hypotheses, exact statistics, thresholds, data partitions, and prospective trading mechanisms remain private until they are scientifically closed or can be disclosed without compromising ongoing work.

## Validation model

SHARK's local gate contains more than one thousand automated tests across mathematical, storage, research-memory, database, and scientific-lifecycle surfaces, plus dedicated Pattern Engine proofs.

The important property is not the count. The gate tests failure modes that can change scientific meaning: no-lookahead boundaries, immutable evidence, canonical database provenance, exact experiment identity, deterministic randomization, result reconstruction, database failure and recovery, evidence exposure, Context Pack determinism, scientific freeze integrity, and fail-closed closure rules.

## Economic boundary

Statistical structure is not called alpha merely because a statistic is significant.

A predictive effect must eventually survive the frictions relevant to its implementation, including spread, slippage, latency, market impact, financing, borrow, option liquidity, hedging, carry, capacity, and execution delay.

The scientific sequence is deliberately staged:

```text
historical structure
-> reproducible state
-> untouched predictive increment
-> economic discrepancy
-> realistic friction
-> controlled execution
-> live evidence
```

SHARK currently makes no public claim of executable alpha, profitability, or production trading authority.

The claim is narrower and more important at this stage: the laboratory is built to make unsupported conclusions difficult to preserve and useful failures difficult to forget.

[Architecture](ARCHITECTURE.md) · [Technical decisions](TECHNICAL_DECISIONS.md) · [Validation](VALIDATION.md) · [Back to profile](https://github.com/Andy11-cpu)
