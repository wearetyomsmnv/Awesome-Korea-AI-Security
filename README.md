# Awesome Korea AI Security [![Awesome](https://awesome.re/badge.svg)](https://awesome.re) ![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg) ![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)

> A curated list of South Korean AI Security, LLM Red Teaming, Agentic Defense, Safety Benchmarks, and Regulatory Frameworks.

South Korea has rapidly built one of the most mature AI security ecosystems in the Asia-Pacific region—bridging state-backed evaluation hubs (**Korea AISI**, **KISA**, **FSI**), sovereign AI hyperscalers (**NAVER Cloud**, **LG AI Research**, **KT**), and specialized offensive/red-teaming powerhouses (**AIM Intelligence**, **Theori**, **SelectStar**, **S2W**).

---

## Contents

- [1. Government Institutes & Regulatory Bodies](#1-government-institutes--regulatory-bodies)
- [2. National Guidelines & Compliance Checklists](#2-national-guidelines--compliance-checklists)
- [3. Agentic AI & MCP Security Tools](#3-agentic-ai--mcp-security-tools)
- [4. Automated Red Teaming & Jailbreak Frameworks](#4-automated-red-teaming--jailbreak-frameworks)
- [5. Safety Benchmarks, Datasets & Open Guard Models](#5-safety-benchmarks-datasets--open-guard-models)
- [6. Corporate Frameworks & Commercial Guardrails](#6-corporate-frameworks--commercial-guardrails)
- [7. Academic Labs & Research Groups](#7-academic-labs--research-groups)
- [8. Korean AI Security Terminology (Search Cheat Sheet)](#8-korean-ai-security-terminology-search-cheat-sheet)
- [Contributing](#contributing)

---

## 1. Government Institutes & Regulatory Bodies

* **[Korea AI Safety Institute (Korea AISI / 인공지능안전연구소)](https://www.aisi.re.kr/eng)** - Operating under the Electronics and Telecommunications Research Institute (ETRI) in Pangyo, Korea AISI serves as the national hub for frontier model safety evaluations, red-teaming methodologies, and international AI safety standardization.
* **[KISA (Korea Internet & Security Agency / 한국인터넷진흥원)](https://www.kisa.or.kr/EN)** - The primary operational cybersecurity agency under MSIT, publishing technical security guidelines for generative AI lifecycle management, RAG architectures, and vulnerability disclosure.
* **[TTA (Telecommunications Technology Association / 한국정보통신기술협회)](https://www.tta.or.kr/eng/)** - Operates the national **CAT (Certification of AI Trustworthiness)** program, conducting technical audits and risk management verification aligned with ISO/IEC 42001 and ISO/IEC 23894.
* **[FSI (Financial Security Institute / 금융보안원)](https://www.fsec.or.kr/eng)** - Oversees AI security in the banking and fintech sectors, enforcing network/model isolation standards and hosting national Financial AI Red Teaming competitions.
* **[PIPC (Personal Information Protection Commission / 개인정보보호위원회)](https://www.pipc.go.kr/eng/)** - Enforces data privacy compliance across LLM training pipelines, inference APIs, and cross-border telemetry transfers.

---

## 2. National Guidelines & Compliance Checklists

* **AI Security Guideline (`인공지능(AI) 보안 안내서`)** *(KISA & MSIT)* - Lifecycle security checklist for AI developers and service operators. Covers RAG vector database access control, embedding poisoning defenses, supply chain integrity (weights/library verification), and Model DoS rate limiting.
* **Guide on Processing Personal Information for Generative AI Development & Utilization (`생성형 AI 개발·활용을 위한 개인정보 처리 안내서`)** *(PIPC)* - Regulatory and technical guardrails for PII scrubbing, synthetic data usage, and external LLM API governance.
* **Financial Sector Generative AI Security Guidelines (`금융분야 생성형 AI 보안 가이드라인`)** *(FSI)* - Mandatory security architecture controls for deploying LLMs and autonomous agents in Korean financial institutions.

---

## 3. Agentic AI & MCP Security Tools

* **[AIM-Intelligence/AIM-MCP](https://github.com/AIM-Intelligence/AIM-MCP)** - Comprehensive Model Context Protocol (MCP) security proxy and toolset for protecting AI agents. Includes:
  * `ai-safety-guard`: Context-aware policy enforcement before invoking external MCP tools (`email`, `slack`, `database`, `file`, `web`) with granular permission tiers (`read`, `write`, `execute`, `delete`).
  * `prompt-injection-detector`: Detection engine covering 15+ OWASP LLM01:2025 injection patterns with quantitative risk scoring (0–100).
  * `credential-scanner` & `url-security-validator`: Real-time secret masking (50+ credential formats) and anti-phishing/homograph validation for agent browsing.
* **[simon-p-j-r/LLM4Pentest](https://github.com/simon-p-j-r/LLM4Pentest)** - Multi-agent offensive security and penetration testing framework featuring dynamic MCP tool creation and automated exploit planning.

---

## 4. Automated Red Teaming & Jailbreak Frameworks

* **[AIM-Intelligence/Automated-Multi-Turn-Jailbreaks](https://github.com/AIM-Intelligence/Automated-Multi-Turn-Jailbreaks)** - Automated multi-turn conversational red-teaming framework implementing *Crescendo*, *Actor Attack* (persona/historical context escalation), and *Acronym Attack* with dynamic prompt rewriting upon refusal detection.
* **[selectstar-ai/STAR-Teaming-paper](https://github.com/selectstar-ai/STAR-Teaming-paper)** *(ACL 2026)* - Black-box automated red-teaming framework utilizing a *Strategy-Response Multiplex Network* to discover, combine, and explain multi-strategy jailbreaks against aligned LLMs.
* **[selectstar-ai/FinRED-paper](https://github.com/selectstar-ai/FinRED-paper)** *(2026)* - Domain-specific red-teaming framework and evaluation pipeline designed to uncover compliance, fraud, and advisory vulnerabilities in financial LLMs.
* **[GFNOrg/red-teaming](https://github.com/GFNOrg/red-teaming)** *(KAIST)* - Official implementation of diverse attack generation using Generative Flow Networks (GFlowNets) and Reinforcement Learning to prevent mode collapse during automated red-teaming.

---

## 5. Safety Benchmarks, Datasets & Open Guard Models

* **[AIM-Intelligence/XL-SafetyBench](https://github.com/AIM-Intelligence/XL-SafetyBench)** - Large-scale multilingual safety benchmark co-developed by **AIM Intelligence**, **Korea AISI**, **KT Corporation**, and **Microsoft**. Evaluates Attack Success Rate (ASR), Not-Unsafe Rate (NSR), and Context-Sensitive Safety Rate (CSR) with native country-specific profiles (`--country "South Korea"`).
* **[naver-ai/korean-safety-benchmarks](https://github.com/naver-ai/korean-safety-benchmarks)** - Foundational Korean LLM safety datasets developed by **NAVER Cloud**, **KAIST**, and **SNU**:
  * **SQuARe**: Sensitive Questions and Acceptable Responses dataset tailored to Korean socio-cultural norms.
  * **KoSBi**: Korean Social Bias dataset (~68,000 context-sentence pairs) with demographic taxonomy and toxicity generation scripts.
* **[Datumo (SelectStar) Hugging Face Hub](https://huggingface.co/datumo)** - Open-weights safety evaluation ecosystem featuring:
  * **Datumo-Guard**: Korean-centric LLM safety classifier and guardrail judge model.
  * **RED-Datumo-REDBench-KR**: Adversarial red-teaming benchmark targeting Korean linguistic nuances and jailbreak patterns.
* **[daekeun-ml/evaluate-llm-on-korean-dataset](https://github.com/daekeun-ml/evaluate-llm-on-korean-dataset)** - Evaluation suite for Korean LLMs/SLMs (KMMLU-Pro, MuSR-Ko, LogicKor), widely used to measure utility degradation and false-refusal rates after applying safety alignment or runtime guardrails.

---

## 6. Corporate Frameworks & Commercial Guardrails

* **[NAVER AI Safety Framework (ASF 2.0)](https://clova.ai/en/tech-blog/en-navers-ai-safety-framework-asf)** - Flagship corporate AI governance and red-teaming methodology in South Korea. **ASF 2.0** extends safety verification from standalone foundation models (HyperCLOVA X) to **On-Service AI**, multi-model orchestrators, and autonomous **AI Agents** (shopping, browser, and workflow agents), incorporating the *AI Impact Assessment Matrix* and internal audit protocol (**CHEC 2.0**).
* **[Theori — αprism (AlphaPrism)](https://aprism.io/)** - Ultra-low-latency inline LLM guardrail and monitoring platform built by offensive security research firm **Theori** (`github.com/theori-io`). Defends against direct/indirect prompt injections, jailbreaks, and PII/IP exfiltration.
* **[S2W — TALON AI Red Teaming](https://s2w.inc/en/solutions/ai-red-teaming)** - Cyber Threat Intelligence (CTI)-driven red-teaming service developed by KAIST spin-off **S2W**. Combines dark-web adversary payload tracking with hands-on exploitation of enterprise RAG pipelines and agentic workflows.

---

## 7. Academic Labs & Research Groups

* **KAIST (Korea Advanced Institute of Science and Technology)** - Active research across GFlowNet-based red teaming, Mixture-of-Experts (MoE) routing vulnerabilities, backdoor mitigation, and alignment robustness.
* **SNU (Seoul National University) & POSTECH** - Research focused on Korean socio-cultural safety alignment, hallucination detection, and privacy-preserving machine learning (Differential Privacy & Machine Unlearning).
* **Korea University (Institute of Cyber Security & Privacy)** - Applied research on adversarial machine learning, supply-chain security for open-weight models, and national regulatory compliance.

---

## 8. Korean AI Security Terminology (Search Cheat Sheet)

Use these Korean keywords when searching GitHub, DBpia, RISS, or government portals (`kisa.or.kr`, `aisi.re.kr`) for primary technical documentation:

| English Term | Korean Term (Hangul) | Romanization / Notes |
|---|---|---|
| **AI Security Guideline** | `인공지능 보안 안내서` | Primary search query for KISA technical checklists |
| **AI Safety Institute** | `인공지능안전연구소` | Official name of Korea AISI |
| **Generative AI Security** | `생성형 AI 보안` | Used in enterprise & financial regulatory docs |
| **AI Red Teaming** | `AI 레드팀` / `생성형 AI 레드팀` | Used for national competitions & technical reports |
| **Prompt Injection** | `프롬프트 인젝션` | Direct (`직접`) & Indirect (`간접`) injection |
| **Jailbreak** | `탈옥 공격` / `제일브레이크` | Literal translation (`탈옥`) is frequently used in papers |
| **AI Agent Security** | `AI 에이전트 보안` | Emerging keyword for MCP & tool-use defense |
| **Personal Data / PII Leak** | `개인정보 유출` | Key term in PIPC & KISA compliance audits |
| **Trustworthy AI Certification** | `인공지능 신뢰성 인증 (CAT)` | TTA's voluntary/regulatory audit framework |

---

## Related Awesome Lists

* [Awesome-LLMSecOps](https://github.com/wearetyomsmnv/Awesome-LLMSecOps) - Curated list of LLM SecOps tools, architectures, and best practices.
* [Awesome-China-AI-Security](https://github.com/wearetyomsmnv/Awesome-China-AI-Security) - Curated list of Chinese AI Security standards, red-teaming benchmarks, and open-source tools.
* [Autonomous Agent Defense Matrix](https://wearetyomsmnv.github.io/Autonomous-Agent-Defense-Matrix/) - Security taxonomy and defense matrix for autonomous AI agents.

---

## Contributing

Contributions, issue reports, and pull requests are welcome! If you know of an open-source Korean AI security tool, dataset, paper, or regulatory standard not listed here, please open a PR.

## License

This repository is licensed under the [MIT License](LICENSE).
