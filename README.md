# Awesome-AI-Driven-Security-Operations-Hub

# Awesome-AI-Driven-Security-Operations-Hub

**Top AI Driven Security Operations Hub (Opensource) 🌟 Star if you like it! 🌟**



**Curated List of SaaS Products & Open-Source GitHub Projects**

*Focused on Agentic SOC Triage, LLM-Powered Investigation, Security Data Lakes & Self-Hosted Detection Engineering*

**Last updated: November 2026**



This repository tracks notable **SaaS platforms** and **open-source projects** for **AI-Driven Security Operations**. These tools enable SOC teams to ingest alerts from across the security stack, correlate and deduplicate signals, triage with AI agents, and orchestrate response—from fully managed enterprise platforms with agentic investigation to open-source SOC stacks that give teams complete control over their detection logic and LLM provider.



**Examples** include Druva DruAI, Microsoft Security Copilot, CrowdStrike Charlotte AI, Palo Alto Cortex XSIAM, Google SecOps (Chronicle), Databricks Mosaic AI, H2O.ai h2oGPTe, Scale AI, and Hugging Face Enterprise (the category leaders in commercial space).



**Open-source emphasis**: This section is expanded with every relevant project for self-hosted AI SOC, alert fusion, and open detection engineering. **Critical note**: The open-source landscape has matured dramatically—**AiSOC** is the most complete self-hosted AI Security Operations Center, with 833 executable detection rules, LLM-agent triage, and a replayable Investigation Ledger, running with no API keys on a bundled local model . **Sentora** offers an air-gap-capable SIEM/EDR/SOAR stack with AI triage and threat feeds . **Security Shallots** provides the lightest possible entry point, running on a Raspberry Pi . No open-source project matches CrowdStrike Charlotte AI's adversary intelligence or Cortex XSIAM's platform breadth, but for core SOC triage and investigation, the options are production-capable.



Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.



## Table of Contents

