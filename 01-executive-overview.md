# DLA: Controlled Execution Around Stochastic Language Models

## Executive Overview

**Publication draft 1.0 | 20 October 2026**  
**Scope:** DLA runtime 0.7.0 and agent profile 0.2.0  
**Document type:** Project-authored technical overview; not peer reviewed

**Author:** Andreas Bender
**e-Mail:** a.bender@optimize-it.com

## Abstract

The Deterministic LLM Agent (DLA) project investigates how a versioned
execution contract can make selected aspects of an LLM-assisted workflow
structurally reproducible without requiring identical model responses.
The central distinction is between variable content and controlled execution.
Within a supported execution profile, the runtime validates the workflow,
applies defined scheduling and failure rules, and records a structural
execution history that can be checked without invoking models or tools again.
The current evidence is limited to local implementation tests and controlled
demonstrations. It does not establish general agent determinism, answer
correctness, production safety, regulatory compliance, or scientific priority.

## 1. The problem

An LLM-assisted workflow combines several sources of variability: generated
text, external services, tool outcomes, resource limits, and concurrent
execution. Repeating the same user request is therefore not, by itself,
sufficient to reproduce the same execution history.

DLA addresses a narrower engineering question:

> Which execution decisions can remain reproducible when model-generated
> content is allowed to vary within a declared contract?

This is a question about control and observation, not a claim that uncertainty
has been removed from the overall system.

## 2. The approach

DLA separates three responsibilities:

- **Content generation:** A language model can provide variable data.
- **Execution control:** An accepted workflow and its versioned rules govern
  the supported execution decisions.
- **Structural inspection:** A recorded history supports validation,
  comparison, and offline replay of the recorded structure.

In the explicit agent profile, model response text does not select the
operator path. This statement must not be generalized to arbitrary workflows
or to plan generation: a model-generated plan can itself vary and must be
validated before execution.

The reproducibility claim is conditional. Relevant plan and input semantics,
contract versions, policies, and classified execution events must remain
equivalent. For example, a successful provider response and a provider failure
need not produce the same history, even for the same initial request.

## 3. Current implementation and evidence

| Area | Current project position | Important boundary |
|---|---|---|
| Workflow control | Versioned validation and execution of supported workflows | Not unrestricted autonomous planning |
| Agent execution | Defined normal, soft-freeze, and hard-freeze paths in the explicit profile | Not semantic verification of model answers |
| Parallel execution | Defined logical rounds and publication order | Not identical physical timing or completion order |
| Failure handling | Defined reactions to classified events | Different event classes can change the structure |
| Replay and comparison | Offline checking of recorded structural histories | Not a fresh execution or proof of external effects |
| Rule changes | Explicitly gated, versioned activation with evaluation checks | Not autonomous or guaranteed improvement |

The project reports a local test run on 20 October 2026 with **185 tests
passed, zero failed, and zero skipped**. Separate project reports dated
19 October 2026 record **44 parallel-runtime tests** and **17 agent-integration
tests**. These are scoped evidence sets, not independent replications or
additional totals to add to the full suite.

The evidence paper explains their provenance and limitations. The public
papers do not distribute the implementation or underlying private test assets.

## 4. Potential value

The approach may help teams investigate workflow regressions, compare
structural execution histories, and separate content changes from changes in
control behavior. These are potential engineering uses, not measured claims
of lower cost, higher throughput, better answers, or reduced operational risk.

In a regulated setting, structural records could be one input to a broader
assurance process. They do not establish legal admissibility, certification,
conformity with a named regulation, or suitability for a safety-critical task.

## 5. What DLA does not establish

The current material does not establish:

- identical tokens, model answers, or arbitrary tool outputs;
- correctness, fairness, completeness, or usefulness of generated content;
- deterministic external side effects or transactional rollback;
- general isolation of untrusted code or comprehensive security;
- production reliability across platforms and deployment environments;
- superiority over other systems, novelty, or a first-of-its-kind result.

A structural comparison can establish equality only within its declared
comparison scope. It is not evidence that two runs used identical private
content, and a hash is not an authenticity guarantee.

## 6. Development direction

Future evaluation should broaden deployment coverage, examine realistic
provider and tool failures, and enable independent scrutiny under appropriate
access arrangements. Domain-specific assurance and performance evaluation
would require separate protocols and acceptance criteria.

These are evaluation priorities, not completed capabilities or release
commitments.

## 7. Public disclosure boundary

This paper describes externally explainable behavior and evidence limits.
It contains no runtime source, executable examples, private traces, prompts,
schemas, implementation recipes, or credentials. Publication does not grant
a license to the non-public implementation.

This disclosure boundary is not a legal opinion on patentability, ownership,
or freedom to operate; those questions require separate rights review.

## Companion papers

- [Architecture and Conditional Structural Determinism](./02-architecture-and-determinism.md)
- [Evidence, Demonstration, and Limitations](./03-evidence-and-limitations.md)
