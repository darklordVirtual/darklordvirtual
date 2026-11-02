# Stian Skogbrott

**AI systems engineering · Agent execution assurance · Applied AI · Critical infrastructure**

I design and build software that connects AI reasoning to **controlled, observable real-world actions**. My work spans Python, API integrations, identity and authorization, distributed systems, operational networks and evidence-driven evaluation.

**My engineering principle:** a model can propose an action; it should not grant itself the authority to execute it.

**[See working systems](#selected-engineering-work) · [Public RFC contributions](#public-rfc-contributions-and-technical-reviews) · [Inspect the evidence](#evidence-and-claim-boundaries) · [Get in touch](#background-and-contact)**

## Selected engineering work

### 1. [REMORA Research](https://github.com/darklordVirtual/REMORA-research): Governed AI execution

Policy-gated tool execution with exact-call authorization, bounded review, separated dispatch, effect evidence and transparent negative-result reporting.

**Inspect:** [run five guided scenarios](https://github.com/darklordVirtual/REMORA-research#try-it-in-two-minutes) · [machine-readable claim register](https://github.com/darklordVirtual/REMORA-research/blob/master/docs/assurance/claim_register_v1.yaml)

*Scope: research software for bounded, controlled pilot evaluation; not a certified production security product.*

### 2. [autonomous-ot-control](https://github.com/darklordVirtual/autonomous-ot-control): Governed digital caretaker

A runnable **simulation-only** testbed for HVAC, lighting and other building controls. It combines signed work orders, separate credentials, policy decisions, simulated actuators and independent read-back. The tests demonstrate where action permission and observed effect must be checked separately.

**Inspect:** [architecture and runnable setup](https://github.com/darklordVirtual/autonomous-ot-control#how-it-works) · [federated test results](https://github.com/darklordVirtual/autonomous-ot-control/blob/main/docs/federation/RESULTS.md)

*Scope: simulated plant and bounded test runs. No physical OT/BMS write path.*

### 3. [EOS / Proptech.Energy](https://github.com/darklordVirtual/EOS): Data and AI for building operations

Building-energy software with meter ingestion, multi-tenant data, dashboards, anomaly analysis and AI-assisted operational insights, informed by hands-on infrastructure and building-systems work.

**Inspect:** [platform overview](https://github.com/darklordVirtual/EOS#overview) · [architecture and operating model](https://github.com/darklordVirtual/EOS/blob/main/deployments/hel1/openclaw/workspace/eos-arkitektur-2026-03-28.md)

### Other open engineering work

- **[Agent Authority Conformance Profiles (AACP)](https://github.com/darklordVirtual/agent-authority-conformance)**: independent *draft* evidence model for seven distinct agent-authorization properties, without aggregate security scores. This is **not** the LF Decentralized Trust lab of a similar name.
- **[Assured Agent Execution](https://github.com/darklordVirtual/assured-agent-execution)**: reference control-plane patterns joining REMORA to approval, execution and selected system-of-record effect checks.
- **[vericlaim](https://github.com/darklordVirtual/vericlaim)**: CI-oriented checks for drift between technical claims and supporting artifacts.

My applied-AI experiments also include **DressMeUp/StyleDNA**, a virtual fashion try-on and AI-styling prototype. I do not present this as a reproducible public deployment.

## Public RFC contributions and technical reviews

I contribute technical reviews, testable boundary statements and implementation feedback to public discussions in **CoSAI / OASIS Workstream 4 (WS4)**. Here are concrete examples, each linked to the actual contribution rather than a general standards logo:

- **[Agent Manifest RFC discussion #149](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/issues/149)**: I proposed the **non-transitive boundary** between declared deployment state, authorized exact calls, non-bypassable execution and verified effects, with specific negative tests. [Read my proposal](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/issues/149#issuecomment-5443926273) and [the author's response](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/issues/149#issuecomment-5595582544).
- **[Evidence Sufficiency RFC discussion #189](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/issues/189)**: I reviewed the strict meaning of `not_established`, proposed separating checker input from authored test expectations and corrected vector provenance boundaries. [Read my review](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/issues/189#issuecomment-5630431104) and [inspect a related REMORA regression artifact](https://github.com/darklordVirtual/REMORA-research/commit/f10ca2a493755f64df9225a8ccb5636aa344a43a).
- **[Containment follow-on #172](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/issues/172)**: contribution to the documented containment/evidence work, with explicit contributor attribution in the draft. [Merged attribution update](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/pull/248) and [credit preference](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/issues/172#issuecomment-6500254075).
- **[Observer independence, PR #240](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/pull/240)**: I tested a proposed observer criterion against REMORA and distinguished **key separation**, **custody independence**, **observer independence** and **observation coverage**. [Read my review](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/pull/240#issuecomment-6019873973) and [the later merged follow-on](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/pull/270).

These are **review and engineering contributions**; they are not claims of primary RFC authorship, CoSAI representation, standards adoption, certification or endorsement of REMORA.

## Evidence and claim boundaries

I prefer a reproducible test and a narrow claim over an impressive number without context.

- **[REMORA claim register](https://github.com/darklordVirtual/REMORA-research/blob/master/docs/assurance/claim_register_v1.yaml)**: claims tied to evidence and evaluation scope.
- **[Capability maturity register](https://github.com/darklordVirtual/REMORA-research/blob/master/docs/assurance/capability_register_v1.yaml)**: implemented, connected and unestablished capabilities.
- **[Negative results](https://github.com/darklordVirtual/REMORA-research/blob/master/NEGATIVE_RESULTS.md)**: what did *not* work, and where utility or assurance remains limited.
- **[OT testbed results](https://github.com/darklordVirtual/autonomous-ot-control/blob/main/docs/federation/RESULTS.md)**: results from bounded, identified test runs; no claim of live physical control.

**Important limitation:** simulation, conformance-vector reproduction and research benchmarks do not independently establish complete mediation in an arbitrary production deployment. A passing result only supports the property, assumptions and revision actually tested.

## Background and contact

I am the founder and managing director of **[Luftfiber AS](https://luftfiber.no/)** in Norway. My background includes more than 15 years across telecommunications, ISP infrastructure, Linux services, network security, wireless systems and building technology. That operational experience shapes my software design: explicit ownership, least privilege, recoverable failures and verifiable outcomes.

**Technology:** Python · TypeScript/React · PostgreSQL/Supabase · REST APIs · Docker/Linux · LLMs and tool integrations · policy-as-code · networking and OT/IoT.

I welcome **engineering collaboration, independent reproduction, technical review and applied-AI/product discussions**.

**[Email](mailto:stian@luftfiber.no) · [LinkedIn](https://www.linkedin.com/in/stianskogbrott/) · [Luftfiber AS](https://luftfiber.no/)**