- [SaaS/Hosted Platforms](#saas-hosted-platforms)

- [Open-Source GitHub Projects](#open-source-github-projects)

- [How to Contribute](#how-to-contribute)

- [Disclaimer](#disclaimer)



## SaaS/Hosted Platforms



- **Druva DruAI**

  **Agentic AI for data security operations** within Druva's cloud platform. **Features**: **Deep Analysis Agents** break investigations into steps, coordinate across systems, and synthesize findings into consolidated reports—reducing 2–3 day manual investigations to **8–10 minutes**; **Notify Me workflows** run deep analysis in background and email results; **Dru MetaGraph** provides tenant-specific graph intelligence across backups, identities, configurations, and telemetry; **Agentic Memory** retains session context and organizational knowledge; **multimodal** supports screenshot uploads for troubleshooting . **Pricing**: Quote-only; bundled with Druva platform. **Free tier**: None. **Best for**: Druva customers wanting agentic investigation over backup and security telemetry—**trade-off**: requires Druva platform commitment; not a standalone SOC tool.



- **Microsoft Security Copilot**

  **Generative AI for security operations** integrated across Microsoft Defender, Sentinel, and Intune. **Pricing**: **Security Compute Units (SCUs)** provisioned hourly in fixed clock blocks; **overage capacity** billed on demand; **M365 E5/E7** customers get auto-provisioned default capacity . **Free tier**: Included capacity for M365 E5/E7. **Best for**: Microsoft-centric SOCs wanting AI-assisted investigation within existing workflows—**trade-off**: SCU provisioning requires usage modeling; best value within Microsoft ecosystem.



- **CrowdStrike Charlotte AI**

  **Agentic AI within Falcon platform** for detection, investigation, and response. **Pricing**: Quote-only; requires Falcon platform. **Free tier**: None. **Best for**: CrowdStrike customers wanting AI-driven triage with adversary intelligence correlation—**trade-off**: ecosystem lock-in; requires Falcon investment.



- **Palo Alto Cortex XSIAM**

  **AI-driven SecOps platform** consolidating SIEM, SOAR, ASM, and XDR. **Pricing**: Quote-only; enterprise contracts. **Free tier**: None. **Best for**: enterprises wanting a single platform for security operations with AI-driven analytics—**trade-off**: enterprise-only; implementation complexity.



- **Google SecOps (Chronicle)**

  **Cloud-native SIEM** with Gemini AI for detection and investigation. **Pricing**: Consumption-based; quote-only. **Free tier**: Trial available. **Best for**: Google Cloud organizations wanting native AI-driven security operations.



- **Databricks Mosaic AI**

  **Lakehouse AI platform** for building custom security analytics and agents. **Pricing**: **Foundation Model APIs** offer pay-per-token for development and **provisioned throughput** for production with compliance certifications including HIPAA . **Free tier**: Community Edition limited. **Best for**: data teams building custom security AI on their lakehouse—**trade-off**: requires Databricks platform and ML engineering.



- **H2O.ai h2oGPTe**

  **Enterprise agentic AI platform** with document AI, audio, vision, and guardrails. **Features**: **79.7% accuracy on GAIA benchmark** (vendor-reported, June 2025); **air-gapped and on-premise deployment**; **SOC 2 Type 2, ISO 27001, FedRAMP High** (government edition) . **Pricing**: **Quote-only**; annual contracts; no self-serve pricing. **Free tier**: None. **Best for**: regulated industries (banking, government, healthcare) needing air-gapped agentic AI—**trade-off**: no self-serve evaluation; complex setup .



- **Scale AI**

  **Data platform and AI application development** for enterprises. **Pricing**: Quote-only. **Free tier**: None. **Best for**: organizations needing high-quality training data and model evaluation.



- **Hugging Face Enterprise**

  **AI platform with enterprise security and access controls**. **Pricing**: **Team $20/user/month** (1 TB private storage per seat, 40 min ZeroGPU/day, 3,000 API req/5 min); **Enterprise** custom (1 TB private per seat, 60 min ZeroGPU, 6,000 req/5 min, SSO, audit logs, SCIM) . **Free tier**: Yes, free plan available. **Best for**: teams wanting open model access with enterprise governance—**trade-off**: platform for building AI, not a SOC tool.



## Open-Source GitHub Projects



- **AiSOC**

  **Open-source AI Security Operations Center** (MIT) — **the most complete self-hosted AI SOC** found in this research, with alert fusion, LLM-agent triage, and a replayable Investigation Ledger . **Features**: **Ingest** normalizes telemetry and stamps an activity projection on every event; **fusion** runs **833 executable detection rules** (of 7,015 on disk) plus 76 sliding-window rules with tenant-specific tuning; **correlation** groups related alerts; **AI agents** investigate and write reasoning to the **Investigation Ledger**—every prompt, tool call, citation, verdict, and token cost logged; **grounding is checked**—verdicts citing indicators not in evidence are demoted to human review; **governed response**—actions require human approval with permission tier checks; **signed evidence bundles** for every investigation . **Deployment profiles**: **core** (16 services, ~8 GB RAM, full alerting pipeline + local LLM), **full** (22 services, ~12 GB, adds event lake, entity graph, search), **demo** (core + synthetic data) . **Ships with a local model**—Ollama runs pinned `llama3.2:3b-instruct-q4_K_M` (~2 GB) for CPU-only triage; no API key required . **Tech stack**: Python/FastAPI, LangGraph, Kafka/Redpanda, PostgreSQL, ClickHouse, OpenSearch, Neo4j, Qdrant. **Deploy**: Self-hosted (Docker Compose; `make up`) or Railway one-click . **Trade-off**: **Not a SIEM replacement**—it correlates and investigates, but does not replace long-term log retention; **requires ~8 GB RAM minimum** for core profile; local model is not frontier-quality (44/50 usable triage verdicts on test) . **Best for**: SOC teams wanting a production-capable, self-hosted AI triage and investigation stack with full auditability—especially those wanting to start without API keys or vendor commitments.



- **Sentora**

  **Open-source, self-hosted AI-powered SIEM, EDR and SOAR** (open source) — **the most air-gap-capable open-source SOC stack** . **Features**: **AI worker fleet** with three modes (automation, manual, defensive); **threat intel** from AlienVault OTX, VirusTotal, abuse.ch (Feodo, ThreatFox, URLhaus) with stale-indicator pruning; **air-gap mode**—OSV mirror, threat feeds served internally, no CDN, local Ollama; **fleet exposure reporting** with coverage transparency (`complete: false` when agents can't be read); **agent config validation** with regex compilation checks before pushing to endpoints . **Tech stack**: Sanic (Python), React, MySQL, RabbitMQ, Ollama. **Deploy**: Self-hosted (Docker Compose). **Trade-off**: **MySQL per-agent databases** add operational complexity; threat feeds require auth keys for abuse.ch (free account) . **Best for**: organizations needing an air-gapped SOC platform with AI triage and endpoint orchestration—especially regulated environments where no telemetry can leave the network .



- **Security Shallots**

  **Lightweight, self-hosted SIEM that runs on anything** (PyPI) — **the easiest entry point to AI-assisted security monitoring** . **Features**: **Ingests** Suricata, Syslog, pfSense, Wazuh, CrowdSec, Pi-hole, Argus agents, and web logs; **normalizes, deduplicates, auto-classifies severity**; **correlates patterns** (port scans, brute force, lateral movement); **groups into incidents** with runbooks; **AI triage via API** (OpenAI/Anthropic) or local Ollama—no GPU needed; **hardware auto-detection** adjusts profile based on RAM/CPU . **Profiles**: Lite (<2 GB, Suricata+syslog); Micro (2–4 GB, +CrowdSec); Standard (4–8 GB, +Wazuh, VictoriaLogs, Grafana); Full (8+ GB, threat engine with baselines, graph, ML) . **Tech stack**: Python, SQLite. **Deploy**: `pip install .`; `shallot run`; systemd service . **Trade-off**: **Small-scale focus**—not enterprise SOC; threat engine disabled on low-RAM profiles; SQLite limits retention at high volume . **Best for**: homelabs, small businesses, and branch offices wanting functional AI-assisted monitoring without Elastic or Splunk infrastructure—especially those starting on a Raspberry Pi or old laptop .



- **OpenUBA**

  **Open-source User & Entity Behavior Analytics framework** (open source, ~523 stars) — **the most focused open-source UEBA project** for behavioral anomaly detection . **Features**: **UEBA framework** for security analytics; developed by data scientists and security analysts; designed for detecting anomalous user and entity behavior; **BETA** status . **Tech stack**: Python. **Deploy**: Self-hosted. **Trade-off**: **BETA**—not production-hardened; smaller community; no built-in alert fusion or LLM triage . **Best for**: data scientists and security analysts wanting a UEBA framework to build behavioral detection models—not a turnkey SOC platform .



### Additional Strong Open-Source Options



- **Click2Fix** — Open-source SOAR platform for automated SOC operations (open source). Integrates with Wazuh, MITRE ATT&CK mapping, playbook-driven automation, audit logging . **Note**: **SOAR layer, not AI SOC**—response orchestration without LLM triage. **Best for**: teams wanting automated response on top of Wazuh detection.

- **No mature open-source equivalent to CrowdStrike Charlotte AI or Cortex XSIAM exists.** Those platforms bundle adversary intelligence, threat graphs, and years of detection content that open-source projects cannot replicate. **AiSOC** provides the closest approximation for self-hosted teams .



**Frameworks for building custom systems**: Combine **AiSOC** for alert fusion and AI triage with **Sentora** for air-gapped SIEM/EDR and **OpenUBA** for behavioral analytics—creating a layered open-source AI SOC stack. **None of these match CrowdStrike's adversary intelligence or Cortex XSIAM's platform consolidation**, but for core SOC triage, investigation, and response, the options are production-capable.



## How to Contribute



1. Fork the repo.

2. Add/edit entries in `README.md` (follow existing format).

3. Include: name, link, 1–2 sentence description, license (for open-source), and whether it's SaaS or open-source.

4. Submit PR with a short explanation.



Star the repo if you find it useful!



## Disclaimer



- This is a **community-curated** list — not exhaustive and not an endorsement.

- AI security operations platforms handling telemetry and incident data must comply with data protection regulations (GDPR, CCPA, etc.) and implement appropriate access controls and audit trails.

- **The "agentic SOC platform" vs. "SIEM with AI" vs. "UEBA framework" vs. "SOAR" distinction is critical.** **Druva DruAI, Microsoft Security Copilot, CrowdStrike Charlotte AI, and Cortex XSIAM** are **agentic SOC platforms**—they provide AI-driven investigation and response within their ecosystems . **AiSOC and Sentora** are **open-source SOC stacks**—they combine ingest, detection, AI triage, and governed response in self-hosted packages . **Security Shallots** is a **lightweight SIEM**—it provides monitoring and AI triage at small scale . **OpenUBA** is a **UEBA framework**—it focuses on behavioral analytics, not full SOC operations . **Click2Fix** is a **SOAR**—it orchestrates response without LLM triage . **Choose based on whether you need full SOC operations, air-gapped deployment, lightweight monitoring, behavioral analytics, or response orchestration.**

- **AiSOC is the most complete open-source AI SOC**—833 executable detection rules, LLM-agent triage with Investigation Ledger, and no API keys required (bundled local model) . **The trade-off**: ~8 GB RAM minimum for core profile; local model is not frontier-quality (44/50 usable verdicts on test) . **For teams wanting auditability and self-hosting, it is the strongest starting point.**

- **Sentora is the air-gap choice**—OSV mirror, internal threat feeds, local Ollama, no CDN . **The trade-off**: MySQL per-agent databases add complexity; threat feeds need abuse.ch auth keys .

- **Security Shallots is the pragmatic homelab/small-office option**—runs on a Raspberry Pi, auto-detects hardware, provides AI triage via API or local Ollama . **The trade-off**: not enterprise-scale; SQLite limits retention.

- **Druva DruAI's Deep Analysis Agents reduce 2–3 day investigations to 8–10 minutes**—with Dru MetaGraph providing tenant-specific context across backups and identities . **The trade-off**: requires Druva platform; not a standalone SOC tool .

- **H2O.ai h2oGPTe is the regulated-industry choice**—air-gapped, SOC 2 Type 2, ISO 27001, FedRAMP High (government edition), with 79.7% GAIA accuracy (vendor-reported) . **The trade-off**: quote-only, annual contracts, complex setup .

- **Hugging Face Enterprise's $20/user/month Team plan** is the most accessible entry point for open model access with governance—1 TB private storage per seat, 40 min ZeroGPU/day . **The trade-off**: it is an AI platform, not a SOC tool.

- Self-hosted open-source solutions require proper infrastructure (Docker, ~8–12 GB RAM for AiSOC; MySQL/RabbitMQ for Sentora), security hardening, and ongoing maintenance. **SOC platforms handle sensitive incident data**—ensure your deployment meets your organization's security and compliance requirements before connecting production telemetry.



---



**Made for SOC analysts, security engineers, and organizations building transparent AI-driven security operations solutions.**

Let's make AI-Driven Security Operations Hubs more open, data-driven, and investigation-auditable.
