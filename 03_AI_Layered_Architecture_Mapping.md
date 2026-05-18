# Output #3 — SE Phases Mapped to the 4‑Layer AI Architecture

Every activity from Output #1 (`P#.A#`) is now mapped into the four layers:

- **Work Process Layer (Biz Process)** — the user activities that drive the phase. *Who* does *what* and *for whom*.
- **Application Layer (Viewer / I‑O)** — the UI/UX surfaces (web UI, chatbot, dashboard, IDE plug‑in, mobile alerts, voice).
- **Agent Layer (Controller / Logic)** — the AI agents and ML services that perform the work (LLM agents, classical ML, heuristic algorithms, RPA, RAG, MCP tools).
- **Data Layer (Model)** — the persisted information (relational DBs, time‑series stores, vector stores / RAG indexes, object stores, knowledge graphs).

Format below per phase:

> **P# — Phase Name**
> **Work Process** · **Application** · **Agent** · **Data**

---

## P1. Requirements Engineering
- **Work Process** — Product Manager, Solution Architect and Customer Program Manager elicit requirements (P1.A1), author the SRS/FRS/NFR (P1.A2), run AI‑assisted quality checks (P1.A3), build the RTM (P1.A4), and run the review board for baselining (P1.A5).
- **Application** — *Requirements Portal* (web), *Customer RFQ Inbox*, *RTM Explorer*, *Chatbot ("Req‑Bot") for clarifications*, *Slack/Teams gateway for elicitation*.
- **Agent** — *Requirement Extraction Agent* (LLM + NER over PDFs/e‑mails), *Ambiguity & INVEST Scoring Agent*, *Spec‑Diff Agent* (NVMe/JEDEC delta detection), *RTM Linking Agent* (embedding similarity), *Review‑Pack Composer Agent*.
- **Data** — Requirements DB, Customer Document Store (object), Spec RAG (NVMe / JEDEC / UFS HCI vectors), RTM Graph DB, Stakeholder Knowledge Graph.

## P2. Architecture & Design
- **Work Process** — Architects, Tech Leads, Security Architects perform P2.A1–A5; design boards approve baselines.
- **Application** — *Design Studio* (web), *ADR Editor*, *C4/UML auto‑renderer*, *Threat‑Model Canvas*, *API Contract Workbench*.
- **Agent** — *Architecture Pattern Recommender*, *ADR Drafting Agent*, *UML / Sequence Diagram Generator*, *NVMe Cmd Table Generator*, *Telemetry Schema Synthesis Agent*, *DFMEA & Threat‑Modeling Agent (STRIDE/LINDDUN)*.
- **Data** — Design Repository, ADR Store, API Contract Registry, Threat Library / CWE / CAPEC RAG, Pattern Catalogue, Design KG.

## P3. Implementation / Coding
- **Work Process** — Firmware / Driver / Automation Engineers commit code; AI agents review and gate.
- **Application** — *IDE plug‑in (Copilot‑like)*, *Pull‑Request Review UI*, *Static‑Analysis Dashboard*, *Unit Test Workbench*, *CLI for scripted refactor*.
- **Agent** — *Code Generation Agent*, *Code Refactor Agent*, *AI Reviewer Agent* (style + security + logic), *Static‑Findings Auto‑Fix Agent* (Coverity / MISRA / CodeQL), *Unit Test Generation Agent*, *Coverage Gap Agent*.
- **Data** — Source Control (Git), Code Vector Index (RAG over codebase), Static‑Findings DB, Unit Test Repo, Coverage Store, Secrets Vault.

## P4. Test Planning & Test Design
- **Work Process** — QA Architects and Test Leads run P4.A1–A5; AI Agents author plans, cases, data, env matrix.
- **Application** — *Test Management UI*, *Risk‑based Strategy Workbench*, *Workload Profile Designer*, *Lab Matrix Visualizer*.
- **Agent** — *Test Plan Generation Agent* (from RTM + risk + history), *Test Case Generation Agent* (SRS + spec → TC), *Workload Synthesis Agent* (FIO/IOMeter), *Env Matrix Optimizer Agent* (set‑cover heuristic).
- **Data** — Test Plan DB, Test Case Repo, Workload Profile Library, Lab/Env Inventory, Historical Defect Density Store.

