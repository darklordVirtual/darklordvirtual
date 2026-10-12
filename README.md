# Stian Skogbrott

**Agent execution security · Python systems · Operational infrastructure**

I build and research systems that make AI-agent actions controllable, auditable and inspectable. My focus is the boundary between a model proposing an action and an operational system being authorized to execute it.

**Core principle: reasoning authority is not execution authority.** Approval, execution authority and evidence of an external effect are separate properties.

I lead **Luftfiber AS**, working with telecommunications and operational infrastructure in Norway. Production operations inform my approach to software: least privilege, explicit trust boundaries, durable state, failure recovery and verification of what actually changed.

## Research and technical contributions

I contribute technical reviews, reproducible tests and bounded conformance cases to public discussions on agent security, MCP/tool authorization and evidence sufficiency, including [CoSAI / OASIS WS4](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/issues/189) and [agent governance interoperability](https://github.com/aeoess/agent-governance-vocabulary/issues/177).

My work emphasizes what evidence can actually establish. A missing observation is not automatically proof of a violation; a passing test is not proof of complete runtime enforcement. Participation in these discussions does not imply standards endorsement, certification or adoption of my projects.

## Selected projects

| Project | What it addresses |
|---|---|
| **[REMORA Research](https://github.com/darklordVirtual/REMORA-research)** | Policy-gated agent execution, exact-call and semantic authority, execution evidence, bounded evaluations and published negative results. |
| **[Agent Authority Conformance Profiles (AACP)](https://github.com/darklordVirtual/agent-authority-conformance)** | Vendor-neutral, draft conformance profiles for seven distinct authority and execution properties. Bounded Claim Reproduction (BCR), explicit inconclusive outcomes and no aggregate security score. |
| **[Assured Agent Execution](https://github.com/darklordVirtual/assured-agent-execution)** | Reference control plane for exact-payload approval, separated execution roles, auditable lifecycle and selected system-of-record effect checks. |
| **[vericlaim](https://github.com/darklordVirtual/vericlaim)** | Evidence-linked CI checks that detect drift between documented claims, benchmarks and supporting artifacts. |
| **[pilotfish](https://github.com/darklordVirtual/pilotfish)** | Experimental policy-governed network link selection; operational router integration remains future work. |

## Inspect the evidence

- **[Research claims](https://github.com/darklordVirtual/REMORA-research/blob/master/docs/assurance/claim_register_v1.yaml)**: machine-readable claim status, evidence level, sample sizes and caveats.
- **[Capability maturity](https://github.com/darklordVirtual/REMORA-research/blob/master/docs/assurance/capability_register_v1.yaml)**: what is implemented, wired, persisted or still unestablished.
- **[Execution-path quickstart](https://github.com/darklordVirtual/REMORA-research/blob/master/docs/deployment/execution-quickstart.md)**: the governed reference path and its credential-topology limits.
- **[Negative results](https://github.com/darklordVirtual/REMORA-research/blob/master/NEGATIVE_RESULTS.md)**: failed hypotheses, safety/utility trade-offs and open research boundaries.
- **[Federation and self-service evidence](https://github.com/darklordVirtual/REMORA-research/blob/master/docs/interop/FEDERATION.md)**: pinned interoperability artifacts, reproduction levels and claim ceilings.
- **[Research paper](https://github.com/darklordVirtual/REMORA-research/blob/master/paper/remora_paper.md)**: current manuscript and its evaluation limitations.

REMORA remains research/shadow-mode software. Bounded external reproductions of specific interoperability contracts do not establish production enforcement, complete runtime coverage, independent safety certification or universal agent safety.

## How I work

I define a bounded property, identify the evidence needed to establish it, and build tests that can falsify it. Claims stay tied to specific revisions and assumptions. When evidence falls short, I narrow the claim rather than stretching the conclusion.

My engineering work spans Python, distributed systems, identity and access controls, policy-as-code, MCP/tool integration and network automation.

## Collaboration

I welcome concrete engineering collaboration, independent reproduction and adversarial review of agent execution controls and evidence semantics. A useful starting point is a specific workflow: which action is proposed, who can authorize it, which credential path can execute it and how its effect can be verified.

**Contact:** [support@luftfiber.no](mailto:support@luftfiber.no)
