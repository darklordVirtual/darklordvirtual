# Stian Skogbrott

**Agent execution authority · policy-as-code · conformance · reliable autonomous systems**

I work on the boundary between **AI reasoning and real-world authority**.

> **The interesting question is not only what an agent can do. It is what the system can prove the agent was allowed to cause.**

My current work is centered on a simple architectural position:

```text
reasoning authority != execution authority
```

A model may propose an action. The authority to approve, bind, dispatch and verify that action should come from controls outside the model's own reasoning loop.

That leads to a research program spanning three layers:

```text
                         ┌──────────────────────────────┐
                         │  REMORA Research             │
                         │  mechanisms + experiments   │
                         └──────────────┬───────────────┘
                                        │
                                        ▼
                         ┌──────────────────────────────┐
                         │  Agent Authority Conformance │
                         │  common evidence vocabulary │
                         └──────────────┬───────────────┘
                                        │
                                        ▼
                         ┌──────────────────────────────┐
                         │  Assured Agent Execution     │
                         │  deployable control patterns│
                         └──────────────────────────────┘
```

The common problem is **action-time authority**: who authorized an action, what exactly was authorized, whether the protected effect can bypass the governed path, whether the authorization remained valid at dispatch, and whether the external effect can be verified afterwards.

## Current research

### [Agent Authority Conformance](https://github.com/darklordVirtual/agent-authority-conformance)

A standalone, vendor-neutral evidence model for comparing authority and execution controls in agentic systems without collapsing them into a vague security score.

It separates seven properties:

| | Property | Question |
|---|---|---|
| **A** | Receipt Integrity | Is the authorization artifact authentic, intact and valid? |
| **B** | Authority Provenance | Who or what actually had authority to approve the action? |
| **C** | Exact-Call Integrity | Is approval bound to the exact call that is executed? |
| **D** | Semantic Authority | Was the action authorized in its real operational meaning? |
| **E** | Execution-Boundary Integrity | Can the protected effect bypass the governed path? |
| **F** | TOCTOU Resistance | Can approved conditions change before execution? |
| **G** | Effect Verification | Did the intended external effect actually occur? |

The rules are deliberately conservative:

```text
PASS requires resolved evidence
UNTESTED is not failure
OUT OF SCOPE is not a deficiency
properties are never aggregated into one score
```

The repository contains a normative v0.1 specification, a machine-readable assessment schema, CI validation and bounded cross-system assessments.

I am particularly interested in whether these seven properties survive contact with systems built on assumptions very different from REMORA. If they do not, the vocabulary should change.

### [REMORA Research](https://github.com/darklordVirtual/REMORA-research)

REMORA explores policy-gated execution assurance for operational AI agents. It sits between an agent proposal and the protected tool path.

```text
proposal
   ↓
authoritative context
   ↓
policy decision
   ↓
review / short-lived grant
   ↓
fresh pre-execution checks
   ↓
exact-call binding
   ↓
controlled dispatch
   ↓
postcondition / effect evidence
```

The project is intentionally evidence-heavy. Claims are tied to committed artifacts, explicit scope and permanent negative results rather than being inferred from architecture diagrams or demos.

**Useful entry points:**

