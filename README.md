# DLA — Deterministic LLM Agent

Public papers and a screener for the DLA project.
This repository contains presentation material, not the runtime source code.

DLA investigates conditional structural reproducibility around stochastic
language models: controlled workflow execution, defined failure reactions,
and offline inspection of recorded execution histories. It does not claim
identical model answers or unconditional determinism from the same user request.

## Watch the screener

**[Watch or download the DLA screener (MP4)](./dla-screener.mp4)**

If GitHub does not display a video player, use **View raw** or download the
file to watch it locally.

The screener presents a synthetic, offline walkthrough of agent execution,
normal and freeze paths, an injected provider-error case, replay, and structural
comparisons. It is not a live-provider demonstration, a physical-parallelism
benchmark, or independent certification.

## Papers

1. [Executive Overview](./01-executive-overview.md) — purpose, potential value,
   current scope, and explicit non-claims.
2. [Architecture & Conditional Structural Determinism](./02-architecture-and-determinism.md)
   — the conditional contract and the distinctions between content and control,
   rerun and replay, and logical and physical order.
3. [Evidence & Limitations](./03-evidence-and-limitations.md) — project test
   evidence, provenance, demonstration boundaries, and open evaluation work.

The papers are project-authored publication drafts dated 20 October 2026,
covering runtime 0.7.0 and agent profile 0.2.0. They are not peer-reviewed
publications, security assessments, or regulatory conformity statements.

## Scope and access

Runtime sources, executable scripts, private test assets, and internal traces
are not distributed here. The public materials alone do not allow readers
to reproduce the implementation tests. Publication does not grant a license
to the non-public implementation.
