# Stian Skogbrott

**AI systems engineering · Agent execution assurance · Applied AI · Critical infrastructure**

I design and build software that connects AI reasoning to **controlled, observable real-world actions**. My work spans Python, API integrations, identity and authorization, distributed systems, operational networks and evidence-driven evaluation.

**My engineering principle:** a model can propose an action; it should not grant itself the authority to execute it.

**[See working systems](#selected-engineering-work) · [Public RFC contributions](#public-rfc-contributions-and-technical-reviews) · [Inspect the evidence](#evidence-and-claim-boundaries) · [Get in touch](#background-and-contact)**

## Selected engineering work

| Project | What I built / investigate | Inspect it |
| --- | --- | --- |
| **[REMORA Research](https://github.com/darklordVirtual/REMORA-research)** | Research implementation for policy-gated tool execution: exact-call authorization, bounded review, dispatch separation, effect evidence and negative-result reporting. **Research / controlled-pilot scope**, not a certified production security product. | [Guided scenarios](https://github.com/darklordVirtual/REMORA-research#try-it-in-two-minutes) · [Claim register](https://github.com/darklordVirtual/REMORA-research/blob/master/docs/assurance/claim_register_v1.yaml) |
| **[autonomous-ot-control](https://github.com/darklordVirtual/autonomous-ot-control)** | Executable **simulation-only** digital caretaker for HVAC, lighting and other building controls. Signed work orders, separated credentials, policy decisions, synthetic actuators and independent read-back connect authorization to observable effects. **No physical OT write path.** | [Architecture / run guide](https://github.com/darklordVirtual/autonomous-ot-control#how-it-works) · [Federated results](https://github.com/darklordVirtual/autonomous-ot-control/blob/main/docs/federation/RESULTS.md) |
| **[EOS / Proptech.Energy](https://github.com/darklordVirtual/EOS)** | Building-energy software combining meter ingestion, multi-tenant data, dashboards, anomaly analysis and AI-assisted operational insights. Draws on my hands-on telecom and building-systems experience. | [Platform overview](https://github.com/darklordVirtual/EOS#overview) · [Architecture](https://github.com/darklordVirtual/EOS/blob/main/deployments/hel1/openclaw/workspace/eos-arkitektur-2026-03-28.md) |
| **[Agent Authority Conformance Profiles (AACP)](https://github.com/darklordVirtual/agent-authority-conformance)** | Independent **draft** evidence model for assessing distinct agent-authorization properties without turning unrelated PASS/FAIL results into an aggregate security score. Separate from the LF Decentralized Trust lab of a similar name. | [Seven properties and status semantics](https://github.com/darklordVirtual/agent-authority-conformance#the-seven-properties) |
| **[Assured Agent Execution](https://github.com/darklordVirtual/assured-agent-execution)** | Reference implementation connecting the REMORA research kernel to approval, execution and selected system-of-record read-back patterns. | [Architecture and example flow](https://github.com/darklordVirtual/assured-agent-execution#architecture) |
| **[vericlaim](https://github.com/darklordVirtual/vericlaim)** | CI-oriented checks for drift between technical claims and the supporting artifacts used to justify them. | [Repository and implementation](https://github.com/darklordVirtual/vericlaim) |

My applied-AI experiments also include **DressMeUp/StyleDNA**, a virtual fashion try-on and AI-styling prototype. That work is not represented here as a reproducible public deployment.

## Public RFC contributions and technical reviews

I participate in public technical work around CoSAI / OASIS Workstream 4 (WS4), especially **authorization at the moment of action**, **containment**, **observer independence** and **the limits of security evidence**. These are **traceable review and implementation contributions**; I do not claim to be the primary author of the RFCs, to speak for CoSAI, or to hold standards approval or certification.

| Public discussion | My specific contribution | Evidence |
| --- | --- | --- |
| **[WS4 Agent Manifest RFC discussion #149](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/issues/149)** | Proposed the non-transitive boundary between a valid declaration, authorized exact call, non-bypassable execution path and verified external effect; outlined isolating negative tests. The proposal was explicitly taken up in the discussion. | [My technical comment](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/issues/149#issuecomment-5443926273) · [Response](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/issues/149#issuecomment-5595582544) |
| **[WS4 Evidence Sufficiency RFC discussion #189](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/issues/189)** | Refined when a verifier may return `not_established`, separated checker inputs from authored test expectations, and corrected provenance boundaries for example vectors. | [My review](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/issues/189#issuecomment-5630431104) · [REMORA regression artifact](https://github.com/darklordVirtual/REMORA-research/commit/f10ca2a493755f64df9225a8ccb5636aa344a43a) |
| **[WS4 Containment follow-on #172](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/issues/172)** | Contributed to the documented containment/evidence discussions and received contributor attribution in the draft. | [Merged contributor-credit update](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/pull/248) · [My credit preference](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/issues/172#issuecomment-6500254075) |
| **[WS4 Observer independence review, PR #240](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/pull/240)** | Checked proposed observer criteria against REMORA and separated *key separation*, *custody independence*, *observer independence* and *observation coverage*. The distinction was discussed and carried forward in later text. | [My review](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/pull/240#issuecomment-6019873973) · [Follow-on PR #270](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/pull/270) |

These links demonstrate **participation and review impact**, not authorship of entire specifications or organizational endorsement.

## Evidence and claim boundaries

I prefer a reproducible test and a narrow claim over an impressive number without context.

- **[REMORA claim register](https://github.com/darklordVirtual/REMORA-research/blob/master/docs/assurance/claim_register_v1.yaml)** — claims tied to evidence and evaluation scope.
- **[Capability maturity register](https://github.com/darklordVirtual/REMORA-research/blob/master/docs/assurance/capability_register_v1.yaml)** — implemented, connected and unestablished capabilities.
- **[Negative results](https://github.com/darklordVirtual/REMORA-research/blob/master/NEGATIVE_RESULTS.md)** — what did *not* work, and where utility or assurance remains limited.
- **[OT testbed results](https://github.com/darklordVirtual/autonomous-ot-control/blob/main/docs/federation/RESULTS.md)** — results from bounded, identified test runs; no claim of live physical control.

**Important limitation:** simulation, conformance-vector reproduction and research benchmarks do not independently establish complete mediation in an arbitrary production deployment. A passing result only supports the property, assumptions and revision actually tested.

## Background and contact

I am the founder and managing director of **[Luftfiber AS](https://luftfiber.no/)** in Norway. My background includes more than 15 years across telecommunications, ISP infrastructure, Linux services, network security, wireless systems and building technology. That operational experience shapes my software design: explicit ownership, least privilege, recoverable failures and verifiable outcomes.

**Technology:** Python · TypeScript/React · PostgreSQL/Supabase · REST APIs · Docker/Linux · LLMs and tool integrations · policy-as-code · networking and OT/IoT.

I welcome **engineering collaboration, independent reproduction, technical review and applied-AI/product discussions**.

**[Email](mailto:stian@luftfiber.no) · [LinkedIn](https://www.linkedin.com/in/stianskogbrott/) · [Luftfiber AS](https://luftfiber.no/)**
