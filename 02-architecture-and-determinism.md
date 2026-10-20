# DLA: Architecture and Conditional Structural Determinism

**Publication draft 1.0 | 20 October 2026**  
**Scope:** DLA runtime 0.7.0 and agent profile 0.2.0  
**Document type:** Project-authored conceptual paper; not a formal verification report

## Abstract

This paper defines the scope of structural determinism used in the DLA
project. It distinguishes accepted workflow execution from model-generated
content, independent reruns from offline replay, and logical scheduling from
physical concurrency. The proposed contract concerns equality of a defined
structural projection under equivalent control-relevant conditions. It does
not imply deterministic language generation, identical external effects, or
unconditional reproducibility from the same user request. The presentation is
conceptual and intentionally omits implementation mechanisms.

## 1. Architectural boundary

DLA treats language-model output as data rather than unrestricted authority
over execution. In the explicit agent profile, the workflow determines the
operator structure; model response text does not select operators or paths.
Provider failures and other classified events can nevertheless change the
recorded execution.

This boundary has two qualifications:

1. The accepted plan must be distinguished from its creation. If a model
   proposes a plan, identical requests need not produce identical plans.
2. The explicit agent profile must be distinguished from other supported
   workflow profiles. A content-independent path claim must not be extended
   to profiles with control-relevant data conditions.

Execution remains subject to versioned validation, policy, and supported
environment assumptions. No capability to execute arbitrary generated code
is implied.

## 2. Definitions

**Execution contract:** The relevant versioned workflow semantics, operator
contracts, scheduling rules, policy bindings, and event classifications.

**Structural projection:** The declared, version-specific representation used
to compare control-relevant aspects of recorded execution. Depending on the
profile, these include operator occurrences, ordering, logical rounds,
classified outcomes, freeze reactions, and termination.

**Independent rerun:** A new execution that can invoke tools or providers and
can encounter different external events.

**Offline replay:** Validation and inspection of a recorded execution
structure without repeating its model or tool effects.

**Freeze reaction:** A profile-defined control response. A planned freeze
classification is distinct from a reaction that actually executed.

## 3. Conditional equality statement

Let R1 and R2 denote independent runs under the same relevant contract C.
Let P_C denote the structural projection for that contract. The intended
contract can be expressed as:

> If R1 and R2 have equivalent control-relevant plans, inputs, policies, and
> classified event histories under C, then P_C(R1) = P_C(R2).

This is a scoped contract statement, not a mathematical proof for arbitrary
programs or environments.

Equivalence here is stronger than having the same natural-language request.
It requires matching the conditions that can influence execution under the
chosen profile. Content may vary only where the contract treats that content
as irrelevant to control.

For example, two successful synthetic responses with different text may
preserve the agent structure. A successful response and a timeout need not.
Even identical response text does not compensate for a changed plan, policy,
or failure classification.

## 4. Three distinct reproducibility questions

### 4.1 Path reproducibility

Do independent executions preserve the projected operator structure under
equivalent control-relevant conditions?

This excludes equality of generated text and arbitrary result values.
Tests with varied synthetic text support only the content-variation cases
actually examined.

### 4.2 Reaction reproducibility

Does the same classified event, at the same relevant execution state under
the same contract, produce the same defined reaction?

The qualification matters: similar symptoms can have different classifications,
and an environmental change can alter which event is observed. Resource limits
do not make the occurrence of a timeout or memory failure deterministic.

### 4.3 Replay validity

Does a recorded history satisfy the applicable structural rules, and can its
projected structure be inspected without repeating effects?

Replay is not an independent rerun. It does not recover omitted content,
verify the historical truth of every recorded event, or demonstrate that an
external action actually occurred.

## 5. Logical parallelism and physical execution

The parallel profile defines logical rounds and an ordered publication of
results. Physical processes and asynchronous requests may finish in a
different order without changing the projected logical history, provided
their control-relevant outcomes remain equivalent.

Logical order is therefore distinct from:

- operating-system scheduling and process start times;
- wall-clock durations and provider latency;
- physical completion order;
- throughput, fairness, and performance guarantees.

On a classified operator failure, the supported round contract lets already
selected siblings finish within their limits and does not start a subsequent
round. This is neither immediate cancellation of every active action nor
transactional rollback. A profile-defined hard freeze of one agent is not
the same event as a runtime-wide operator failure.

## 6. Structural records and trust

The comparison scope excludes content and physical measurements that are not
part of the declared structural projection. Consequently, equal structural
histories can coexist with different answers, different timings, or different
private inputs outside that comparison scope.

A comparison hash is a compact equality aid for the defined projection. It
is not a digital signature, provenance attestation, proof of full-content
identity, or proof that a record is complete and authentic. Structural
metadata can itself reveal sensitive workflow information.

## 7. Assurance boundaries

Validation constrains accepted workflow structure and supported contracts;
it does not establish semantic truth. Defined error handling does not
establish general safety. Versioned rule activation does not establish an
improvement unless a relevant evaluation demonstrates one.

Applications still need domain-specific controls, data governance, access
management, operational monitoring, and appropriate human responsibility.
These requirements are not presented as implemented or certified features
of the DLA runtime.

## 8. Status and research boundary

Local tests provide bounded evidence for the implementation described in the
companion evidence paper. No general proof, independent certification,
comparative benchmark, or systematic literature review is supplied here.
Accordingly, this paper makes no priority or superiority claim.

Broader platform coverage, independent evaluation, and formal analysis remain
future evaluation work, not consequences of the present contract statement.

## Disclosure and companion papers

Only conceptual boundaries are disclosed. Runtime sources, detailed algorithms,
schemas, private inputs, and internal trace formats are not included. This
paper is not a legal assessment of intellectual-property protection.

- [Executive Overview](./01-executive-overview.md)
- [Evidence, Demonstration, and Limitations](./03-evidence-and-limitations.md)
