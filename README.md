# Stian Skogbrott

**Agentic AI governance · execution assurance · policy-as-code · reliable automation**

CEO at **Luftfiber AS**. I build software close to real operational infrastructure, with a current focus on one narrow problem with broad consequences:

> **How can autonomous AI agents act against real systems without letting model reasoning become execution authority?**

My work follows a simple progression:

```text
research                     conformance                     deployment
   │                              │                              │
   ▼                              ▼                              ▼
REMORA-research  ─────►  Agent Authority Conformance  ─────►  Assured Agent Execution
```

The common thread is action-time authority: who authorized an action, what exactly was authorized, whether the protected effect can bypass the governed path, and whether the external result can be verified.

## Current work

### [Agent Authority Conformance](https://github.com/darklordVirtual/agent-authority-conformance)

A standalone, vendor-neutral evidence model for evaluating authority and execution controls in agentic systems.

It separates seven properties that are often collapsed into one vague claim that a tool call was “authorized”:

- **A** Receipt Integrity
- **B** Authority Provenance
- **C** Exact-Call Integrity
- **D** Semantic Authority
- **E** Execution-Boundary Integrity
- **F** TOCTOU Resistance
- **G** Effect Verification

The evidence rule is intentionally strict: `PASS` requires resolved evidence; `UNTESTED` is not failure; `OUT OF SCOPE` is not a deficiency; and the seven properties must never be aggregated into a security score or ranking.

The repository includes a normative v0.1 specification, a machine-readable assessment schema, CI validation, and bounded cross-system examples.

### [REMORA Research](https://github.com/darklordVirtual/REMORA-research)

A policy-gated execution assurance layer placed between an agent proposal and the protected tool path.

```text
proposal
   ↓
policy decision
   ↓
review / grant
   ↓
fresh pre-execution check
   ↓
exact-call binding
   ↓
enforcement + dispatch
   ↓
effect verification
```

REMORA is research/shadow-mode software and makes no production-certification claim. Its claims are tied to committed evidence, explicit scope and published negative results.

- [Claim register](https://github.com/darklordVirtual/REMORA-research/blob/master/docs/assurance/claim_register_v1.yaml)
- [Negative results](https://github.com/darklordVirtual/REMORA-research/blob/master/NEGATIVE_RESULTS.md)

### [Assured Agent Execution](https://github.com/darklordVirtual/assured-agent-execution)

Product-oriented work on turning execution-assurance research into deployable control-plane patterns: exact-payload approval binding, separate proposer/approver/executor identities, controlled dispatch, audit evidence and postcondition verification.

### [vericlaim](https://github.com/darklordVirtual/vericlaim)

CI/CD for claims: mechanically binds documentation, benchmarks, published results and reusable code to the evidence that supports them, so drift fails the build instead of silently becoming project truth.

## How I work

I am more interested in **falsifiable claims than impressive demos**.

1. State the property being claimed.
2. Build a test or benchmark that can disprove it.
3. Bind the result to committed evidence.
4. Keep scope and caveats with the result.
5. Publish negative results instead of deleting failed hypotheses.
6. Feed useful disagreement back into architecture, code and the evaluation model.

A representative REMORA example is the BFCL C-ext3 ablation: structural controls accepted 24/500 wrong-tool calls, contracts + intent reduced that to 6/500, and a stricter semantic floor reduced native wrong-tool ACCEPTs to 0/500. The same run missed important autonomy targets. Both outcomes remain published.

## Standards and technical discussions

External technical discussions are part of the research loop: expose an architectural claim, let other implementers attack it, then turn useful disagreement into a sharper model or test.

- **CoSAI WS4 · Agent Manifest RFC**  
  [Semantic correctness, execution authority, and observed effect as separate properties](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/issues/149#issuecomment-5361848671)

- **CoSAI WS4 · runtime evidence / OCSF boundary**  
  [Admission vs. closure evidence, runtime trust-base integrity, and policy separation](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/issues/149#issuecomment-5381095802)

- **AEGIS Core dialogue**  
  Cross-system discussion around replay suppression, exact-call binding, scope declarations and the boundary between SDK evidence and deployment evidence now feeds directly into the standalone Agent Authority Conformance model.

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
- exact-call and semantic tool-selection integrity
- postcondition / effect verification
- conformance models and reproducible benchmarks
- Python systems for reliable autonomous workflows
- telecom and network automation

If you are working on agent runtimes, governance, MCP security, execution controls or reproducible evaluation, I am particularly interested in **technical comparison, adversarial review and independent replication**.
