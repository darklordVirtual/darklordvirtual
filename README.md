# Stian Skogbrott

**Agentic AI governance · execution assurance · policy-as-code · reliable automation**

I work on a narrow problem with broad consequences:

> **How can autonomous AI agents act against real systems without letting model reasoning become execution authority?**

My current work focuses on action-time authorization, exact-call binding, policy enforcement, runtime evidence, controlled execution, effect verification, and falsifiable evaluation.

## Current research

### [REMORA](https://github.com/darklordVirtual/REMORA-research)

A policy-gated execution assurance layer placed between an agent proposal and the protected tool path.

`proposal → policy decision → review/grant → fresh pre-execution check → exact-call binding → enforcement → dispatch → effect verification`

REMORA deliberately separates properties that are often collapsed into one vague notion of "agent safety":

- deployment integrity
- permission and authority provenance
- semantic correctness
- exact-call integrity
- execution-boundary integrity
- TOCTOU resistance
- observed effect

**Status:** research/shadow-mode software. No production-certification claim. External replication remains welcome.

### [Agent Authority Conformance v0.1](https://github.com/darklordVirtual/REMORA-research/blob/master/docs/benchmarks/agent-authority-conformance-v0.1.md)

A draft, vendor-neutral vocabulary for evaluating agent execution systems property by property rather than collapsing them into a single security score.

The evidence rule is intentionally strict: `PASS` requires resolved evidence; `UNTESTED` is not failure; `OUT OF SCOPE` is not a deficiency.

First application:
[AEGIS Core 3.4.0 × REMORA crosswalk](https://github.com/darklordVirtual/REMORA-research/blob/master/docs/benchmarks/aegis-remora-crosswalk.md).

## How I work

I am more interested in **falsifiable claims than impressive demos**.

1. State the property being claimed.
2. Build a test or benchmark that can disprove it.
3. Bind results to committed evidence.
4. Keep scope and caveats with the result.
5. Publish negative results instead of deleting failed hypotheses.
6. Feed useful findings back into architecture, code, and external technical discussions.

A representative example is the REMORA BFCL C-ext3 ablation: structural controls accepted 24/500 wrong-tool calls, contracts + intent reduced that to 6/500, and a stricter semantic floor reduced native wrong-tool ACCEPTs to 0/500. The same run also missed important autonomy targets. Both sides remain published.

- [Claim register](https://github.com/darklordVirtual/REMORA-research/blob/master/docs/assurance/claim_register_v1.yaml)
- [Negative results](https://github.com/darklordVirtual/REMORA-research/blob/master/NEGATIVE_RESULTS.md)

## Selected projects

### [Assured Agent Execution](https://github.com/darklordVirtual/assured-agent-execution)

A product-oriented execution layer built around pinned REMORA artifacts: exact-payload approval binding, separate proposer/approver/executor identities, controlled dispatch, and postcondition verification.

### [vericlaim](https://github.com/darklordVirtual/vericlaim)

CI/CD for claims: mechanically binds documentation, benchmarks, published results, and reusable code to the evidence that supports them, so drift fails the build instead of silently becoming project truth.

## Standards and technical discussions

I use external discussions as part of the research loop: expose an architectural claim, let other implementers attack it, then bring the useful disagreement back into the model.

- **CoSAI WS4 · Agent Manifest RFC**  
  [Semantic correctness, execution authority, and observed effect as separate properties](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/issues/149#issuecomment-5361848671)

- **CoSAI WS4 · runtime evidence / OCSF boundary**  
  [Admission vs. closure evidence, runtime trust-base integrity, and policy separation](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/issues/149#issuecomment-5381095802)

These discussions are useful precisely when they expose a missing property, an artificial boundary, or a claim that needs to be narrowed.

## Principles

```text
reasoning authority != execution authority

a valid receipt != proof of effect

permission != semantic correctness

telemetry != authorization

unknown != safe

OUT OF SCOPE != failure

negative results are results
```

## Current interests

- agent authority and execution assurance
- MCP and agent-to-tool security boundaries
- policy-as-code and PDP/PEP architectures
- runtime evidence and trustworthy observability
- delegation and short-lived authority
- semantic tool-selection evaluation
- postcondition / effect verification
- conformance models and reproducible benchmarks
- Python systems for reliable autonomous workflows

## Background

I build software while working close to real operational infrastructure and production systems. That makes failure modes, credential custody, blast radius, rollback, auditability, and boring deterministic controls unusually interesting to me.

If you are working on agent runtimes, governance, MCP security, execution controls, or reproducible evaluation, I am particularly interested in **technical comparison, adversarial review, and independent replication**.