## P5. Build & Integration
- **Work Process** — Build/Release Engineers and Integration Engineers run P5.A1–A5.
- **Application** — *CI/CD Dashboard*, *Build Artifact Browser*, *BVT Gate Console*, *Defect Triage Inbox*.
- **Agent** — *Self‑Healing CI Agent* (repairs broken pipelines), *Build Signing/Versioning Agent*, *Integration Orchestrator Agent*, *BVT Gate Agent*, *Defect Auto‑Triage Agent* (dedupe + classify + commit‑bisect).
- **Data** — Artifact Repository, Build Telemetry, BVT Result Store, Defect DB, Commit Graph (for bisect).

## P6. Verification & Validation
- **Work Process** — QA Test Engineers, Performance Engineers, Compliance Engineers, Security Engineers, Lab Operators run P6.A1–A9.
- **Application** — *V&V Cockpit* (real‑time test execution), *Compliance Console*, *Perf / QoS Trend Dashboard*, *RCA Workbench*, *Robotics Operator Console*, *Lab Reservation UI*.
- **Agent** — *Functional Test Orchestrator*, *Perf Regression Detector*, *Compliance Conformance Agent* (RAG over spec), *Endurance / EOL Prediction Agent*, *PLI / Surprise‑Removal Agent (drives Robotics)*, *Compat Matrix Optimizer*, *Security Fuzz Guidance Agent*, *Test Impact Analysis Agent* (P6.A8), *Log/Trace Summarization & RCA Agent* (P6.A9).
- **Data** — Test Execution DB, Time‑Series Telemetry (SMART, log pages), Perf Baseline Store, Endurance Trend Store, Spec RAG, Trace / Bus‑capture Object Store, Failure Pattern Vector Index.

## P7. Release Engineering & Customer Release
- **Work Process** — Release Manager, Customer Quality Engineer, Compliance Officer run P7.A1–A5.
- **Application** — *Release Readiness Dashboard*, *Release Notes Studio*, *Customer Qual Portal*, *Compliance Pack Builder*, *Secure Distribution UI*.
- **Agent** — *Release Risk Scoring Agent*, *Release Notes Drafting Agent*, *Qual Pack Assembler*, *Compliance Doc Generator*, *Secure Publish Agent*.
- **Data** — Release Catalogue, Customer Profile DB, Compliance Cert Store, Signing Key Store, Distribution Audit Log.

## P8. Post‑Release / Field Sustenance
- **Work Process** — Support Engineers, Reliability Engineers, FA Lab, Product Manager.
- **Application** — *Field Health Dashboard*, *RMA / FA Workbench*, *Voice‑of‑Customer Console*, *Hotfix Cockpit*, *Lessons‑Learned KB Browser*.
- **Agent** — *Field Telemetry Anomaly Agent*, *RMA / FA Correlation Agent*, *VOC NLP Agent* (sentiment, topic), *Hotfix Planner Agent*, *Lessons‑Learned KB Updater Agent* (feeds P1).
- **Data** — Field Telemetry Lake, RMA / FA DB, Customer Ticket Store, Hotfix Catalogue, Lessons‑Learned KB (vector), Failure → FW correlation Graph.

---

## Cross‑Phase / Cross‑Layer Backbones (apply to every phase)

These are not phase‑specific; they live underneath and serve all phases.

- **Identity, AuthN/AuthZ, RBAC** (Application + Data).
- **Observability** (logs, metrics, traces for the agents themselves).
- **Model Ops** — model registry, prompt registry, eval harness, drift monitoring (Agent + Data).
- **Knowledge Mesh** — central RAG across specs, code, design, tests, defects, field data (Data).
- **Orchestration / MCP bus** — how agents call tools and each other (Agent).
- **Human‑in‑the‑Loop fabric** — review queues, approval gates, audit trail (Application + Data).

These backbones are reused unchanged when Zion sub‑systems are embedded in Output #5.
