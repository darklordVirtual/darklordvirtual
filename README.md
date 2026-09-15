# Stian Skogbrott

**AI execution controls · Python systems · network automation**

I build systems that control what AI agents are allowed to do and make those decisions inspectable.

I am CEO of **Luftfiber AS**, working with telecom and operational infrastructure in Norway. That experience shapes my software work: keeping credentials under control, containing failures, handling stale state and verifying what actually changed.

My core architectural principle is **reasoning authority ≠ execution authority**. A model can propose an action; approval and execution depend on authority established outside its reasoning loop.

## Open standards & AI security

I contribute technical review and executable conformance cases to discussions in [CoSAI / OASIS WS4](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems).

The [evidence-sufficiency RFC #189](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/issues/189) explicitly references my checker, regression artifacts and cases where identical observations can correspond to different underlying histories. Those cases show why missing evidence cannot automatically establish either conformance or a violation.

My contribution focuses on what a verifier can legitimately conclude, including `NOT_ESTABLISHED`, and on keeping test expectations separate from evidence inputs. This is participation in an ongoing standards discussion; it does not imply adoption or endorsement of my projects.

## Selected projects

| Project | Purpose |
|---|---|
| **[REMORA Research](https://github.com/darklordVirtual/REMORA-research)** | Research into policy-gated agent execution, authorization binding and evidence of external effects. Includes reproducible experiments, a claim register and published negative results. |
| **[Agent Authority Conformance](https://github.com/darklordVirtual/agent-authority-conformance)** | An independent evidence model for seven authority and execution properties. Draft v0.2 adds explicit inconclusive verdicts, stricter evidence requirements and a bounded reference checker. |
| **[Assured Agent Execution](https://github.com/darklordVirtual/assured-agent-execution)** | Product-oriented control-plane work: separate approval and execution roles, exact-payload binding, selected effect verification and an auditable lifecycle. |
| **[vericlaim](https://github.com/darklordVirtual/vericlaim)** | CI checks that bind documented claims and benchmark numbers to their supporting artifacts, detecting drift when the evidence changes. |
| **[pilotfish](https://github.com/darklordVirtual/pilotfish)** | Early research into network link selection governed by policy, cost constraints and evidence freshness. Includes a decision core and simulator; router adapters remain future work. |

REMORA is research/shadow-mode software. Each project documents its own scope and limitations; the portfolio makes no claim of production certification or universal agent safety.

## Inspect the evidence

Three useful starting points:

- **[Claims and reproduction evidence](https://github.com/darklordVirtual/REMORA-research/blob/master/docs/02-evidence-and-claims.md)** — inspect the artifacts and caveats behind individual claims, with the [machine-readable register](https://github.com/darklordVirtual/REMORA-research/blob/master/docs/assurance/claim_register_v1.yaml) as a companion.
- **[Negative results](https://github.com/darklordVirtual/REMORA-research/blob/master/NEGATIVE_RESULTS.md)** — failed hypotheses, withdrawn claims and known limitations remain part of the record.
- **[Public technical discussion](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/issues/189)** — follow the reasoning, objections and unresolved questions around evidence sufficiency.

For a longer read, see the [REMORA paper (PDF)](https://github.com/darklordVirtual/REMORA-research/blob/master/paper/remora_paper.pdf). The [v0.11.0 release](https://github.com/darklordVirtual/REMORA-research/releases/tag/v0.11.0) provides downloadable artifacts and checksums. AAE documents its separate [pinned core and verification procedure](https://github.com/darklordVirtual/assured-agent-execution/blob/main/docs/pinned-core.md).

## How I work

I start with a bounded property, identify the evidence it needs and build a test that can expose a violation. Claims stay tied to revisions and explicit assumptions. When a result fails to support the claim, I narrow the claim or change the implementation.

My work spans Python, distributed systems, policy-as-code, identity and access controls, MCP/tool integration and network automation.

## Work with me

Through Luftfiber, I am interested in engineering work on governed AI integrations, Python automation and reliable operational infrastructure. I also welcome independent replication, adversarial review and collaboration on executable conformance cases.

A useful starting point is a concrete workflow: which actions it needs, who can authorize them and how their effects can be checked.

**Contact:** [support@luftfiber.no](mailto:support@luftfiber.no)
