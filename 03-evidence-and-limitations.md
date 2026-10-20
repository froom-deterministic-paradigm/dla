# DLA: Evidence, Demonstration, and Limitations

**Publication draft 1.0 | 20 October 2026**  
**Scope:** DLA runtime 0.7.0 and agent profile 0.2.0  
**Document type:** Project-authored evidence summary; not an independent audit

## Abstract

This paper summarizes the evidence available for selected DLA execution
contracts. It distinguishes a newly observed local full-suite result,
previously generated project test reports, and a synthetic screener
demonstration. The evidence supports bounded implementation claims in the
tested conditions. It does not provide public source-based reproducibility,
independent replication, a proof of arbitrary agent determinism, or an
assessment of real-world model quality, security, or regulatory compliance.

## 1. Evidence provenance

The evidence available during preparation consists of local project records:

| Evidence item | Observation or reported result | Qualification |
|---|---|---|
| Full implementation suite, 20 October 2026 | 185 passed; 0 failed; 0 skipped; 0 cancelled | Directly observed local run; not a separately archived, source-bound public release |
| Parallel-runtime report, 19 October 2026 | 44 passed; 0 failed; 0 skipped | Previously generated project report with source digests |
| Agent-integration report, 19 October 2026 | 17 passed; 0 failed; 0 skipped | Previously generated project report with source digests |
| Screener preparation and viewer documentation | Describes synthetic runs, replay, comparisons, and recording | A demonstration description, not an independent experiment |

The two dated reports identify Windows x64 and Node.js 20.20.2 as their
execution environment. The new full-suite observation is a separate local
result; it is not asserted to refresh those reports or their source bindings.

The 44 and 17 tests are scoped subsets represented within the broader test
coverage. They must not be added to 185 to suggest a larger independent
sample. Test counts are not statistical confidence levels or failure-rate
estimates.

The report statements that their sources remained unchanged concern their
own recorded execution windows. They do not certify later changes. Their
source digests identify recorded source versions but do not authenticate
the reports or make unpublished sources publicly inspectable.

## 2. Claims and supporting observations

| Narrow claim | Supporting test coverage | What remains outside the claim |
|---|---|---|
| Supported plans are validated before effects | Rejection of malformed plans, invalid dependencies, unsupported configurations, and policy violations | Correctness of arbitrary accepted business logic |
| Logical scheduling is stable in tested cases | Expected round selections, ordering variations, capacity and priority cases | Arbitrary workloads, dynamic scheduling, or performance |
| Logical publication need not follow physical completion | Controlled reversed completion tests and separate local process-overlap probes | Identical timings or deterministic external side effects |
| Failure barriers follow defined rules | Selected sibling completion, no later round, stable primary-error selection, cancellation classification | Rollback or immediate termination of all active work |
| Agent paths tolerate tested content variation | Independent synthetic reruns across defined normal and freeze cases | All model outputs or all possible workflows |
| Replay avoids renewed effects | Offline replay checks with provider and process-start paths blocked in tests | Authentication of the original execution |
| Structural records respect tested content boundaries | Checks excluding selected private values and diagnostics from structural comparison | Complete anonymity or absence of metadata leakage |

The local process-overlap evidence uses trusted test workers in a controlled
environment. Agent oracle-overlap tests use injected asynchronous responses.
These are different experiments and must not be described as live-model or
unrestricted-tool evidence.

## 3. Screener interpretation

The documented screener is an English-language, synthetic walkthrough.
Its preparation creates separate examples for:

- normal, soft-freeze, and hard-freeze agent behavior;
- an independent rerun with different synthetic response text;
- an injected provider-error classification.

The viewer presents recorded structures, offline replay, and equal or
different comparisons. These observations illustrate the distinction between
content variability and structural comparison.

The documented demonstration does not call a live model provider and does
not measure physical tool-process parallelism. It is not a benchmark, a
production workload, or evidence of answer quality. Recording a demonstration
does not make it an independent verification.

The existing screener video was not frame-reviewed as part of preparing these
papers. Its final content, visible metadata, and correspondence to the stated
scope require review before publication. This paper does not certify that
the existing video was produced by a particular recorded test session.

## 4. Reproducibility and access

The implementation, test sources, detailed reports, and raw execution records
are not distributed with these public papers. Readers therefore cannot
reproduce the reported test runs from the public materials alone.

The results are project-reported except for the directly observed local
full-suite run described above. Neither category constitutes independent
replication. No unavailable internal document is presented as an accessible
public reference.

An independent evaluation would require an agreed implementation snapshot,
access to appropriate test assets, a specified environment, predetermined
acceptance criteria, and a publication policy for results. This paper does
not imply that such access is currently offered or that the evaluation has
already occurred.

## 5. Threats to validity

### Internal validity

Tests can share assumptions with the implementation, and injected responses
can omit failure modes of real services. A passing suite cannot rule out
defects outside its assertions. This publication review did not independently
re-audit the test implementation.

### External validity

Local Windows-based evidence and bounded fixtures do not establish behavior
on other platforms, under sustained load, against hostile tools, or in
uncontrolled distributed environments.

### Construct validity

Structural equality measures the declared control projection. It must not
be substituted for answer correctness, identical data, truthful provenance,
or identical external consequences.

### Reporting limitations

The test observations do not provide population failure rates, performance
distributions, comparative baselines, or an independently published immutable
implementation release. Historic documentation of additional checks is not
treated as a newly reproduced result.

## 6. Explicit non-claims

The evidence does not establish:

- general determinism for arbitrary LLM agents;
- factual correctness, fairness, or usefulness of generated answers;
- safe execution of arbitrary untrusted code;
- production readiness, comprehensive security, or crash recovery;
- guaranteed optimization gains or autonomous self-improvement;
- regulatory conformity, certification, legal admissibility, or suitability
  for medical, legal, or safety-critical decisions;
- novelty, priority, or superiority relative to other systems.

No paid live-provider evaluation, independent security assessment, or
cross-platform certification is claimed by this evidence summary.

## 7. Future evaluation

Useful next steps include independently specified replication, broader
environment coverage, realistic provider-failure studies, and separate
evaluation of semantic task quality and operational risk. Any performance
comparison should define workloads, baselines, and measurement conditions.

These are proposed evaluation activities, not completed results or scheduled
release commitments.

## Disclosure and companion papers

This summary deliberately excludes source code, executable instructions,
private traces, detailed schemas, source inventories, credentials, and
internal filesystem locations. It does not certify intellectual-property
clearance or confer rights to the implementation.

- [Executive Overview](./01-executive-overview.md)
- [Architecture and Conditional Structural Determinism](./02-architecture-and-determinism.md)