- [Claim register](https://github.com/darklordVirtual/REMORA-research/blob/master/docs/assurance/claim_register_v1.yaml)
- [Negative results](https://github.com/darklordVirtual/REMORA-research/blob/master/NEGATIVE_RESULTS.md)
- [Evidence and claims](https://github.com/darklordVirtual/REMORA-research/blob/master/docs/02-evidence-and-claims.md)
- [Architecture](https://github.com/darklordVirtual/REMORA-research/blob/master/ARCHITECTURE.md)

REMORA is research/shadow-mode software. It does **not** claim production certification or universal agent safety.

### [Assured Agent Execution](https://github.com/darklordVirtual/assured-agent-execution)

Product-oriented work on turning the research into deployable control-plane patterns: exact-payload approval binding, separate proposer/approver/executor identities, controlled dispatch, auditable execution state and postcondition verification.

### [pilotfish](https://github.com/darklordVirtual/pilotfish)

The same question outside AI: which network link may a class of traffic use, and
who can prove it was allowed to.

Link selection today is a metric optimisation. That is the right answer only
when nothing but latency constrains the choice, and it is the wrong one whenever
something else does: a metered LTE plan with a cap, a contractual SLA, traffic
that may not cross an unencrypted or foreign path, a free-space-optics hop whose
weather evidence has gone stale. Those constraints usually end up as static
failover lists nobody can audit.

So policy governs which links are *permitted* for a traffic class, with a reason
recorded for every exclusion, and a cheap scheduler chooses freely inside that
set. Evidence carries a timestamp and a source, so a permitted set contracts on
its own as measurements age, and a site that loses its authority falls to a
signed floor policy rather than to whatever it last liked.

The simulator compares it against the three selectors people actually run, and
[NEGATIVE_RESULTS.md](https://github.com/darklordVirtual/pilotfish/blob/master/NEGATIVE_RESULTS.md)
records where governance bought nothing: on plain failover it ties greedy
selection, and it damps flapping no better. Where it pays, it pays by refusing
to carry traffic, and the cost is published in the same table as the benefit.

### [vericlaim](https://github.com/darklordVirtual/vericlaim)

An experiment in treating technical claims like build artifacts: documentation, benchmark results and reusable code are mechanically bound to the evidence that supports them, so unsupported drift can fail CI instead of silently becoming project truth.

## Where the work has been tested from outside

The rule above is easy to write and only means something when someone else
applies it to you. Two recent cases, stated at the level the evidence supports.

**An external technical review of REMORA**, against a locked commit, produced
eleven findings: a published component ablation whose numbers were absent from
the artifact it cited, an execution path whose token bound less than its
documentation claimed, a false-accept rate measured against the wrong
denominator, and eight more. Ten are closed, each with a negative conformance
test that fails on the original defect. The eleventh is independent replication,
which cannot be closed from inside the repository, and it is recorded as open
rather than argued away. The withdrawn claim and what replaced it are in
[NEGATIVE_RESULTS.md §57](https://github.com/darklordVirtual/REMORA-research/blob/master/NEGATIVE_RESULTS.md).

**A cross-implementation run against the
[APS conformance suite](https://github.com/Agent-Authority-Conformance/aps-conformance-suite).**
REMORA's canonical JSON was compared byte for byte against RFC 8785 vectors from
another project. The run found a Windows harness defect in that suite and a
coarse boundary in REMORA's own implementation, and the resulting interop record
is [open for review there](https://github.com/Agent-Authority-Conformance/aps-conformance-suite/pull/41).

The most useful part was being wrong in public. That record originally claimed
REMORA prevents two argument sets from sharing canonical bytes. The corpus
maintainer showed in review that distinct float literals collapse during JSON
parsing before the check runs, so the guarantee holds for integers and nothing
else. The claim is now narrowed in the code, the record and the design document,
with a test pinning the limit.

An author-run interop record is not certification, not endorsement, and not
independent validation. It is one implementation's observed behaviour against
another project's vectors, with the divergences kept rather than smoothed.

## What I am trying to falsify

I prefer research questions that can embarrass the architecture.

Some of the questions I am actively interested in:

- **Authority provenance:** can a system prove that the principal approving an action actually held the required authority, including delegation and attenuation?
- **Credential topology:** how do we demonstrate that a protected side effect is unreachable outside the policy enforcement path rather than merely assuming it?
- **Exact-call integrity:** what canonical representation is sufficient to bind authorization to complex, nested and versioned tool arguments without ambiguity?
- **Distributed TOCTOU:** how should single-use grants, revocation and approval freshness behave across processes, hosts and retries?
- **Semantic authority:** where should authoritative task meaning come from when the model itself cannot be allowed to manufacture the authority for its own proposal?
- **Effect verification:** what constitutes authoritative evidence that an external side effect occurred, especially when the downstream system offers weak read-back semantics?
- **Conformance validity:** can independent assessors apply the same authority model and reach comparable conclusions without sharing implementation assumptions?

These are more interesting to me than another benchmark claiming that an agent completed a task successfully.

## Evidence over posture

My working rule is simple:

1. State the property precisely.
2. Define what evidence would support it.
3. Design a test that can disprove it.
4. Bind the result to an immutable artifact or revision.
5. Keep scope and caveats next to the result.
6. Publish negative results and failed hypotheses.
7. Change the architecture when the evidence says it should change.

A useful result can therefore be `PASS`, `UNTESTED`, `OUT OF SCOPE`, or a falsified hypothesis. The label matters less than whether another engineer can inspect how it was obtained.

## Technical discussions as research input

I use external discussions to pressure-test the work, not to accumulate endorsements. The most useful response is often a precise objection that forces a property boundary or claim to become narrower.

Selected examples:

- **CoSAI WS4 · Agent Manifest RFC**  
  [Semantic correctness, execution authority and observed effect as separate properties](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/issues/149#issuecomment-5361848671)

- **CoSAI WS4 · runtime evidence / OCSF boundary**  
  [Admission vs. closure evidence, runtime trust-base integrity and policy separation](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/issues/149#issuecomment-5381095802)

- **AEGIS Core × Agent Authority Conformance**  
  A cross-system dialogue around replay suppression, argument binding, scope declarations and the difference between SDK-level evidence and deployment-level guarantees. The point is not to rank implementations, but to see whether the same vocabulary describes both fairly.

## Principles I keep returning to

```text
reasoning authority != execution authority

a valid receipt != proof of effect

permission != semantic correctness

a pre-tool hook != an enforcement boundary

telemetry != authorization

unknown != safe

OUT OF SCOPE != failure

negative results are results
```

## Where expert review would be valuable

I would particularly like criticism or replication from people working in:

- distributed systems and concurrency
- IAM, capability security and delegated authority
- formal methods and protocol analysis
- policy engines, PDP/PEP architectures and policy-as-code
- agent runtimes, MCP and tool-execution infrastructure
- secure systems architecture and credential isolation
- observability, audit evidence and postcondition verification
- safety evaluation, benchmark methodology and inter-rater agreement

If you can show that an assumption is wrong, a property is underspecified, a test proves less than claimed, or an important dimension is missing, **that is a useful contribution**.

Good collaboration here looks like:

```text
claim → counterexample → narrower property → reproducible test → better architecture
```

Independent assessment of **Agent Authority Conformance**, adversarial review of **REMORA**, and technically serious comparisons with other execution-control systems are especially welcome.

## Background

I am CEO of **Luftfiber AS** and work close to production telecom and operational infrastructure. That environment keeps the research anchored in mundane but important realities: credential custody, tenant boundaries, stale state, blast radius, rollback, auditability and what happens when software touches systems that matter.

My broader interests include Python systems, network automation, MCP infrastructure, trustworthy autonomous operations and the engineering gap between an impressive agent demo and an agent that should be permitted to act.
